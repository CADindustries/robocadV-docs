InRangeBool
================================

Функция InRangeBool проверяет, входит ли значение в заданный промежуток.

.. tabs::

    .. tab:: Python

        **Раположение и название:** Funcad.in_range_bool()

        **Входные данные:**  

        - *float* входное значение
        - *float* нижняя граница
        - *float* верхняя граница

        **Выходные данные:**

        *bool* входит ли заданное значение в промежуток

        **Пример:**

        .. code-block:: python
            :linenos:

            from robocadSimPy.funcad import Funcad


            out = Funcad.in_range_bool(5, 0, 12)  # выходные данные - True
        
        **Дополнительная информация:**
        
        \-\-\-
