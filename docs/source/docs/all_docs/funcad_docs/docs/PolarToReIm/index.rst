PolarToReIm
================================

PolarToReIm function converts the polar components of a complex number into its rectangular components.

.. tabs::

    .. tab:: Python

        **Location and name:** Funcad.polar_to_reim()

        **Inputs:**  

        - *float* r value
        - *float* theta value

        **Output:**

        *tuple* that includes:

        - X value
        - Y value

        **Example:**

        .. code-block:: python
            :linenos:

            from robocadSimPy.funcad import Funcad


            out = Funcad.polar_to_reim(30, 20)  # (12.242461854401759, 27.38835752182883)
        
        **Additional info:**
        
        \-\-\-
