# Lecture 1

Introduction:

- What Machine Learning does
    
    Study of algorithms that:
    
    - Improve their performance P
    - at some task T
    - with experience E
    
    well-defined learning task: <P, T, E>
    
    Example :  Learning to predict Emergency C-sections, Learning to classify text documents, learning to detect objects in Images, Learn to classify the word a person is thinking about, based on FMRI brain activity
    
- Machine Learning - Theory
    
    PAC Learning Theory
    
    #examples (m)
    
    representational complexity(H)
    
    error rate($\epsilon$)
    
    failure probability($\delta$)
    
    $$
    m \ge \frac 1 \epsilon(ln |H| + ln (\frac 1 \delta))
    $$
    
- ML in CS:
    
    Machine learning already the preferred approach to
    
    - Speech recognition, Natural language processing
    - Computer Vision
    - Medical outcomes analysis
    - Robot control
        
        ![Screenshot 2023-07-29 at 11.21.27 PM.png](Lecture%201%200f84e7f6d5614fb2aef5ebaa3d3484a3/Screenshot_2023-07-29_at_11.21.27_PM.png)
        
        ![Screenshot 2023-07-29 at 11.22.49 PM.png](Lecture%201%200f84e7f6d5614fb2aef5ebaa3d3484a3/Screenshot_2023-07-29_at_11.22.49_PM.png)
        
- Function Approximation
    - **Problem Setting:**
        
        Set of possible instances X
        
        Unknown target function f: X→Y
        
        Set of function hypotheses H = {h | h: X→Y}
        
    - **Input:**
        
        Training examples $\{x^(i), y^(i)\}$ of unknown target function f
        
    - **Output:**
        
        Hypothesis $h \in H$ that best approximated target function f 
        
    
    ![Screenshot 2023-07-29 at 11.32.01 PM.png](Lecture%201%200f84e7f6d5614fb2aef5ebaa3d3484a3/Screenshot_2023-07-29_at_11.32.01_PM.png)
    
    A Decision tree for f: <Outlook, Temperature, Humidity, Wind> → Play Tennis?
    
    ![Screenshot 2023-07-29 at 11.36.32 PM.png](Lecture%201%200f84e7f6d5614fb2aef5ebaa3d3484a3/Screenshot_2023-07-29_at_11.36.32_PM.png)
    
    Each internal node: test one discrete-valued attribute attribute $X_i$
    
    Each branch from a node: selects one value for $X_i$
    
    Each leaf node: Predict $Y (or \ P(Y|X \in leaf))$
    
- Decision tree learning
    - **Problem Setting:**
        - Set of possible instances X
            
            each instance x in X is a feature vector
            
            - e.g: <Humidity=low, Wind=weak, Outlook=rain, Temp=hot>
        - Unknown target function f: X→Y
            
            Y=1 if we play tennis on this day, else Y=0
            
        - Set of function hypotheses H = {h | h: X→Y}
            
            each hypothesis h is a decision tree
            
            trees sorts x to leaf, which assigns y
            
    - **Input:**
        
        Training examples $\{x^(i), y^(i)\}$ of unknown target function f
        
    - **Output:**
        
        Hypothesis $h \in H$ that best approximated target function f 
        
        ![Screenshot 2023-07-29 at 11.49.18 PM.png](Lecture%201%200f84e7f6d5614fb2aef5ebaa3d3484a3/Screenshot_2023-07-29_at_11.49.18_PM.png)
        
- Top Down Induction of Decision Trees
    
    node = Root
    
    Main loop:
    
    1. A ← the “*best*” decision attribute for next node
    2. Assign A as decision attribute for node
    3. For each value of A, create new descendant of node
    4. Sort training examples to leaf nodes
    5. If training examples perfectly classified, Then STOP, Else iterate over new leaf nodes
- Sample Entropy
    
    S is a sample of training examples
    
    $p_{(+)}$ is the proportion of positive examples in S
    
    $p_{(-)}$ is the proportion of negative examples in S
    
    Entropy measures the impurity of S
    
    $H(S) \equiv - p_{(+)}log_2 p_{(+)}-p_{(-)}log_{2} p_{(-)}$
    
    $H(X) = - \sum_{i=1}^{n} P(X=i) log_2P(X=i)$
    
    H(X) is the expected number of bits needed to encode a randomly drawn value of X(under most efficient code)
    
    Most efficient possible code assigns -log_2P(X=i) bits to encode the message X=i
    
    So, Expected number of bits to code one random X is:
    
    $- \sum_{i=1}^{n} P(X=i) log_2P(X=i)$
    
    ***Specific conditional entropy*** H(X| Y=v) of X given Y=v :
    
    $H(X|Y=v) = - \sum_{i=1}^{n} P(X=i|Y=v) log_2P(X=i|Y=v)$
    
    Conditional entropy H(X| Y=v) of X given Y=v :
    
    $H(X|Y) = - \sum_{v \in values (Y)} P(Y=v) H(X|Y=v)$
    
    Mutual information aka Information Gain of X and Y(objective is to maximise this):
    
    $I(X,Y) = H(X) -H(X|Y) = H(Y) - H(Y|X)$
    
    ![Screenshot 2023-07-30 at 12.13.32 AM.png](Lecture%201%200f84e7f6d5614fb2aef5ebaa3d3484a3/Screenshot_2023-07-30_at_12.13.32_AM.png)
