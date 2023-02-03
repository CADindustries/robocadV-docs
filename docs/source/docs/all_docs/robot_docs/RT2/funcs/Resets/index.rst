Обнуление
================================

Описание функций и примеры использования:

.. tabs::

	.. tab:: Python

		**Расположение и название:** RT2.reset_right_enc, RT2.reset_left_enc, RT2.reset_back_enc, RT2.reset_imu

		**Входные данные:**  

		*bool* - нужно ли обнулять

		**Выходные данные:**

		\-\-\-

		**Пример:**

		.. code-block:: python
			:linenos:

			# робот будет двигаться вперед 10 секунд, а потом обнулит правый энкодер
			from robocadSim.robots import RT2
			import time


			robot = RT2.RT2()

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

		**Расположение и название:** RT2.setResetRightEnc(), RT2.setResetLeftEnc(), RT2.setResetBackEnc(), RT2.setResetImu()

		**Входные данные:**  

		*boolean* - нужно ли обнулять

		**Выходные данные:**

		\-\-\-

		**Пример:**

		.. code-block:: java
			:linenos:

			// робот будет двигаться вперед 10 секунд, а потом обнулит правый энкодер
			import robots.RT2;

			public class Main
			{
				public static void main(String[] args) throws InterruptedException  //static method
				{
					RT2 robot = new RT2();
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

		**Расположение и название:** robocadSimLV -> robocadSim -> robots -> RT2 -> RT2

		**Входные данные:**  

		*bool* - нужно ли обнулять

		**Выходные данные:**

		\-\-\-

		**Пример:**

		В этом примере у робота просто постоянно обнуляются правый и левый энкодеры

		.. image:: labView/rt_2_resets.PNG
			:align: center
			:width: 800

		**Дополнительная информация:**

		\-\-\-