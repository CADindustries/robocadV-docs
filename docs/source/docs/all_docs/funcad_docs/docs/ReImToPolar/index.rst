ReImToPolar
================================

ReImToPolar function converts the rectangular components of a complex number into its polar components.

.. tabs::

    .. tab:: Python

        **Location and name:** Funcad.reim_to_polar()

        **Inputs:**  

        - *float* X value
        - *float* Y value

        **Output:**

        *tuple* that includes:

        - r value
        - theta value

        **Example:**

        .. code-block:: python
            :linenos:

            from robocadSimPy.funcad import Funcad


            out = Funcad.reim_to_polar(30, 20)  # (36.05551275463989, 0.5880026035475675)
        
        **Additional info:**
        
        \-\-\-
