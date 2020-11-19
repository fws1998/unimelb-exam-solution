# 2020 Final

**Question 1: [6 Marks]**

**For each of the layers of the OSI model state one key functionality that layer brings to networking; use one sentence explaining each. Then briefly explain what would be the problem(s) emerging if we were to combine the bottom two layers into one layer.**

Application: Use to receive information directly from user and disaplay incoming data to user.

Presentation: Use for data formatting, encryption, compression

Session: Use for authentication, authrorizaiton, session management

Transport: Provide efficient, reliable and cost-effective data transmission service, transmits data using transmission protocols including TCP and UDP

Network: Decides which physical path the data will take

Data Link: Use for reliable, efficient communication between two physically-connected nodes on a network.

Physical: Transmits raw bit stream over the physical medium



**Question 2: [3 Marks]**

**A computer is connected to an Internet Service Provider with a modem having 256Kbps connection capability. Given a frame size of 128 bits, compute the latency of communication for this computer to the provider’s server that the computer connects to. You can assume that the connection uses a fiber link, and speed of light for that particular medium is 100,000km/s. Also assume that the connection is only 1km long. Compute the latency under these settings. Show your calculations.**
$$
\text{T-delay} = \frac{128 bits}{256 \times 10^3 bps} = 5 * 10^{-4} s = 0.5 ms\\
\text{P-delay} = \frac{1km}{1 * 10^5 km/s} = 1 * 10^{-5} s = 0.01ms\\
L = \text{T-delay} + \text{P-delay} = 0.51 ms \\
\therefore latency is 0.51ms
$$


**Question 3: [4 Marks]**

**We have seen the MAC sublayer in class. Compare wireless communication mediums with respect to classical wired mediums and state the new issues we face using a few sentences to explain each issue.**

In wireless complications, stations may have coverage regions, which lead to hidden and exposed terminal problems.

Hiden terminals problems: senders cannot sense each other but collide at inteded receiver

Exposed terminals problem: senders are aware of each other and have different target, which can be handled simultaneously but however they didn't do so because they detecting other are transmitting messages.



**Question 4: [6 Marks]**

**We need to use the Cyclic redundancy check method for some data transmission as a means to deal with errors. Please compute the final data to be sent given the following information and show your steps/calculations. Original Data is 10010100 and your G(x) is x4 + x + 1.**

Final data: 1001 0100 0111



**Question 5: [5 Marks]**

**A channel has a bit rate of 15kbps and a propagation delay of 20ms. For what value of frame size does stop-and-wait protocol give an efficiency of 25 percent? Show your calculations.**
$$
U = \frac{L}{L+2T_pB}\\
0.25 = \frac{L}{L + 2 * 20 * 10^{-3} * 15 * 10^3} \\
L = 200bits \\
\therefore \text{The frame size is 200 bits}
$$
**Question 6: [4 Marks]**

**Given the adaptive tree walk protocol we have seen in class what happens with the following organization of stations and only B, D, F, and H want to send something. Please give steps in time, one per line, and explain briefly what happens in each time step.**

B D F H

Slot 1 -> B,D,F,H - collision

Slot 2 -> B, D - collison

Slot 3 -> B

Slot 4 -> D

Slot 5 -> F, H - collison

Slot 6 -> F

Slot 7 -> H



**Question 7: [6 Marks]**

**Distance vector routing is used for the six nodes given below, connected as shown in the figure. The following vectors have just come into router C from B: (5, 0, 7, 11, 10, 7); from D: (15, 11, 4, 0, 10, 11); and from E: (5, 10, 6, 10, 0, 3). Each vector contains the distances from a certain node to the other nodes, in the order of (A, B, C, D, E, F). The distances from C to B, D, and E, are 7, 4, and 6, respectively. What is the new vector for C: Use a list of outgoing lines to use and the expected distances from C to the other nodes, one entry per line for this would be clear enough and there is no need to draw a figure.**

| To   | DISTANCE | OUTGOING |
| ---- | -------- | -------- |
| A    | 11       | E        |
| B    | 7        | B        |
| C    | 0        | -        |
| D    | 4        | D        |
| E    | 6        | E        |
| F    | 9        | E        |



**Question 8: [5 Marks]**

