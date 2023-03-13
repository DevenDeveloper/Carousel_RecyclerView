# Carousel Recycler view
The CenterZoomLayoutManager is designed to give a centered and zoomed-in effect to the items in a RecyclerView. It achieves this by scaling the items based on their position in the RecyclerView. Items in the center of the screen are scaled up, while items at the top and bottom of the screen are scaled down.

One of the benefits of using the CenterZoomLayoutManager is that it can enhance the visual appeal of your app's user interface. It can make your app look more dynamic and engaging by drawing the user's attention to the centered and zoomed-in items.

In conclusion, the CenterZoomLayoutManager is a useful library for Android developers who want to create visually stunning and interactive RecyclerViews. It offers a unique scrolling behavior that can improve the user experience of your app and make it stand out from the competition.

# Preview:


https://user-images.githubusercontent.com/50836835/224488887-6a1f9b07-2f16-47a9-9e4c-f53b504bb853.mp4


# How to Install
> Step 1. Add the JitPack repository to your build file
  * Add it in your root build.gradle at the end of repositories:

```
allprojects {
	repositories {
		maven { url 'https://jitpack.io' }
	}
}
```
  
> Step 2. Add the dependency
```
dependencies {
	  implementation 'com.github.DevenDeveloper:Carousel_RecyclerView:1.1.0'
}
```

# Example
```kotlin
val images: MutableList<ModelImages> = ArrayList()
images.add(ModelImages(1, "", "https://images.idgesg.net/images/article/2019/05/cso_best_security_software_best_ideas_best_technology_lightbulb_on_horizon_of_circuit_board_landscape_with_abstract_digital_connective_technology_atmosphere_ideas_innovation_creativity_by_peshkov_gettyimages-965785212_3x2_2400x1600-100797318-large.jpg?auto=webp&quality=85,70"))
images.add(ModelImages(2, "", "https://imageio.forbes.com/specials-images/imageserve/637b1d11729a96ce28ea598c/The-Top-10-Tech-Trends-In-2023-Everyone-Must-Be-Ready-For/960x0.jpg?format=jpg&width=960"))
images.add(ModelImages(3, "", "https://s35764.pcdn.co/wp-content/uploads/2021/09/tech2-1024x630.png"))
images.add(ModelImages(4, "", "https://investormediapro.bg/wp-content/uploads/2021/02/Tech-of-tomorrow-tint-1130x636-1.jpg"))
images.add(ModelImages(4, "", "https://www.valueresearchonline.com/content-assets/images/50971_20220623-tech__w660__.jpg"))

val layoutManager: RecyclerView.LayoutManager = CenterZoomLayoutManager(
	this, LinearLayoutManager.HORIZONTAL,
        false
)

recyclerView.scrollToPosition(images.size / 2)
val snapHelper: SnapHelper = LinearSnapHelper()
snapHelper.attachToRecyclerView(recyclerView)
recyclerView.layoutManager = layoutManager
recyclerView.adapter = ImageAdapter(this, images)
```
  
