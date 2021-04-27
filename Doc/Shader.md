## 渲染流水线
### 渲染流水线 
概念阶段之间的信息 应用阶段--几何阶段--光栅化阶段  
### CPU和GPU之间的通信
1.把数据加载到显存中   
2.设置渲染状态 (定义场景中的网格，使用哪个着色器，光源属性，材质)  
3.调用Draw Call  
### GPU流水线
1.顶点着色器：把顶点坐标从模型空间转换到齐次裁剪，通常再由硬件得到归一化的设备坐标（NDC）  
2.裁剪：完全在视野内，完全在视野外，部分在视野内  
3.屏幕映射：屏幕映射得到的屏幕坐标决定了这个顶点对应屏幕上那个像素以及距离这个像素有多远  
4.三角形设置：计算每个图元覆盖了那些像素，以及为这些像素计算它们的颜色  
5.三角形遍历：将会检查每个像素是否被一个三角形网格所覆盖，如果被覆盖的话就会生成一个片元  
6.片元着色器：输入是上一个阶段对顶点信息插值得到的结果，输出是一个或者多个颜色值（这一阶段最重要的技术是纹理采样）  
7.逐片元操作：模板测试--深度测试-- 混合  
### 一些容易困惑的地方
什么是OpenGL/DirectX  
什么是HLSL,GLSL,Cg  
什么是DrawCall  
什么是固定管线渲染  

