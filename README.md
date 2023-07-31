# cs228-linear-mnist-classifier
Formatting the data:Your goal will be building a linear classifier for MNIST. Towards this goal, we need to format the data to obtain a 
dataset S = (xi, yi)N=50,000i=1.
Input: Each input xis a 28 ×28 matrix. Convert inputs x to vectors of size 784.•
Output:Each labelyis a digit from 0 to 9. 
Apply one-hot encoding onyand convert it to a vectoryoh of size 10. 
For instance,y=5maps to yoh =[000001000]
Linear classifier:Our goal is learning a matrixW∈R10×784so that given an inputx,f(x)=W x will correctly predict the associated labely. 
The labelˆyoutput byfis the location of the largest entry offi.e.ˆyi=arg max0≤i≤9fi(x)Hence, the test accuracy is given by acc(W)=P(y=ˆy).Training:You will use quadratic loss and gradient descent for training. The training loss function atithexample (xi, yi)isLi(W)=12∥yi−W xi∥2ℓ2.For training, you will use minibatch stochastic gradient descent (SGD). SGD has three parameters:• Number of iterations ITR• a batch size Bwhere N=50,000 ≥B≥1.• a learning rate η>0.SGD algorithm is as follows:
Initialize: W0=0for 1≤t≤ITR ∶(i)select Bnumbers (ri)Bi=1from {1,2,...,N}uniformly at random (with replacement)(ii)calculate the gradient G=1BB∑i=1∇Lri(W).(iii)Wt=Wt−1−ηG.Return WFINAL =WITR.