**Please first briefly explain in a few steps how Dijkstra’s algorithm works for this question as we saw in class. Then given that Dijkstra’s algorithm, compute the shortest path from C to F for routing data for the following simple network. You do not need to show your steps but just give the final path.**

Using Dijkstra's, we will first Create a empty set P and initial all the distance for all nodes as infinity and start from the sink node and assign distance to 0

And then repeat until all nodes in P:

- For all the nodes not in P, compare distance d

- Pick a node v with min distance and add it to P 

- Update d for all the adjacent nodes of b(newly added node) 



Distance from C to F: 8, the path is C-B-F



**Question 9: [5 Marks]**

**For the transport layer, we want to use symmetric connection release. Is there a way to develop a perfect protocol for this, i.e. that does not lose any data in connection release regardless of circumstances? If the answer is yes, then explain one such protocol with a few sentences using two connected hosts and give the key insight of your solution as well. If not, then explain with a few sentences why it cannot be developed by discussing/modeling the problem at a higher level.**

No, if the acknowledgement of a disconnect request lost, one will always waiting for the other to disconnect while the other have already disconnect.



**Question 10: [3 Marks]**

**How does transparent fragmentation in Network Layer works, explain with a few sentences and mention its benefits and disadvantages.**

Transparent fragmentation divide and reassembled packages in each network. 

Pros:

The end host do not need to consider fragmentation.

Cons:

need more works

fragments must travel through the same gateway, which results in route constrained.



**Question 11: [3 Marks]**

**Briefly explain the difference between flow control and congestion control in networking.**

Flow control is an issue for point to point traffic, mainly focus on solving the problem that sender transmit data rate faster than receiver's maximum receive rate.

Congestion control is an issue affecting the ability of the subnet to actually carry the available traffic, in a global context.



**Question 12: [3 Marks]**

**A Hamming distance of 3 is given for a particular coding mechanism with a given alphabet of codewords of 000000, 000111, 111000, 111111, e.g., 01 becomes 000111. How many bit errors can this scheme correct? Show your calculations and briefly explain.**
$$
N_{\text{can_correct_bits}} = \frac{\text{3} - 1}{2} = 1
$$
**Question 13: [4 Marks]**

**Given the following figure for analysis of what TCP Tahoe does for congestion control that we saw in class, explain what happens in transmission rounds 0 – 6 and 15 - 20 briefly, describing the algorithms used there. Then describe how we can improve upon that.**

Slow start, the sender initializes the congestion window to a size and for each set of acknowledgements, it doubles the congestion window. And it reach its threshold at 6 round, so it increases its congestion window linearly.

To improve, we can use Fast recovery, which will set the window size to the half of current window size instead of reducing to 1, when packet loss.



**Question 14: [5 Marks]**

**Given the following protocol for authentication using Public Key Cryptography we saw in class, if we change the steps as stated in this question and then try to use the protocol, i.e., instead of the original steps that are given in the following figure, what would happen to the algorithm/communication, what would be changing in the protocol and how? Briefly explain. Changes are: Step 3: RA is dropped as well as Step 6: KS is dropped and Step 7: KS is replaced by EB.**

Without RA Bob can can still send back an acknowledgement but Alice cannot be sure that whether the responding person is Bob or not.

The whole purpose of this protocol is to share a secret key Ks. The public/private key algorithm is expensive and is hard to use for large data communications, therefore this is only used in the beginning to share a key Ks which will be used later by Alice and Bob to communicate via symmetric key algorithm. Without Ks, the encryption and decryption is very expensive and the whole process is meaningless



**Question 15: [3 Marks]**

**I can create a simple cipher as follows: i) create a random bit string as a key for this transmission only on my computer ii) convert my plaintext that I want to send by using its ASCII representation to a bit string as well iii) compute the XOR of these two strings bit by bit (assuming the same length for the two strings for the sake of simplicity for this question) iv) send the result string across to the other host who can undo the XOR operation. Is there a way to break this method, e.g., an intruder understanding this message somehow? If yes, give a way to break it, if not state the key reason why it cannot be broken. Then, briefly discuss the main strengths and weaknesses of this method.** 



No, this method is similar to one-time pad, which is hard to break without knowing the key.



Strengths:

Simple and easy to implement

hard to break

low computational cost



Weaknesses:

Not practical, need a key for every new message.

Need to consider how to share the key.

The key size is determined by the message.











