Моторы
================================

Описание функций и примеры использования:

.. tabs::

	.. tab:: Python

		**Расположение и название:** RT1.right_motor_speed, RT1.left_motor_speed, RT1.back_motor_speed

		**Входные данные:**  

		*float* - скорость на мотор

		**Выходные данные:**

		\-\-\-

		**Пример:**

		.. code-block:: python
			:linenos:

			# робот будет двигаться вперед в течение 10 секунд
			from robocadSim.robots import RT1
			import time


			robot = RT1.RT1()

			robot.connect()

			robot.right_motor_speed = -10
			robot.left_motor_speed = 10

			time.sleep(10)

			robot.right_motor_speed = 0
			robot.left_motor_speed = 0

			time.sleep(0.1)

			robot.disconnect()

        
		**Дополнительная информация:**

		- Минимальная скорость - -100, максимальная - 100

	.. tab:: Java

		**Расположение и название:** RT1.setRightMotorSpeed(), RT1.setLeftMotorSpeed(), RT1.setBackMotorSpeed()

		**Входные данные:**  

		*float* - скорость на мотор

		**Выходные данные:**

		\-\-\-

		**Пример:**

		.. code-block:: java
			:linenos:

			// робот будет двигаться вперед в течение 10 секунд
			import robots.RT1;

			public class Main
			{
				public static void main(String[] args) throws InterruptedException  //static method
				{
					RT1 robot = new RT1();
					robot.connect();

					robot.setRightMotorSpeed(-10);
					robot.setLeftMotorSpeed(10);

					Thread.sleep(10000);

					robot.setRightMotorSpeed(0);
					robot.setLeftMotorSpeed(0);

					Thread.sleep(100);

					robot.disconnect();
				}
			}

		**Дополнительная информация:**

		- Минимальная скорость - -100, максимальная - 100

	.. tab:: LabVIEW

		**Расположение и название:** robocadSimLV -> robocadSim -> robots -> RT1 -> RT1

		**Входные данные:**  

		*float* - скорость на мотор

		**Выходные данные:**

		\-\-\-

		**Пример:**

		В этом примере робот просто постоянно едет вперед

		.. image:: labView/rt_1_motors.PNG
			:align: center
			:width: 800

		**Дополнительная информация:**

		- Минимальная скорость - -100, максимальная - 100