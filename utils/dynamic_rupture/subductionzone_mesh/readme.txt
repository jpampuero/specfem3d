To generate the subduction zone mesh for SPECFEM3D:

0. Include the path to cubit.py in your $PYTHONPATH environment variable.
   Modify the user parameters in file process_slab_rotate.py following the guidelines therein

1. In the linux shell, run:
     python process_slab_rotate.py
   This step creates a file called slab_rotate_before_loft.cub
   
2. Open the Trelis graphical user interface, then run create_chunks_mesh.jou
   This step creates a file called slab_rotate.cub
   If you have no easy access to the Trelis GUI, you can instead run in the linux shell:
     trelis -nographics -input ./create_chunks_mesh.jou

3. In the linux shell, run:
     python exportmesh.py
   This step creates the SPECFEM3D mesh files

Notes:
Python scripts have been tested with python 2.7, but 2.6 to 3.5 should also be fine.
Step 1 runs on the linux shell, but not directly in the Trelis window (the numpy and matplotlib modules cannot be found).
Type "sh run.sh" to run steps 1 to 3 automatically.
