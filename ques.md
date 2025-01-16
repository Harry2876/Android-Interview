**Core Android (Expanded)**

1.  **What is an Intent in Android?**

-  **Answer**: An Intent is a messaging object used to request an action from another app component, such as starting a new activity or service.

2.  **What is a Fragment?**

-  **Answer**: A Fragment represents a portion of the UI within an Activity. It allows modular design and can be reused in multiple activities.

3.  **What is ANR (Application Not Responding)?**

-  **Answer**: ANR occurs when the main thread is blocked for too long (5 seconds for input or 10 seconds for broadcast execution).

4.  **What is Context in Android?**

-  **Answer**: Context provides access to application-specific resources and classes. For example, getApplicationContext() gives global context, and getContext() provides local context.

5.  **What is the difference between** onCreate() **and** onStart()**?**

-  **Answer**: onCreate() is called once during the activity lifecycle to initialize resources, while onStart() is called when the activity becomes visible.

6.  **What is a BroadcastReceiver?**

-  **Answer**: A component that listens for and responds to system-wide broadcast events (e.g., battery low, network change).

7.  **What are Content Providers?**

-  **Answer**: They enable apps to access data stored in other apps, such as contacts or media files, using a URI.

8.  **What is the purpose of an Adapter in Android?**

-  **Answer**: Adapters bind data to UI components like ListView and RecyclerView.

9.  **What is the Manifest file in Android?**

-  **Answer**: It declares essential information about the app, including permissions, components, and minimum API level.

10.  **Explain the difference between** Parcelable **and** Serializable**.**

-  **Answer**: Parcelable is more efficient and used in Android, while Serializable is a Java interface that uses reflection and is slower.

11.  **What are Jetpack libraries?**

-  **Answer**: Jetpack libraries like Navigation, Data Binding, Room, and WorkManager simplify development and promote best practices.

12.  **What is the role of ViewModel in Android?**

-  **Answer**: ViewModel stores and manages UI-related data in a lifecycle-conscious way to survive configuration changes.

13.  **What is a Service in Android?**

-  **Answer**: A component used for long-running background operations, like playing music or fetching data.

14.  **What is the difference between** startService() **and** bindService()**?**

-  **Answer**: startService() creates a service that runs independently, while bindService() allows interaction between client and service.

15.  **What is Data Binding?**

-  **Answer**: Data Binding connects UI components in layouts to data sources, allowing automatic updates of the UI when data changes.

16.  **What is View Binding?**

-  **Answer**: View Binding generates classes for XML layouts, allowing direct references to views without findViewById().

17.  **What is Room Database?**

-  **Answer**: Room is a Jetpack library providing an abstraction layer over SQLite to make database operations more manageable.

18.  **What are Android Permissions?**

-  **Answer**: Permissions are required to access restricted features (e.g., camera, location).

19.  **Explain Android's Handler class.**

-  **Answer**: A Handler allows communication between a worker thread and the main thread, enabling message handling and runnable execution.

20.  **What is the difference between Implicit and Explicit Intents?**

-  **Answer**: Explicit intents specify the target component directly, while implicit intents let the system resolve the component.

**Kotlin**

1.  **What is null safety in Kotlin?**

-  **Answer**: Kotlin uses nullable (?) and non-nullable types to prevent NullPointerException.

2.  **What are higher-order functions?**

-  **Answer**: Functions that take other functions as parameters or return functions. Example: map().

3.  **Difference between** val **and** var**.**

-  **Answer**: val is immutable, while var is mutable.

4.  **What are extension functions?**

-  **Answer**: Functions added to existing classes without modifying them. Example:

fun String.lastChar(): Char = this[this.length - 1]

5.  **What is a sealed class?**

-  **Answer**: A sealed class restricts inheritance to a predefined set of subclasses.

6.  **What are data classes?**

-  **Answer**: Special classes for holding data. They generate equals(), hashCode(), and toString() automatically.

7.  **What is a companion object?**

-  **Answer**: An object associated with a class, similar to static members in Java.

8.  **What is lazy initialization in Kotlin?**

-  **Answer**: Lazy initializes properties only when accessed for the first time.

9.  **What is the** safe-call **operator?**

-  **Answer**: It allows null-safe access using ?..

10.  **What is the Elvis operator?**

-  **Answer**: Provides a default value for nullable types using ?:.

**RecyclerView**

1.  **What is a RecyclerView in Android?**

-  **Answer**: RecyclerView is an advanced and flexible version of ListView. It is used to display large sets of data efficiently by recycling views that are no longer visible.

2.  **What are the components of RecyclerView?**

-  **Answer**:

-  **Adapter**: Binds data to the RecyclerView.

-  **ViewHolder**: Represents a single item view.

-  **LayoutManager**: Positions items within RecyclerView (e.g., LinearLayoutManager, GridLayoutManager).

-  **ItemDecoration**: Adds visual decorations.

-  **ItemAnimator**: Animates changes in items.

