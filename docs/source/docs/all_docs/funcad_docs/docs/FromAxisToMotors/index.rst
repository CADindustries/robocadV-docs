FromAxisToMotors
================================

FromAxisToMotors function is used to remake input axis values into motors values for **tricycle** robot.

.. tabs::

    .. tab:: Python

        **Location and name:** Funcad.fatm()

        **Inputs:**  

        - *float* speed to X axis
        - *float* speed to Y axis
        - *float* speed to Z axis

        **Output:**

        *tuple* that includes:

        - Speed to right motor
        - Speed to left motor
        - Speed to back motor

        **Example:**

        .. code-block:: python
            :linenos:

            from robocadSimPy.funcad import Funcad


            out = Funcad.fatm(5, -5, 3)  # (2.273672, -9.273672,  4.)
        
        **Additional info:**
        
        \-\-\-