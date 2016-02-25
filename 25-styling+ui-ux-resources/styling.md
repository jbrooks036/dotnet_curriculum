# Styling
* ?? this whole file needs to be reviewed ??

#### 1) Think about how to manage it all...  then start modifying:
* `_Layout.cshtml`
 * `@Styles.Render` ("~/Content/css") [??]
 * `BundleConfig`
 * new StyleBundle (`~/Content/css`)
	 * where `~` is `<ProjectName>`
* `_<Project>Layout`
 * add in lines from `_Layout`
 * and make Bundles to include files
 * screen width to start playing with:  960 is good, or 1024.

#### 2) Rebuild and try to run
#### 3) Login/Register
#### 4) While running, modify Views.
* Take elements of `_Layout` and put in `_ProjectNameLayout`
* Create simple classes inside `main.css`, to serve as visual guides

## Special Features

#### Custom Assets
 * Contained inside `Content` folder, already bootstrap-ready
 * Add `Custom.js`, `Main.css`, to get them included in app source
 * `App_Start/BundleConfig` concatenates assets and makes it possible to reference them

#### Cursor Hover-Over Effect
 * Mouse-enter over padding for anchor
 * Cursor needs to change during hover
 * Fade in - to soften effect

#### Accessibility
* `WAI-ARIA` Library - **USE IT!!**

#### AngularJS [?? these notes need special help!!]
* In Solution Explorer, click on main project > NuGet PkgMgr > Add angularjs
* Put assets for Angular inside `_ProjectNameLayout`
* Add script tag
* Add script bundle
* [??] app.js
