This is the Windows binary release of the Pinocchio library.  The full
technical description is given in Ilya Baran and Jovan Popovic,
"Automatic Rigging and Animation of 3D Characters," SIGGRAPH 2007.
The source can be found at http://www.mit.edu/~ibaran/autorig/code.html

-------
RUNNING
-------

First try running with the given objects:
DemoUI data/test.obj -motion data/walk.txt

After about 10 seconds, a window should open and a guy should walk
around in it.

In the window, use the left mouse button to pan, wheel to zoom, and
right mouse button to rotate the view.  Pressing S toggles the skeleton
display, F toggles flat shading, G toggles ground display, and T resets
the view.

Then try using your own meshes--make sure they are nice, closed, and
connected.  Igarashi's Teddy (and Fibermesh) can easily produce such
obj files.  Pinocchio can also read text files in .off, .ply and .stl
formats.

If the mesh is not oriented correctly (should be upright and facing
you), the "-rot x y z degrees" option lets you apply rotations.
Running with the -mo option only displays the mesh and doesn't
do any analysis.

When DemoUI runs, it also outputs the embedded skeleton to
skeleton.out and the attachment (bone weights) to attachment.out.
Each line in skeleton.out corresponds to a joint and is of the form:
idx x y z prev
where prev is the index of the previous joint.
Each line in attachment.out corresponds to a mesh vertex and
consists of bone weights for each bone in the order of skeleton
joints (see HumanSkeleton in Pinocchio/skeleton.cpp).

If you want to provide your own skeleton, use the "-skel file" where
file is in the format described above.  For annotations, you'll have
to modify the skeleton.cpp file to build the skeleton
programmatically.  If the skeleton has already been embedded, and
you just want Pinocchio to generate bone weights, use the -nofit
option.
