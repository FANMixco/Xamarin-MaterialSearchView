<a href="https://github.com/sponsors/FANMixco/" target="_blank">
   <img src="https://raw.githubusercontent.com/FANMixco/Xamarin-SearchBar/master/bmc-rezr5vpd.gif" alt="sponsor" />
</a>

# Xamarin-MaterialSearchView
Cute library to implement SearchView in a Material Design Approach for Xamarin.Android, based on Miguel Catalan's version.

![](https://raw.githubusercontent.com/MiguelCatalan/MaterialSearchView/master/art/voice.gif)

## Get it

|  Package  |Latest Release|
|:----------|:------------:|
|**Xamarin-MaterialSearchView**|[![NuGet Badge Xamarin-MaterialSearchView](https://buildstats.info/nuget/Xamarin-MaterialSearchView)](https://www.nuget.org/packages/Xamarin-MaterialSearchView/)|

### **Basic example:**

**XML:**
**Layout:**

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
	android:background="@color/colorGray"
   android:layout_width="fill_parent"
   android:layout_height="fill_parent"
   android:orientation="vertical">
   <include layout="@layout/search_container" />
</LinearLayout>
```

**search_container.xml**

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<FrameLayout
	xmlns:android="http://schemas.android.com/apk/res/android"
	android:id="@+id/toolbar_container"
	android:layout_width="match_parent"
	android:layout_height="wrap_content">

	<android.support.v7.widget.Toolbar
		android:id="@+id/toolbar"
		android:layout_width="match_parent"
		android:layout_height="?attr/actionBarSize"
		android:background="@color/colorPrimary" />

	<com.miguelcatalan.materialsearchview.MaterialSearchView
		android:id="@+id/search_view"
		android:layout_width="match_parent"
		android:layout_height="wrap_content" />
</FrameLayout>
```

**Menu:**
**menu_search.xml**

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
	xmlns:app="http://schemas.android.com/apk/res-auto"
	xmlns:tools="http://schemas.android.com/tools"
	tools:context="com.domain.myApp.YourClassActivity">
	<item
		android:id="@+id/action_search"
		android:icon="@drawable/ic_action_action_search"
		android:orderInCategory="100"
		android:title="@string/search_title"
		app:showAsAction="always" />
</menu>
```

**C#:**

```csharp
public partial class YourClassActivity : AppCompatActivity
{
	private MaterialSearchView SearchView;
	protected override void OnCreate(Bundle savedInstanceState)
	{

		SearchView = FindViewById<MaterialSearchView>(Resource.Id.search_view);

		SearchView.SetOnQueryTextListener(new MaterialSearchViewListener(this));

		//Optional to enable voice search
		//SearchView.SetVoiceSearch(true);        
	}

	public override bool OnCreateOptionsMenu(IMenu menu)
	{
		MenuInflater.Inflate(Resource.Menu.menu_search, menu);

		SearchView.SetMenuItem(menu.FindItem(Resource.Id.action_search));

		return true;
	}
}

public partial class YourClassActivity
{
	public class MaterialSearchViewListener : Java.Lang.Object, MaterialSearchView.IOnQueryTextListener
	{
		public bool OnQueryTextChange(string p0)
		{
			return true;
		}

		public bool OnQueryTextSubmit(string p0)
		{
			return true;
		}
	}
}
```

# Help me
Pull requests are more than welcome, help me and others improve this awesome library.

The code is based in the Krishnakapil original concept.

# License
	Copyright 2015-2020 Miguel Catalan Bañuls and Federico Navarrete

	Licensed under the Apache License, Version 2.0 (the "License");
	you may not use this file except in compliance with the License.
	You may obtain a copy of the License at

		http://www.apache.org/licenses/LICENSE-2.0

	Unless required by applicable law or agreed to in writing, software
	distributed under the License is distributed on an "AS IS" BASIS,
	WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
	See the License for the specific language governing permissions and
	limitations under the License.
	

### Follow me at:

|  LinkedIn  |YouTube|Amazon|Goodreads|Instagram|Cyber Prophets|Sharing Your Stories|
|:----------|:------------:|:------------:|:------------:|:------------:|:------------:|:------------:|
|[![LinkedIn](https://i.stack.imgur.com/idQWu.png)](https://bit.ly/lfanmixco)|[![YouTube](https://i.stack.imgur.com/CFPMR.png)](https://youtube.com/c/FedericoNavarrete)|[![Amazon](https://i.stack.imgur.com/NFOeE.png)](https://www.amazon.com/Federico-Navarrete/e/B08NJTXQRV)|[![Goodreads](https://i.stack.imgur.com/oBk0g.jpg)](https://www.goodreads.com/author/show/21125413.Federico_Navarrete)|[![Instagram](https://i.stack.imgur.com/PIfqY.png)](https://www.instagram.com/federico_the_consultant)|[![RedCircle Podcast](https://i.stack.imgur.com/4XICF.png)](https://redcircle.com/shows/cyber-prophets)|[![RedCircle Podcast](https://i.stack.imgur.com/4XICF.png)](https://redcircle.com/shows/sharing-your-stories)|

