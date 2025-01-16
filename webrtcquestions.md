# WebRTC Interview Questions and Answers

## **Basic Questions**

1. **What is WebRTC, and why is it used?**  
   WebRTC (Web Real-Time Communication) is a technology that enables peer-to-peer audio, video, and data communication in real-time directly between browsers or applications without requiring intermediaries (except signaling).

2. **What are the primary components of WebRTC?**  
   - **MediaStream**: Captures audio and video.  
   - **RTCPeerConnection**: Manages peer-to-peer connections and media exchange.  
   - **RTCDataChannel**: Allows arbitrary data communication between peers.

3. **What is the purpose of ICE in WebRTC?**  
   ICE (Interactive Connectivity Establishment) helps in finding the best path between peers for communication, even through NAT or firewalls.

4. **Explain the role of STUN and TURN servers in WebRTC.**  
   - **STUN**: Determines a peer's public IP address.  
   - **TURN**: Relays media between peers if a direct connection cannot be established.

5. **What is SDP (Session Description Protocol), and how does it work in WebRTC?**  
   SDP is a protocol used to describe multimedia sessions, including codecs, formats, and connection information. It is exchanged during signaling.

6. **What is the significance of `getUserMedia()` in WebRTC?**  
   It captures media from the user's devices (camera and microphone) and provides a MediaStream.

7. **How does WebRTC handle NAT traversal?**  
   WebRTC uses STUN to discover public IPs and TURN as a fallback to relay media through a server.

8. **What are ICE candidates, and why are they important?**  
   ICE candidates are network configurations (IP/port pairs) shared between peers to establish a connection.

9. **What are the different states of an RTCPeerConnection?**  
   - New  
   - Connecting  
   - Connected  
   - Disconnected  
   - Failed  
   - Closed  

10. **How does WebRTC ensure secure communication?**  
    WebRTC encrypts data using DTLS (Data Transport Layer Security) and SRTP (Secure Real-time Transport Protocol).

---

## **Intermediate Questions**

11. **What is the difference between STUN and TURN servers?**  
    - STUN only provides the public IP of the client.  
    - TURN relays media if direct peer-to-peer communication fails.

12. **What is the role of a signaling server in WebRTC?**  
    The signaling server exchanges metadata (SDP, ICE candidates) between peers to establish a connection.

13. **How does WebRTC support peer-to-peer data exchange?**  
    Through the RTCDataChannel API, which allows reliable/unreliable data transfer between peers.

14. **Explain the purpose of RTCPeerConnection in WebRTC.**  
    RTCPeerConnection is the core API managing the connection, ICE candidates, and media/data streams.

15. **What are DataChannels in WebRTC, and how are they used?**  
    DataChannels enable bidirectional communication of arbitrary data (e.g., chat messages, files) between peers.

16. **How do you add an ICE candidate in WebRTC?**  
    ```javascript
    peerConnection.addIceCandidate(new RTCIceCandidate(candidate));
    ```

17. **What are MediaStreams in WebRTC?**  
    MediaStreams represent audio and video streams captured from user devices or received from remote peers.

18. **How do you handle remote tracks in WebRTC?**  
    Use the `ontrack` event to add the remote track to a media element like `<video>`.

19. **What is the difference between `ontrack` and `onaddstream` in WebRTC?**  
    - `ontrack`: Modern API to handle individual tracks.  
    - `onaddstream`: Deprecated API that worked with entire streams.

20. **What is the role of codecs in WebRTC, and what are the common ones?**  
    Codecs encode and decode media streams. Common ones:  
    - Video: VP8, VP9, H.264.  
    - Audio: Opus, G.711.

---

## **Advanced Questions**

21. **How does WebRTC handle video compression and streaming?**  
    It uses video codecs (VP8, VP9) to compress streams, adapting to network conditions using bandwidth estimation algorithms.

22. **What are the main challenges in scaling a WebRTC application?**  
    Peer-to-peer architecture doesn't scale well for many users. SFU or MCU servers are used to manage multiple connections.

23. **What is the role of SFUs (Selective Forwarding Units) and MCUs (Multipoint Control Units) in WebRTC?**  
    - SFU: Forwards media streams selectively to participants.  
    - MCU: Decodes, mixes, and encodes streams for all participants.

24. **How do you establish a peer connection using WebRTC?**  
    - Create `RTCPeerConnection`.  
    - Add local media tracks.  
    - Create an offer and set the local description.  
    - Exchange SDP and ICE candidates via signaling.

25. **How does WebRTC support multiple streams from a single peer?**  
    By attaching multiple MediaStreams to the same PeerConnection.

