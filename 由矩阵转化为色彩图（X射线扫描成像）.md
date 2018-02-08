n = 30;
mat1 = Table[Range[n], n];
For[i = 1, i <= n, i++, 
  For[j = 1, j <= n, j++, mat1[[i, j]] = RandomReal[]]];
mat2 = mat1;
For[i = 1, i <= n, i++, 
  For[j = 1, j <= n, j++, color = Hue[mat1[[i, j]]/1]; 
   mat2[[i, j]] = 
    Graphics[{color,Rectangle[]}, 
     ImageSize -> {10, 10}, Background -> color]]];
GraphicsGrid[mat2, ImageSize -> {800, 800}, Spacings -> 0]
(*因为没有实际的传感器数据，故此段程序首先产生了一个n阶矩阵。然后将矩阵中各元素的数值转化为对应颜色的小正方形，再将各正方形无缝拼贴成图像。对于类似于处理微传感器阵的数据，非常方便*)

![彩图](https://github.com/dadiancjw/julia-dream/blob/master/p.jpg)