3.  **How does RecyclerView improve performance?**

-  **Answer**: It uses ViewHolder for efficient view recycling, reducing the number of findViewById() calls.

4.  **What is the role of LayoutManager in RecyclerView?**

-  **Answer**: LayoutManager determines how items are displayed (linear, grid, or custom).

5.  **What is DiffUtil?**

-  **Answer**: DiffUtil calculates the difference between two lists and updates only the changed items in RecyclerView.

6.  **What is the purpose of ViewHolder?**

-  **Answer**: ViewHolder holds references to views for each item to avoid redundant findViewById() calls.

7.  **How can you add a click listener to RecyclerView items?**

-  **Answer**: By implementing an interface in the Adapter or using setOnClickListener in ViewHolder.

8.  **How do you handle dynamic data changes in RecyclerView?**

-  **Answer**: Use notifyDataSetChanged(), notifyItemInserted(), or DiffUtil for efficient updates.

9.  **What is the difference between ListView and RecyclerView?**

-  **Answer**: RecyclerView is more efficient, supports animations, and is highly customizable compared to ListView.

10.  **How do you implement swipe-to-delete in RecyclerView?**

-  **Answer**: Use ItemTouchHelper for swipe gestures.

11.  **What is SnapHelper in RecyclerView?**

-  **Answer**: SnapHelper aligns items to the center of the RecyclerView (e.g., PagerSnapHelper, LinearSnapHelper).

12.  **What are ItemDecorations?**

-  **Answer**: ItemDecorations are used to draw custom dividers or decorations for RecyclerView items.

13.  **How do you create multiple view types in RecyclerView?**

-  **Answer**: Override getItemViewType() in Adapter and inflate layouts accordingly.

14.  **How do you handle pagination in RecyclerView?**

-  **Answer**: Use RecyclerView.OnScrollListener and load more data when the user scrolls to the end.

15.  **What is StaggeredGridLayoutManager?**

-  **Answer**: A LayoutManager for displaying items in a staggered grid pattern.

16.  **What is RecyclerView.Adapter?**

-  **Answer**: A class that binds data to RecyclerView and creates ViewHolder objects.

17.  **How do you optimize RecyclerView performance?**

-  **Answer**: Use DiffUtil, avoid nesting, and set fixed size with setHasFixedSize(true).

18.  **What are RecyclerView Animations?**

-  **Answer**: Default or custom animations applied to add, remove, or move items.

19.  **How does RecyclerView reuse views?**

-  **Answer**: RecyclerView uses a pool of ViewHolders to reuse item views, reducing memory usage.

20.  **Can you implement RecyclerView with Epoxy?**

-  **Answer**: Yes, Epoxy simplifies RecyclerView implementation with models and pre-built components.

**MVVM (Model-View-ViewModel)**

1.  **What is MVVM?**

-  **Answer**: MVVM is an architectural pattern that separates UI (View), logic (ViewModel), and data (Model).

2.  **How does ViewModel work?**

-  **Answer**: ViewModel holds and manages UI-related data to survive configuration changes.

3.  **What is LiveData?**

-  **Answer**: LiveData is a lifecycle-aware data holder that notifies observers when data changes.

4.  **What is MutableLiveData?**

-  **Answer**: MutableLiveData allows data modification and is usually observed by the View.

5.  **How do you implement data binding in MVVM?**

-  **Answer**: Use <data> tags in XML to bind ViewModel properties directly to the UI.

6.  **What is the role of a Repository in MVVM?**

-  **Answer**: Repository abstracts data sources (e.g., local database, remote API) and provides data to ViewModel.

7.  **Why use MVVM over MVP?**

-  **Answer**: MVVM reduces boilerplate code and integrates seamlessly with LiveData and ViewModel.

8.  **How do you test ViewModel?**

-  **Answer**: Use unit tests to verify ViewModel behavior, ensuring data updates as expected.

9.  **What is the role of Coroutines in MVVM?**

-  **Answer**: Coroutines simplify asynchronous operations in ViewModel, improving code readability.

10.  **What is the benefit of using LiveData in MVVM?**

-  **Answer**: LiveData ensures data updates only when the associated lifecycle is active.

...

Alright! Here's a detailed, expanded explanation for **all the remaining sections**:

**Epoxy RecyclerView**

1.  **What is Epoxy in Android?**

-  **Answer**: Epoxy is an open-source library that simplifies RecyclerView implementation by creating models for each item. It offers better abstraction and dynamic UI building.

2.  **What are Epoxy Models?**

-  **Answer**: Epoxy Models represent individual items in RecyclerView. These are created by extending EpoxyModel or using @EpoxyModelClass.

3.  **How does Epoxy improve RecyclerView implementation?**

-  **Answer**: It reduces boilerplate code by using annotations to automatically generate models and manage view bindings.

4.  **What are** EpoxyController **and** EpoxyAdapter**?**

-  **Answer**:

