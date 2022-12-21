<!-- # Title -->
# Doc Reminder      |       **PRIVATE**
![Demo](https://media.discordapp.net/attachments/655489748885831713/1054754902099890256/1.png)


<!-- # Short Description -->

>- The user can add **Documents** with *images*, *title* and *validity*
>- The *images* can be added from the *gallery* or *camera*
>- It is possible to *delete* and *recover* any **Document** easily

This application is a scope of an idea that it is not complex itself but it is pretty meaningful to me. It was the first idea that my wife and I had
when I started studying for become an **Android Developer**. \
The idea itself was a simple application that allows the user to create document registrations in his cellphone in order to link it's validity and
it's image. It would allow any user to match, for example, one document that have 2 years validity purchase and you will have it saved locally (with further improvements in the cloud),
and then have all this information together ti easily access and avoid losing any own benefits. \
This application, as I said is a scoupe and I intend to improve it properly with time. 


<!-- # Badges -->
<div style="display: inline_block"><br>
    <img height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/androidstudio/androidstudio-original.svg">
    <img height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kotlin/kotlin-original.svg">
</div>

---

# Tags

`Android Studio` `Kotlin` `Coroutines` `MVVM` `Room` `Hilt` `Clean Architecture`

---


# Demo

![](https://media.discordapp.net/attachments/655489748885831713/1054750389779578950/1.gif)
>- The user is requested to accept permissions in the first the app is directed to the register a new document interface


Gallery | Camera
:-:|:-:
![](https://media.discordapp.net/attachments/655489748885831713/1054750393361502289/2.gif)  |  ![](https://media.discordapp.net/attachments/655489748885831713/1054750392648474633/3.gif)
>- Create new **Document** registries with images from the *gallery* or *camera*


![](https://media.discordapp.net/attachments/655489748885831713/1054750391847358554/4.gif)


<img height="100" width="200" src="https://media.discordapp.net/attachments/655489748885831713/1054754901546250280/2.png">    <img height="100" width="200" src="https://media.discordapp.net/attachments/655489748885831713/1054754902099890256/1.png">
>- **Documents** registered, when validity expires, displays a different color to the user

![](https://media.discordapp.net/attachments/655489748885831713/1054750391281131620/5.gif)
>- Easily *delete* a **Document**, but also have the possibility to *recover* it for a few seconds

![](https://media.discordapp.net/attachments/655489748885831713/1054750390354186370/6.gif)
>- Displays all the registered images from the **Document** and it's *validity* with a simple touch


---

# Code Example
```kotlin
private fun itemTouchHelperCallback(): ItemTouchHelper.SimpleCallback {
        return object: ItemTouchHelper
        .SimpleCallback(0, ItemTouchHelper.LEFT or ItemTouchHelper.RIGHT) {
            override fun onMove(
                recyclerView: RecyclerView,
                viewHolder: RecyclerView.ViewHolder,
                target: RecyclerView.ViewHolder
            ): Boolean {
                return false
            }

            override fun onSwiped(viewHolder: RecyclerView.ViewHolder, direction: Int) {
                val doc = adapterDoc.recoverDocPosition(viewHolder.adapterPosition)
                viewModel.onEvent(MainEvents.Delete(doc))
                Snackbar.make(binding.root, "Doc deleted successfully", Snackbar.LENGTH_LONG)
                    .setAction("Undo") {
                        viewModel.onEvent(MainEvents.Restore)
                    }.show()
            }
        }
    }
```

This code above shows the ItemHelper added to the adapter that allows the user to swip the item, right or left, and delete the selected **Document**. \
When the event is triggered, it displays a *Snackbar* that allows the user to **recover** the recently deleted item and replace it on the diplay again. \
The code only displays the request of the action, but not the code of the event itself.

---

# Libraries

>- [Timber](https://github.com/JakeWharton/timber)
>- [Lifecycle](https://developer.android.com/jetpack/androidx/releases/lifecycle)
>- [Coroutines](https://developer.android.com/kotlin/coroutines?hl=pt-br)
>- [KTX](https://developer.android.com/kotlin/ktx)
>- [Navigation Components](https://developer.android.com/guide/navigation)
>- [Hilt](https://dagger.dev/hilt/)
>- [ROOM](https://developer.android.com/jetpack/androidx/releases/room?hl=pt-br)
>- [Picasso](https://square.github.io/picasso/)
>- [Carousel View](https://github.com/sayyam/carouselview)
---

# Contributors

- [Thiago Rodrigues](https://www.linkedin.com/in/tods/)
