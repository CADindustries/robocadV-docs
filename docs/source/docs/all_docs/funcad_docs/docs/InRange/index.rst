InRange
================================

InRange function is used to clip input value by range.

.. tabs::

    .. tab:: Python

        **Location and name:** Funcad.in_range()

        **Inputs:**  

        - *float* input value
        - *float* lower threshold
        - *float* upper threshold

        **Output:**

        *float* ranged value

        **Example:**

        .. code-block:: python
            :linenos:

            from robocadSimPy.funcad import Funcad


            out = Funcad.in_range(5, 0, 12)  # 5
        
        **Additional info:**
        
        \-\-\-
