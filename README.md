### How to get into your build:

### Step 1. Add the JitPack repository to your build file

Add it in your root build.gradle at the end of repositories:

```gradle 
	dependencyResolutionManagement {
		repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
		repositories {
			mavenCentral()
			maven { url 'https://jitpack.io' }
		}
	}
 ```
### Step 2. Add the dependency

```gradle 
	dependencies {
	        implementation 'com.github.thuandev23:ShimmerEffectCompose:Tag'
	}
```
other
```gradle 
	dependencies {
	        implementation ("com.github.thuandev23:ShimmerEffectCompose:1.0")
	}
```


### Add in your code: 

```gradle
                        ShimmerListItem(
                            isLoading = isLoading,
                            shimmerContent = { // can be replaced with a custom shimmer layout
                                Column(modifier = Modifier.padding(16.dp)) {
                                    Box(
                                        modifier = Modifier
                                            .fillMaxWidth()
                                            .height(150.dp)
                                            .clip(RoundedCornerShape(8.dp))
                                            .shimmerEffect()
                                    )
                                    Spacer(modifier = Modifier.height(8.dp))
                                    Box(
                                        modifier = Modifier
                                            .fillMaxWidth(0.6f)
                                            .height(20.dp)
                                            .shimmerEffect()
                                    )
                                }
                            },
                            contentAfterLoading = {
                                Row(
                                    modifier = Modifier
                                        .fillMaxWidth()
                                        .padding(16.dp)
                                ) {
                                    Icon(
                                        imageVector = Icons.Default.Home,
                                        contentDescription = null,
                                        modifier = Modifier.size(100.dp)
                                    )
                                    Spacer(modifier = Modifier.width(16.dp))
                                    Text(
                                        text = "This is a long text to show that our shimmer display " +
                                                "is looking perfectly fine"
                                    )
                                }
                            },
                            modifier = Modifier
                                .fillMaxWidth()
                                .padding(16.dp)
                        )
```


