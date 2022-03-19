FromMotorsToAxis
================================

FromMotorsToAxis function is used to remake input motors values into axis values for **tricycle** robot.

.. tabs::

    .. tab:: Python

        **Location and name:** Funcad.fmta()

        **Inputs:**  

        - *float* speed to right motor
        - *float* speed to left motor
        - *float* speed to back motor

        **Output:**

        *tuple* that includes:

        - Speed to X axis
        - Speed to Y axis
        - Speed to Z axis

        **Example:**

        .. code-block:: python
            :linenos:

            from robocadSimPy.funcad import Funcad


            out = Funcad.fmta(5, -5, 0)  # (8.66, 0., 0.)
        
        **Additional info:**
        
        \-\-\-
