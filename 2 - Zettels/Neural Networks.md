
### Background 

Neural networks in computer systems are systems designed to mimic the structure of human brain . A neural network consists of neurons that are inter connected to each other like neural cells and collectively influence decision making . Neural networks are widely used in modern day use cases such as image recognition, speech recognition etc. 

### How neural networks function  

- Neruons can be assumed something as plain as an entity holding value .
- The neurons are structured in layers . The first layer is the layer that receives input while the last layer is where we see the outcome . All the layers in the middle is where the magic happens .![[Pasted image 20250127225319.png]]
- How does these neurons and layers actually operate ? Let’s say we have an image that is black and white and each pixel is represented by a number that determines the grayscale of the pixel . Each pixel’s value is fed to the neuron of the first layer for processing . 
- But how do the layers process and understand and return the value that is presented ? This is engineered similar to the how our brain works , it breaks down the image into multiple pieces and then joins them together to bring together a value . 
- For instance these middle two layers can be having sub-figures on their own to figure out until they collectively add to a potential result . ![[Pasted image 20250127230237.png]]
- **How are these  sub-problems recognised** - each neuron in one layer is connected to the neuron in the succeeding layer , and each of this connection has a weight associated with it , positive or negative . The neuron in the succeeding layer is tasked to find the sub-pattern from the weights and preceding layer’s neuron data . ![[Pasted image 20250127230944.png]]
- The entire result is interpreted as the weighted average of the values in the neurons and the weights corresponding as shown above and stored in the neurons .  But the problem here is that neurons store values from 0-1 hence an additional mathematical function is used to smoothen the data . This function can be either sigmoid or ReLU (rectified linear unit ) ![[Pasted image 20250127231351.png]]
- Bias values are often added to these weighted averages before being smoothened , to improve the accuracy of the results . 
- **How are these data stored and how is the result computed** - The entire structure revolves around matrices . The weights of each of these neurons for each of the neurons are stored in a matrix of rows that are equal to the neurons in a layer and columns that are equal to the number of the neurons .Multiplied by another matrix with the values held by each neuron .![[Pasted image 20250127233922.png]]
- By default the end result is stored in the succeeding layer’s neuron . 



Literature sources : [[But what is a neural network ? Deep Learning Chapter one]]