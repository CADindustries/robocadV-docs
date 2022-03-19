Transfunction
================================

Transfunction function is used to rearrange input value.

.. tabs::

    .. tab:: Python

        **Location and name:** Funcad.transfunc_np()

        **Inputs:**  

	- *np.ndarray* 2d input/output array
        - *float* value to remake

        **Output:**

        *float* rearranged input

        **Example:**

        .. code-block:: python
            :linenos:

            from robocadSimPy.funcad import Funcad
	    import numpy as np


            out = Funcad.transfunc_np(np.array([[2, 10], [20, 100]]), 5)  # out will be 50
        
        **Additional info:**
        
        \-\-\-
