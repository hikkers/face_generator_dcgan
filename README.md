# DCGAN Face Generator

В данном ноутбуке содержится имплементация Generative adversarial network (GAN) с использованием Pytroch. Данный GAN был обучен на датасете лиц людей [Flickr Faces](https://github.com/NVlabs/ffhq-dataset), который содержит изображения лиц людей в высоком разрешении (1024х1024). В нашем датасете 3143 изображения.

<p>
<img src="assets/dataset_batch.png" align="middle">
</p>

## DCGAN
<p>
<img src="assets/GAN.png" align="middle">
</p>

DCGAN состоит из генератора и дискриминатора.
Архитектура дискриминатора:
<br>
**Conv2d > BatchNorm2d > LeakyReLU**
<br>

Архитектура генератора:
<br>
**TransposeConv2d > BatchNorm2d > LeakyReLU** и **nn.Tanh** на выходном слое.
<br>

## Обучение
Визуализация процесса обучения модели на датасете из 3143 картинок:

<p>
<img src="assets/training.gif" align="middle">
</p>

Гиперпараметры использованные в обучении:
	
	image_size = 64
	batch_size = 64
	lr_d = 0.0002 # discriminator learning rate
	lr_g = 0.0002 # generator learning rate
	epochs = 150 # number of epochs
	latent_size = 128 # size of the latent space
	latent_shape = 1 # latent shape

## Результаты

Cгенерированные изображения после 150 эпох:

<p>
<img src="assets/generated-images-0150.png" align="middle">
</p>

Сэмплирование генератора. На вход подаются векторы из нормального распределения:

<p>
<img src="assets/gen_sampling.png" align="middle">
</p>
