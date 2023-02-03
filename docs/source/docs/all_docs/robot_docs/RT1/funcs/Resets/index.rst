Обнуление
================================

Описание функций и примеры использования:

.. tabs::

	.. tab:: Python

		**Расположение и название:** RT1.reset_right_enc, RT1.reset_left_enc, RT1.reset_back_enc, RT1.reset_imu

		**Входные данные:**  

		*bool* - нужно ли обнулять

		**Выходные данные:**

		\-\-\-

		**Пример:**

		.. code-block:: python
			:linenos:

			# робот будет двигаться вперед 10 секунд, а потом обнулит правый энкодер
			from robocadSim.robots import RT1
			import time


			robot = RT1.RT1()

			robot.connect()

			robot.right_motor_speed = -10
			robot.left_motor_speed = 10

			time.sleep(10)

			print(robot.right_motor_enc)  # -5560.0

			robot.reset_right_enc = True

			robot.right_motor_speed = 0
			robot.left_motor_speed = 0

			time.sleep(0.1)

			print(robot.right_motor_enc)  # 0.0

			robot.reset_right_enc = False

			robot.disconnect()

        
		**Дополнительная информация:**

		\-\-\-

	.. tab:: Java

		**Расположение и название:** RT1.setResetRightEnc(), RT1.setResetLeftEnc(), RT1.setResetBackEnc(), RT1.setResetImu()

		**Входные данные:**  

		*boolean* - нужно ли обнулять

		**Выходные данные:**

		\-\-\-

		**Пример:**

		.. code-block:: java
			:linenos:

			// робот будет двигаться вперед 10 секунд, а потом обнулит правый энкодер
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

					System.out.println(robot.getRightMotorEnc());  // -5560.0

					robot.setResetRightEnc(true);

					robot.setRightMotorSpeed(0);
					robot.setLeftMotorSpeed(0);

					Thread.sleep(100);

					System.out.println(robot.getRightMotorEnc());  // 0.0

					robot.setResetRightEnc(false);

					robot.disconnect();
				}
			}

		**Дополнительная информация:**

		\-\-\-

	.. tab:: LabVIEW

		**Расположение и название:** robocadSimLV -> robocadSim -> robots -> RT1 -> RT1

		**Входные данные:**  

		*bool* - нужно ли обнулять

		**Выходные данные:**

		\-\-\-

		**Пример:**

		В этом примере у робота просто постоянно обнуляются правый и левый энкодеры

		.. image:: labView/rt_1_resets.PNG
			:align: center
			:width: 800

		**Дополнительная информация:**

		\-\-\-