-  **EpoxyController**: A class to build models and manage updates dynamically.

-  **EpoxyAdapter**: Used when you need to create static lists of Epoxy Models.

5.  **How do you implement a model in Epoxy?**

-  **Answer**:

@EpoxyModelClass(layout = R.layout.item_view)

abstract class ItemViewModel : EpoxyModelWithHolder<ItemViewModel.Holder>() {

 @EpoxyAttribute lateinit var title: String

 override fun bind(holder: Holder) {

 holder.titleView.text = title

 }

 class Holder : EpoxyHolder() {

 lateinit var titleView: TextView

 override fun bindView(itemView: View) {

 titleView = itemView.findViewById(R.id.titleView)

 }

 }

}

6.  **What is an Epoxy Attribute?**

-  **Answer**: Epoxy attributes (annotated with @EpoxyAttribute) allow dynamic data to be passed to models.

7.  **How does Epoxy handle RecyclerView performance?**

-  **Answer**: Epoxy uses DiffUtil internally for efficient updates and view recycling.

8.  **Can you use DataBinding with Epoxy?**

-  **Answer**: Yes, Epoxy supports DataBinding by generating models that bind directly to layout XML files.

9.  **How do you set up Epoxy in a project?**

-  **Answer**: Add the Epoxy dependency in build.gradle and configure annotation processing.

10.  **What are Epoxy's built-in helpers?**

-  **Answer**: Built-in helpers like Carousel simplify creating common RecyclerView patterns (e.g., horizontal scrolling).

**Firebase Realtime Database**

1.  **What is Firebase Realtime Database?**

-  **Answer**: A cloud-hosted NoSQL database that updates data in real-time across all connected devices.

2.  **How do you set up Firebase Realtime Database in an Android project?**

-  **Answer**:

-  Add Firebase to the project via the Firebase console.

-  Include firebase-database dependency in build.gradle.

3.  **What is the structure of Firebase Realtime Database?**

-  **Answer**: Data is stored as JSON objects, with nodes and keys representing the hierarchical structure.

4.  **How do you read data from Firebase?**

-  **Answer**:

val database = FirebaseDatabase.getInstance().reference

database.child("users").addValueEventListener(object : ValueEventListener {

 override fun onDataChange(snapshot: DataSnapshot) {

 val user = snapshot.getValue(User::class.java)

 }

 override fun onCancelled(error: DatabaseError) {

 // Handle error

 }

})

5.  **How do you write data to Firebase?**

-  **Answer**:

val database = FirebaseDatabase.getInstance().reference

val user = User("John", 25)

database.child("users").child("user1").setValue(user)

6.  **What are Firebase Database Rules?**

-  **Answer**: Rules control access to the database. Example:

{

 "rules": {

 ".read": "auth != null",

 ".write": "auth != null"

 }

}

**Firebase Authentication**

1.  **What is Firebase Authentication?**

-  **Answer**: A feature to handle user sign-up, sign-in, and identity verification using email, Google, Facebook, etc.

2.  **How do you implement email authentication?**

-  **Answer**:

FirebaseAuth.getInstance().createUserWithEmailAndPassword(email, password)

 .addOnCompleteListener { task ->

 if (task.isSuccessful) {

 // User registered successfully

 }

 }

3.  **How does Firebase handle session management?**

-  **Answer**: Firebase automatically manages sessions using tokens.

4.  **What are Authentication Providers in Firebase?**

-  **Answer**: Email/password, Google, Facebook, Twitter, GitHub, and phone authentication.

**Retrofit and REST API**

1.  **What is Retrofit?**

-  **Answer**: A type-safe HTTP client for Android to interact with REST APIs.

2.  **How do you create a Retrofit instance?**

-  **Answer**:

val retrofit = Retrofit.Builder()

 .baseUrl("https://api.example.com/")

 .addConverterFactory(GsonConverterFactory.create())

 .build()

3.  **How do you define an API interface in Retrofit?**

-  **Answer**:

interface ApiService {

 @GET("users")

 suspend fun getUsers(): List<User>

}

4.  **How do you handle responses in Retrofit?**

-  **Answer**:

val api = retrofit.create(ApiService::class.java)

val users = api.getUsers()

5.  **What is a Converter Factory in Retrofit?**

-  **Answer**: A factory for serializing and deserializing data (e.g., Gson, Moshi).

**Dagger and Hilt**

1.  **What is Dagger?**

-  **Answer**: Dagger is a Dependency Injection framework for managing object creation and dependency resolution.

2.  **What is Hilt?**

-  **Answer**: Hilt is a simplified DI library built on Dagger, designed for Android.

3.  **What is a Component in Dagger?**

-  **Answer**: An interface that tells Dagger where to inject dependencies.

4.  **What are Modules in Dagger?**

-  **Answer**: Modules provide instances of dependencies.

5.  **How do you define a Dependency in Hilt?**

-  **Answer**: Use @Module and @Provides annotations to declare dependencies.
