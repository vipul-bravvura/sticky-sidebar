# Sticky Sidebar ES5 
## IE 11 Support

## Install

#### NPM

If you are using NPM as package manager:

````
npm install sticky-sidebar-es5
````

## Usage

Your website's html structure has to be similar to this in order to work:

````html
<div class="main-content">
    <div class="sidebar">
        <div class="sidebar__inner">
            <!-- Content goes here -->
        </div>
    </div>
    <div class="content">
        <!-- Content goes here -->
    </div>
</div>
````

Note that inner sidebar wrapper ``.sidebar__innner`` is optional but highly recommended, if you don't write it yourself, the script will create one for you under class name ``inner-wrapper-sticky``. but this may cause many problems.

For the above example, you can use the following JavaScript:

````html
<script type="text/javascript" src="./js/sticky-sidebar.js"></script>

<script type="text/javascript">
  var sidebar = new StickySidebar('.sidebar', {
    topSpacing: 20,
    bottomSpacing: 20,
    containerSelector: '.main-content',
    innerWrapperSelector: '.sidebar__inner'
  });
</script>
````

#### Via jQuery/Zepto

You can configure sticky sidebar as a jQuery plugin, just include ``jquery.sticky-sidebar.js`` instead ``sticky-sidebar.js`` file than configure it as any jQuery plugin.

````html
<script type="text/javascript" src="./js/jquery.js"></script>
<script type="text/javascript" src="./js/jquery.sticky-sidebar.js"></script>

<script type="text/javascript">
  $('#sidebar').stickySidebar({
    topSpacing: 60,
    bottomSpacing: 60
  });
</script>
````

Make sure to include ``sticky-sidebar.js`` script file after ``jquery.js``.

## Usage with [ResizeSensor.js](https://github.com/marcj/css-element-queries/blob/master/src/ResizeSensor.js)

Sticky sidebar integrated with [ResizeSensor.js](https://github.com/marcj/css-element-queries/blob/master/src/ResizeSensor.js) to detect when sidebar or container is changed. To use resize sensor with this plugin just make sure to include ResizeSensor.js before `sticky-sidebar.js` code whether through module loader, bundle or event inclusion as a `<script>` and enable `resizeSensor` option (enabled by default) and it will works.

You can choose not to include `ResizeSensor.js` and sticky sidebar will continue work without any problem but without automatically detect resize changes.

## Browser Support

Sticky sidebar works in all modern browsers including Internet Explorer 9 and above, but if you want it to work with IE9, should include [`requestAnimationFrame`](https://gist.github.com/paulirish/1579671) polyfill before sticky sidebar code.

If you have any issues with browser compatibility don’t hesitate to [Submit an issue](https://github.com/abouolia/sticky-sidebar/issues/new).

 