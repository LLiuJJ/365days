## 3DPhotoWall_CSS3

使用CSS的transform以及perspective等新属性，实现3D照片墙效果

### zoom属性
是IE浏览器的专属属性，Firefox等浏览器不支持，它可以设置或检索对象的缩放比例。

### backface-visibility
设置被旋转的元素的背面是否是可见的。

### filter:blur(10px)
filter是CSS3的滤镜属性，blur表示模糊滤镜。

### transform-style
需要设置在父元素上，preserve-3d表示该元素的所有子元素位于3D空间中。flat表示所有子元素都将被平展到该元素（父元素）的2D平面中进行呈现，注意这里的平展到父元素的2D平面中呈现，表示的是当父元素rotateY的时候看
不见子元素的3D呈现效果，而preserve-3d可以看见这种3D效果。
正方体中：除了前面，其他的面都是先rotate了再translateZ的，顺序不同效果也会不同，比如top面，是先rotateX了90度，然后再translateZ了一段距离，这里的translateZ是这个面已经rotateX(90deg)以后的坐标中translateZ的，而不是在开始的状态下为坐标translateZ的，这点很重要，所以在3D效果中
，顺序很重要。
### perspective
元素添加该属性表示其子元素会获得透视效果，如果设置元素自身的透视效果就设置该元素的transform:perspective()属性。
元素旋转过来时没有透视也会呈现3D效果（父元素设置transform-style:preserve-3d;属性），但是父元素不设置perspective属性的话就不存在景深效果。
所以preserve-3d用来设置子元素在父元素空间的3D效果，而perspective用来设置子元素在父元素中的景深效果。
### perspective-origin
同样设置在父元素上，用来选择视角的位置。

[demo展示](https://yy709593266.github.io/3DPhotoWall_CSS3/)
