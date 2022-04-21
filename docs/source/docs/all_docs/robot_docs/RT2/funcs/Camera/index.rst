Camera
================================

Here is examples how to get camera image.

.. tabs::

    .. tab:: Python

        **Location and name:** RT2.bytes_from_camera

        **Inputs:**  

        \-\-\-

        **Output:**

        *bytes* of image from robot

        **OpenCV example:**

        .. code-block:: python
            :linenos:

	    	# this code will show you real time image from robot camera for 10 seconds
            from robocadSimPy.robots import RT2
	    	import numpy as np
	    	import cv2


            robot = RT2.RT2()
	    	robot.connect()
            st_time = time.time()

			while time.time() - st_time < 10:
				nparr = np.frombuffer(robot.bytes_from_camera, np.uint8)
				if nparr.size > 0:
					img_rgb = nparr.reshape(480, 640, 3)
					img_bgr = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2BGR)

					cv2.imshow("robot image", img_bgr)
					cv2.waitKey(1)
			robot.disconnect()

        **PIL example:**

        .. code-block:: python
            :linenos:

			# this code will save image from robot camera
			from robocadSimPy.robots import RT2
			import numpy as np
			from PIL import Image


			robot = RT2.RT2()
			robot.connect()

			while len(robot.bytes_from_camera) == 0:
				pass

			img = Image.frombytes("RGB", (640, 480), robot.bytes_from_camera)
			img.save(r"image_from_robot.png", "PNG")
			robot.disconnect()
        
        **Additional info:**
        
        \-\-\-

    .. tab:: Java

        **Location and name:** RT2.getBytesFromCamera()

        **Inputs:**  

        \-\-\-

        **Output:**

        *byte[]* of image from robot

        **awt/swing example:**

        .. code-block:: java
            :linenos:

	    	# this code will show you real time image from robot camera for 10 seconds
        	import robots.RT2;

			import javax.swing.*;
			import java.awt.*;
			import java.awt.image.BufferedImage;

			public class Main
			{
				public static void main(String[] args)  //static method
				{
					JFrame jFrame = new JFrame();
					JPanel panel = new JPanel();

					jFrame.setLayout(new FlowLayout());

					jFrame.setSize(640, 480);
					panel.setSize(640, 480);
					JLabel jLabel = new JLabel();

					panel.add(jLabel);
					jFrame.add(panel);
					panel.setVisible(true);
					jFrame.setVisible(true);

					jFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

					RT2 robot = new RT2();
					robot.connect();

					long stTime = System.currentTimeMillis();

					BufferedImage icon = new BufferedImage(1, 1, BufferedImage.TYPE_3BYTE_BGR);

					while (System.currentTimeMillis() - stTime < 10000)
					{
						if (robot.getBytesFromCamera().length > 0)
							icon = Converter(robot.getBytesFromCamera());
						jLabel.setIcon(new ImageIcon(icon));
						jFrame.repaint();
					}

					jFrame.setVisible(false);
					jFrame.dispose();

					robot.disconnect();
				}

				private static BufferedImage Converter(byte[] array)
				{
					int height = 480;
					int width = 640;
					
					BufferedImage newImage = new BufferedImage(width, height, BufferedImage.TYPE_3BYTE_BGR);
					int ctr=0;

					for(int i = height - 1; i >= 0; i--)
					{
						for(int j = 0; j < width; j++)
						{
							Color color = new Color(array[ctr] & 0xff, array[ctr + 1] & 0xff, array[ctr + 2] & 0xff);
							newImage.setRGB(j, i, color.getRGB());
							ctr += 3;
						}

					}
					return newImage;
				}
			}

        **JavaCV example:**

        .. code-block:: python
            :linenos:

	    
        
        **Additional info:**
        
        \-\-\-
