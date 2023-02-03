Сенсоры
================================

Описание функций и примеры использования:

.. tabs::

	.. tab:: Python

		**Расположение и название:** RT1.left_ir, RT1.right_ir, RT1.left_us, RT1.right_us, RT1.imu

		**Входные данные:**  

		\-\-\-

		**Выходные данные:**

		*float* - значение датчика (см. или градус)

		**Пример:**

		.. code-block:: python
			:linenos:

			# робот будет двигаться вперед, пока стенка не будет слишком близко
			from robocadSim.robots import RT1
			import time


			robot = RT1.RT1()

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

		**Расположение и название:** RT1.getLeftIR(), RT1.getRightIR(), RT1.getLeftUS(), RT1.getRightUS(), RT1.getIMU()

		**Входные данные:**  

		\-\-\-

		**Выходные данные:**

		*float* - значение датчика (см. или градус)

		**Пример:**

		.. code-block:: java
			:linenos:

			// робот будет двигаться вперед, пока стенка не будет слишком близко
			import robots.RT1;

			public class Main
			{
				public static void main(String[] args) throws InterruptedException  //static method
				{
					RT1 robot = new RT1();
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

	.. tab:: LabVIEW

		**Расположение и название:** robocadSimLV -> robocadSim -> robots -> RT1 -> RT1

		**Входные данные:**  

		\-\-\-

		**Выходные данные:**

		*float* - значение датчика (см. или градус)

		**Пример:**

		В этом примере робот просто постоянно едет вперед и выводит на фронт панель значение правого инфракрасного датчика

		.. image:: labView/rt_1_sensors.PNG
			:align: center
			:width: 800

		**Дополнительная информация:**

		- Максимальная видимость ИК датчика - 40 см.
		- Максимальная видимость УЗ датчика - 100 см.
		- Минимальный угол поворота - -180, максимальный - 180
