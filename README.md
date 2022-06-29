Template
============================

Template for making new Project

Introduction
------------

build.gradle(app):
    buildFeatures {
        dataBinding true
    }

All xml:
    parentLayout -> layout (leave "android", "app", "tools", and "context")

build.gradle(Module)
    // for nav
    implementation "androidx.navigation:navigation-fragment-ktx:2.4.2"
    implementation "androidx.navigation:navigation-ui-ktx:2.4.2"

*Add a navigation graph to the project

activity_main.xml
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical">
        <fragment
            android:id="@+id/navHostFragment"
            android:name="androidx.navigation.fragment.NavHostFragment"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            app:navGraph="@navigation/navigation"
            app:defaultNavHost="true" />
    </LinearLayout>

???Fragment.kt
    override fun onCreateView(inflater: LayoutInflater, container: ViewGroup?,
        savedInstanceState: Bundle?): View {
        val binding = DataBindingUtil.inflate<Fragment???Binding>(inflater,
            R.layout.fragment_first, container, false)
        return binding.root
    }

Good luck!

(VCS->)

-------

Copyright 2022 Norram.