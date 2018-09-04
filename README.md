# blender-examples

Sample creations and notes for blender usage. This was done following the course at 
udemy [Learn 3D Modelling - The Complete Blender Creator Course](https://www.udemy.com/blendertutorial/)
by Ben Tristem, Michael Bridges, GameDev.tv by Ben Tristem


# GPU Rendering issue on MacBook Pro

Running rendering using Cycles Renderer on GPU compute just hangs.  In Process monitor, a process called 
"CVMCompiler" just spins up with 100% CPU.  In online forums, someone say if this process is running means
OS is falling back to software rendering.  This takes quite a time and never completes.  I had to kill blender
and CVM compiler.

But the following helped.

Macbook Pro 2016 model comes with two GPUs "Intel HD Graphics 530" and "AMD Radeon Pro 450". The later has only 2 GB and 
the former has only 1 GB. 

1. User preference -> System select "OpenCL" and unselect "Intel HD Graphcis" and only keep "Radeon Pro"
2. In same page, under OpenGL -> Selection keep "OpenGL Select" 

Now cycles render with GPU compute works
