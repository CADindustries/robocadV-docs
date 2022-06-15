Сенсоры
================================

Описание функций и примеры использования:

.. tabs::

	.. tab:: Python

		**Расположение и название:** RT2.left_ir, RT2.right_ir, RT2.left_us, RT2.right_us, RT2.imu

		**Входные данные:**  

		\-\-\-

		**Выходные данные:**

		*float* - значение датчика (см. или градус)

		**Пример с использованием библиотеки OpenCV:**

		.. code-block:: python
			:linenos:

			# робот будет двигаться вперед, пока стенка не будет слишком близко
			from robocadSim.robots import RT2
			import time


			robot = RT2.RT2()

			robot.connect()

			robot.right_motor_speed = -10
			robot.left_motor_speed = 10

			time.sleep(0.1)

			while robot.left_ir > 20:
				pass

			robot.right_motor_speed = 0
			robot.left_motor_speed = 0

			time.sleep(0.1)

			robot.disconnect()

        
		**Дополнительная информация:**

		- Максимальная видимость ИК датчика - 40 см.
		- Максимальная видимость УЗ датчика - 100 см.
		- Минимальный угол поворота - -180, максимальный - 180

	.. tab:: Java

		**Расположение и название:** RT2.getLeftIR(), RT2.getRightIR(), RT2.getLeftUS(), RT2.getRightUS(), RT2.getIMU()

		**Входные данные:**  

		\-\-\-

		**Выходные данные:**

		*float* - значение датчика (см. или градус)

		**Пример:**

		.. code-block:: java
			:linenos:

			// робот будет двигаться вперед, пока стенка не будет слишком близко
			import robots.RT2;

			public class Main
			{
				public static void main(String[] args) throws InterruptedException  //static method
				{
					RT2 robot = new RT2();
					robot.connect();

					robot.setRightMotorSpeed(-10);
					robot.setLeftMotorSpeed(10);

					Thread.sleep(100);

					while (robot.getLeftIR() > 20)
					{

					}
					
					robot.setRightMotorSpeed(0);
					robot.setLeftMotorSpeed(0);

					Thread.sleep(100);

					robot.disconnect();
				}
			}

		**Дополнительная информация:**

		- Максимальная видимость ИК датчика - 40 см.
		- Максимальная видимость УЗ датчика - 100 см.
		- Минимальный угол поворота - -180, максимальный - 180
