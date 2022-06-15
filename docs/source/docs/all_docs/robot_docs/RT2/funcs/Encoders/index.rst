Энкодеры
================================

Описание функций и примеры использования:

.. tabs::

	.. tab:: Python

		**Расположение и название:** RT2.right_motor_enc, RT2.left_motor_enc, RT2.back_motor_enc

		**Входные данные:**  

		\-\-\-

		**Выходные данные:**

		*float* - значение энкодера (тик)

		**Пример с использованием библиотеки OpenCV:**

		.. code-block:: python
			:linenos:

			# робот будет двигаться вперед, пока не насчитает по правому энкодеру 3000
			from robocadSim.robots import RT2
			import time


			robot = RT2.RT2()

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

		**Расположение и название:** RT2.getRightMotorEnc(), RT2.getLeftMotorEnc(), RT2.getBackMotorEnc()

		**Входные данные:**  

		\-\-\-

		**Выходные данные:**

		*float* - значение энкодера (тик)

		**Пример:**

		.. code-block:: java
			:linenos:

			// робот будет двигаться вперед, пока не насчитает по правому энкодеру 3000
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
