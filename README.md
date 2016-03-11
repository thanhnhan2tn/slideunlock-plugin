# jquery-slideunlock-plugin

## html
```html
<div id="slide-wrapper">
    <input type="hidden" value="" id="lockable"/>
    <div id="slider">
        <span id="label"></span>
        <span id="lableTip">Slide to confirm I am human!</span>
    </div>
</div>
```

## css
```css
#slide-wrapper{
    width: 360px;
    position: relative;
    padding: 50px;
    background: #ECF0F1;
    margin: 0 auto;
}
#slider{
    padding:20px;
    position: relative;
    border-radius: 2px;
    background-color: #FDEB9C;
    overflow: hidden;
    text-align: center;
}
#slider.success{
    background-color: #E5EE9F;
}
#label{
    width: 40px;
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    background: #E67E22;
    z-index: 999;
    cursor: pointer;
}
#labelTip{
    z-index: 9;
}
```

## JavaScript
depend on jQuery
```javascript
<script type="text/javascript" src="js/jquery.min.js"></script>
<script type="text/javascript" src="js/jquery.slideunlock.min.js"></script>
<script type="text/javascript">
    $(function () {
        var slider = new SliderUnlock("#slider", {
            labelTip: "滑动解锁",
            successLabelTip: "解锁成功",
            duration: 200   // 动画效果执行时间，默认200ms
        }, function(){
            alert('success');
        }, function(){
            $(".warn").text("index:" + slider.index + "， max:" + slider.max + ",lableIndex:" + slider.lableIndex + ",value:" + $("#lockable").val() + " date:" + new Date().getUTCDate());
        });
        slider.init();

        $("#reset-btn").on('click', function(){
            slider.reset();
        });
    })
</script>
```

```
var slider = new SliderUnlock(element, options, success, always);
slider.init();
```

## Demo
<p data-height="268" data-theme-id="0" data-slug-hash="bpeoEp" data-default-tab="result" data-user="ArronYR" class="codepen">See the Pen <a href="http://codepen.io/ArronYR/pen/bpeoEp/">jquery-slide-unlock</a> by Arron.y (<a href="http://codepen.io/ArronYR">@ArronYR</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>