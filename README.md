
# Generated binding classes
https://developer.android.com/topic/libraries/data-binding/generated-binding

A binding class is generated for each layout file. By default, the name of the class is based on the name of the layout file, converting it to Pascal case and adding the Binding suffix to it. The above layout filename is activity_main.xml so the corresponding generated class is ActivityMainBinding. This class holds all the bindings from the layout properties (for example, the user variable) to the layout's views and knows how to assign values for the binding expressions.

# Create View in 'layout' tags

      <?xml version="1.0" encoding="utf-8"?>
      <layout xmlns:app="http://schemas.android.com/apk/res-auto"
          xmlns:tools="http://schemas.android.com/tools"
          xmlns:android="http://schemas.android.com/apk/res/android">

          <data class="com.example.generatedbindingclasses.ActivityMainBinding">
              <variable name="user" type="com.example.generatedbindingclasses.User"/>
          </data>

          <androidx.constraintlayout.widget.ConstraintLayout
              android:layout_width="match_parent"
              android:layout_height="match_parent"
              tools:context=".MainActivity">

              <TextView
                  android:id="@+id/firstName"
                  android:layout_width="wrap_content"
                  android:layout_height="wrap_content"
                  android:text="@{user.firstName}"
                  app:layout_constraintBottom_toBottomOf="parent"
                  app:layout_constraintLeft_toLeftOf="parent"
                  app:layout_constraintRight_toRightOf="parent"
                  app:layout_constraintTop_toTopOf="parent" />

          </androidx.constraintlayout.widget.ConstraintLayout>
      </layout>
      
# You can bind view via fallowing code in activity

        // Create a binding object
        var binding: ActivityMainBinding = ActivityMainBinding.inflate(layoutInflater)
        setContentView(binding.root)
        
# Custom binding class names
By default, a binding class is generated based on the name of the layout file, starting with an uppercase letter, removing underscores ( _ ), capitalizing the following letter, and suffixing the word Binding. The class is placed in a databinding package under the module package. For example, the layout file contact_item.xml generates the ContactItemBinding class. If the module package is com.example.my.app, then the binding class is placed in the com.example.my.app.databinding package.

        <data class="ContactItem">
            …
        </data>
        
You can also use the full package name where you want the binding class to be generated. The following example creates the ContactItem binding class in the com.example package:

        <data class="com.example.generatedbindingclasses.ActivityMainBinding">
            <variable name="user" type="com.example.generatedbindingclasses.User"/>
        </data>
        
Complete Code in view and activity can see in this repository
