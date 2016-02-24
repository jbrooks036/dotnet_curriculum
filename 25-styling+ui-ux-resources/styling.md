# Styling
* ?? this whole file needs some serious review ??

### How to include custom assets in my project?
 * Contained inside `Content` folder, already bootstrap-ready
 * Add `Custom.js`, `Main.css`, to get them included in app source
 * `App_Start/BundleConfig` : concatenates assets and makes it possible to reference them

### Think about how to manage it all
* `_Layout.cshtml`
* `@Styles.Render` ("~/Content/css") [??]
* `BundleConfig`
  * new StyleBundle (`~/Content/css`)
	 * where `~` is `<ProjectName>`
* `_<Project>Layout`
 * add in lines from `_Layout`
 * and make Bundles to include files
* Rebuild and try to run
* Login/Register
* [Screen width to start playing with:  960 is good, or 1024.]
* While running, modify Views.
* Take elements of `_Layout` and put in `_ProjectNameLayout`
* Create simple classes inside `main.css`, to serve as visual guides

#### Hover-Over
* Mouse-enter over padding for anchor
* Cursor needs to change during hover
* Fade in - to soften effect
* `WAI-ARIA` library  (use it!)
