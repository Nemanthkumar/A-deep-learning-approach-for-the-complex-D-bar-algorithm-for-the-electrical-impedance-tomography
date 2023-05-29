# A-deep-learning-approach-for-the-complex-D-bar-algorithm-for-the-electrical-impedance-tomography
Steps involved in the Neural network:

Final data collection.mlx

1. For the data collection, the data is taken with the background admittivity as the blood and the target as the tissues which is the additive value of the blood admittivity.
2. conductance is taken as the conductivity value which is taken from the italian national research council and the susceptance is derived as

we are only involving only the capacitor as the human body is equivalent to the combination of resistance and capacitance
I = C dV/dt
to convert to frequency domain of the time domain representation of the signal, the equation is written as
I = C V.w, where w is frequency
I/V = epsilon.w , where epsilon - permittivity 
G = epsilon.w -->(1)

we know that,
B/G = tan(delta), where tan(delta) - loss tangent

from the (1), we can write B = sigma.epsilon.w.tan(delta) 

Refer the values of the conductance and susceptance from the thesis.

Saving data.mlx

Now the data is collected from which we are taking the "scattering transform output" which is 4 channel(2 complex matrix, so real and imagingary is splitted to 2 channels, so totally 4 channel) as the input of the neural network and the output is the ideal expected output which is of 2 channel(Conductance and Susceptance).

Jupyter notebook file:

The i/p data and the o/p data which we obtained is normalised to the scale of 0-1 and fed to the convolutional neural network and it is trained with the cross validation technique to
prevent overfitting of the network.

Evaluation performance:

Data is collected where the ellipse is placed at the center and moved towards the right slowly and this kind of data is generated.
We seperate the target and the background and we see how much it is deviated from the original data.
so we seperate the target for the ideal data, dbar and the neural network reconstructed data as well.
we find the amplitude response, ringing for both the real and imaginary reconstructed images.

I was quite confused with the evaluation technique and I don't know how to compare with the ideal image. So, in the file most_final.ipynb, I found the absolute mean between the ideal data amplitude response and ringing and in the finalest, I have done the division of the reconstructed data with the original data.

Noise data analysis:

We collect the data by infusing noise at different levels from 200 db and we see how the reconstruction occurs visually in both d-bar and the neural network reconstruction.