26. **What is the significance of `createOffer()` and `createAnswer()` in WebRTC?**  
    - `createOffer()`: Generates SDP for initiating a connection.  
    - `createAnswer()`: Generates SDP in response to an offer.

27. **How do you renegotiate a WebRTC connection?**  
    Use `createOffer()` or `createAnswer()` again and reapply SDP through signaling.

28. **What are the common errors encountered in WebRTC, and how do you handle them?**  
    - `ICE connection failed`: Check TURN/STUN server configuration.  
    - `Permission denied`: Ensure user consent for camera/microphone.  
    - Debug using browser DevTools and WebRTC internals.

29. **What are the differences between `onicecandidate` and `oniceconnectionstatechange`?**  
    - `onicecandidate`: Triggered when a new ICE candidate is found.  
    - `oniceconnectionstatechange`: Triggered on state changes in the ICE connection.

30. **How can WebRTC be integrated with third-party signaling protocols like Socket.io or Firebase?**  
    Use these protocols to exchange SDP and ICE candidates during signaling.

---

## **Code-Specific Questions**

31. **Provide an example of creating a PeerConnection in WebRTC.**  
    ```javascript
    const pc = new RTCPeerConnection(configuration);
    ```

32. **Write a code snippet to handle a signaling message in WebRTC.**  
    ```javascript
    socket.on('signal', (data) => {
        if (data.sdp) {
            pc.setRemoteDescription(new RTCSessionDescription(data.sdp));
        }
        if (data.candidate) {
            pc.addIceCandidate(new RTCIceCandidate(data.candidate));
        }
    });
    ```

33. **How do you capture video from a camera using WebRTC? Provide an example.**  
    ```javascript
    navigator.mediaDevices.getUserMedia({ video: true })
        .then((stream) => {
            videoElement.srcObject = stream;
        });
    ```

34. **Provide a code example of how to set up a DataChannel in WebRTC.**  
    ```javascript
    const dataChannel = pc.createDataChannel('chat');
    dataChannel.onmessage = (event) => console.log('Message:', event.data);
    ```

35. **How do you close a WebRTC PeerConnection programmatically?**  
    ```javascript
    pc.close();
    ```

36. **Write code to add a remote ICE candidate.**  
    ```javascript
    pc.addIceCandidate(new RTCIceCandidate(candidate));
    ```

37. **How do you stream audio using WebRTC? Provide a code example.**  
    ```javascript
    navigator.mediaDevices.getUserMedia({ audio: true })
        .then((stream) => pc.addTrack(stream.getAudioTracks()[0], stream));
    ```

38. **Provide an example of how to attach a MediaStream to a video element.**  
    ```javascript
    videoElement.srcObject = stream;
    ```

39. **Write a WebRTC code snippet to exchange SDP between peers.**  
    ```javascript
    pc.createOffer()
        .then((offer) => pc.setLocalDescription(offer))
        .then(() => signalingServer.send({ sdp: pc.localDescription }));
    ```

40. **How do you handle the `onnegotiationneeded` event in WebRTC?**  
    Trigger renegotiation by creating and sending a new SDP offer.

---

## **Scenario-Based Questions**

41. **How would you implement a basic video chat application using WebRTC?**  
    - Capture media with `getUserMedia()`.  
    - Create a `RTCPeerConnection`.  
    - Exchange SDP and ICE candidates.

42. **How does WebRTC handle network changes during an ongoing session?**  
    It uses ICE to renegotiate connection paths automatically.

43. **What are the steps to enable screen sharing using WebRTC?**  
    Use `getDisplayMedia()` to capture the screen.

44. **How do you test the quality of a WebRTC connection in a production environment?**  
    Monitor metrics like packet loss, jitter, and latency using `getStats()`.

45. **How do you debug WebRTC-related issues in real-time?**  
    Use browser DevTools and chrome://webrtc-internals.

46. **What happens when one of the peers in a WebRTC session loses connection temporarily?**  
    WebRTC attempts reconnection using ICE restarts.

47. **How can WebRTC be used for live broadcasting?**  
    Stream media from a source peer to an SFU, which distributes it to viewers.

48. **How would you integrate WebRTC with a custom authentication system?**  
    Use token-based authentication during signaling.

49. **What are the steps to optimize WebRTC for low-latency communication?**  
    - Use adaptive bitrate codecs.  
    - Prioritize low-latency data transmission.

50. **How do you measure and improve bandwidth utilization in WebRTC?**  
    Use `RTCPeerConnection.getStats()` to monitor and optimize bitrate allocation.
