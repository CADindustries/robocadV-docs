Энкодеры
================================

Описание функций и примеры использования:

.. tabs::

	.. tab:: Python

		**Расположение и название:** RT1.right_motor_enc, RT1.left_motor_enc, RT1.back_motor_enc

		**Входные данные:**  

		\-\-\-

		**Выходные данные:**

		*float* - значение энкодера (тик)

		**Пример:**

		.. code-block:: python
			:linenos:

			# робот будет двигаться вперед, пока не насчитает по правому энкодеру 3000
			from robocadSim.robots import RT1
			import time


			robot = RT1.RT1()

			robot.connect()

			robot.right_motor_speed = -10
			robot.left_motor_speed = 10

			time.sleep(0.1)

			while abs(robot.right_motor_enc) < 3000:
				pass

			robot.right_motor_speed = 0
			robot.left_motor_speed = 0

			time.sleep(0.1)

			robot.disconnect()

        
		**Дополнительная информация:**

		- Это бета версия работы энкодеров

	.. tab:: Java

		**Расположение и название:** RT1.getRightMotorEnc(), RT1.getLeftMotorEnc(), RT1.getBackMotorEnc()

		**Входные данные:**  

		\-\-\-

		**Выходные данные:**

		*float* - значение энкодера (тик)

		**Пример:**

		.. code-block:: java
			:linenos:

			// робот будет двигаться вперед, пока не насчитает по правому энкодеру 3000
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

					while (Math.abs(robot.getRightMotorEnc()) < 3000)
					{

					}

					robot.setRightMotorSpeed(0);
					robot.setLeftMotorSpeed(0);

					Thread.sleep(100);

					robot.disconnect();
				}
			}

		**Дополнительная информация:**

		- Это бета версия работы энкодеров

	.. tab:: LabVIEW

		**Расположение и название:** robocadSimLV -> robocadSim -> robots -> RT1 -> RT1

		**Входные данные:**  

		\-\-\-

		**Выходные данные:**

		*float* - значение энкодера (тик)

		**Пример:**

		В этом примере робот просто постоянно едет вперед и выводит на фронт панель значение правого энкодера

		.. image:: labView/rt_1_encs.PNG
			:align: center
			:width: 800

		**Дополнительная информация:**

		- Это бета версия работы энкодеров
