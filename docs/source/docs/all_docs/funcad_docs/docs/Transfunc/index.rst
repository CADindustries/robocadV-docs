Transfunction
================================

Функция Transfunction преобразует входное значение в зависимости от заданных массивов.

.. tabs::

    .. tab:: Python

        **Раположение и название:** Funcad.transfunc_np()

        **Входные данные:**  

	- *np.ndarray* двумерный массив входных и выходных данных
        - *float* значение для преобразования

        **Выходные данные:**

        *float* преобразованное значение

        **Пример:**

        .. code-block:: python
            :linenos:

            from robocadSimPy.funcad import Funcad
	    import numpy as np


            out = Funcad.transfunc_np(np.array([[2, 10], [20, 100]]), 5)  # выходные данные - 50
        
        **Дополнительная информация:**
        
        \-\-\-
