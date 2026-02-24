# Week 1 
### method to sum incrementally up to a number of times
```
def sum_incremental(times, increment):
    total = 0.0

    for _ in range(times):
        total += increment

    return total
```
### run
```
# abolute error -1.588205122970976e-10
ae1000 = 1000 - wk1.sum_incremental(10000, 0.1)

# abolute error -1.8848368199542165e-08
ae10000 = 10000 - wk1.sum_incremental(100000, 0.1)

# abolute error -1.3328826753422618e-06
ae100000 = 100000 - wk1.sum_incremental(1000000, 0.1)
```
### III matrix operations
```math
A=\begin{bmatrix}1&2\\-1&1\end{bmatrix}, B=\begin{bmatrix}2&0\\0&2\end{bmatrix}, C=\begin{bmatrix}2&0&-3\\0&0&-1\end{bmatrix}, D=\begin{bmatrix}1&2\\2&3\\-1&0\end{bmatrix}, 
x=\begin{bmatrix}1\\0\end{bmatrix}, y=\begin{bmatrix}0\\1\end{bmatrix}, z=\begin{bmatrix}1\\2\\-1\end{bmatrix}
```
### solutions
```math
(a) A+B=\begin{bmatrix}1+2&2+0\\-1+0&1+2\end{bmatrix} = \begin{bmatrix}3&2\\-1&3\end{bmatrix}
```
```math
(b) 3x-4y=\begin{bmatrix}3*1\\3*0\end{bmatrix} - \begin{bmatrix}4*0\\4*1\end{bmatrix} = \begin{bmatrix}3\\-4\end{bmatrix}
```
```math
(c) Ax=\begin{bmatrix}1*1+2*0\\-1*1+1*0\end{bmatrix} = \begin{bmatrix}1\\-1\end{bmatrix}
```
```math
(d) B(x-y)=\begin{bmatrix}2&0\\0&2\end{bmatrix}*\begin{bmatrix}1-0\\0-1\end{bmatrix} =\begin{bmatrix}2&0\\0&2\end{bmatrix}*\begin{bmatrix}1\\-1\end{bmatrix}
=\begin{bmatrix}2*1+0*(-1)\\0*1+2*(-1)\end{bmatrix}=\begin{bmatrix}2\\-2\end{bmatrix}
```
```math
(e) Dx=\begin{bmatrix}1&2\\2&3\\-1&0\end{bmatrix}*\begin{bmatrix}1\\0\end{bmatrix} =\begin{bmatrix}1*1+2*0\\2*1+3*0\\(-1)*1+0*0\end{bmatrix}
=\begin{bmatrix}1\\2\\-1\end{bmatrix}
```
```math
(f) Dy=\begin{bmatrix}1&2\\2&3\\-1&0\end{bmatrix}*\begin{bmatrix}0\\1\end{bmatrix} =\begin{bmatrix}1*0+2*1\\2*0+3*1\\(-1)*0+0*1\end{bmatrix}
=\begin{bmatrix}2\\3\\0\end{bmatrix}
```
```math
(g) AB=\begin{bmatrix}1&2\\-1&1\end{bmatrix}*\begin{bmatrix}2&0\\0&2\end{bmatrix} =\begin{bmatrix}1*2+2*0&1*0+2*2\\-1*2+1*0&-1*0+1*2\end{bmatrix}
=\begin{bmatrix}2&4\\-2&2\end{bmatrix}
```
```math
(h) BC=\begin{bmatrix}2&0\\0&2\end{bmatrix}*\begin{bmatrix}2&0&-3\\0&0&-1\end{bmatrix} =\begin{bmatrix}2*2+0*0&2*0+0*0&2*(-3)+0*(-1)\\0*2+2*0&0*0+2*0&0*(-3)+2*(-1)\end{bmatrix}
=\begin{bmatrix}4&0&-6\\0&0&-2\end{bmatrix}
```
```math
(i) CD=\begin{bmatrix}2&0&-3\\0&0&-1\end{bmatrix}*\begin{bmatrix}1&2\\2&3\\-1&0\end{bmatrix} =\begin{bmatrix}2*1+0*2+(-3)*(-1)&2*2+0*3+(-3)*0\\0*1+0*2+(-1)*(-1)&0*2+0*3+(-1)*0\end{bmatrix}
=\begin{bmatrix}5&4\\1&0\end{bmatrix}
```
### IV logistic equation
```math
x_{n+1}=\rho x_n(1-x_n)
```
```math
\rho = 0.8, 1.5, 2.8, 3.2, 3.5, 3.65
```
```code
#rho_vals = [0.8, 1.5, 2.8, 3.2, 3.5, 3.65]
def logistic_eq(rho, n):
    # first result x(0) = 0.5
    results =[0.5]
    for _ in range(n-1):
        x_ = rho*results[-1]*(1-results[-1])
        results.append(x_)

    return results
```
```math
\begin{aligned}
For \rho = 0.8 &ensp;   
x_{1..50} = [0.5, 0.2, 0.12800000000000003, 0.08929280000000003, 0.06505567669452801, \\0.048658748499476046, 0.03703285975515263, 0.02852914164280626, 0.02217218377594477, 0.017344462434040402, \\0.013634905645531652, 0.010759195994855282, 0.008514748557119659, 0.00675379809130295, 0.00536654744211589, \\0.004270198088533929, 0.003401570797454888, 0.0027120000908518326, 0.002163716117087242, 0.001727227559721519, \\0.0013793953957427659, 0.0011019941312679757, 0.0008806237921621013, 0.0007038786351190235, 0.0005627065519888372, \\0.0004499119306601488, 0.0003597676079318388, 0.0002877105401600974, 0.00023010221024414258, 0.0001840394105735867, \\0.00014720443205515398, 0.00011774621032826985, 9.418587692657855e-05, 7.53416047577329e-05, 6.026874272026035e-05, \\4.821208831912901e-05, 3.8567811130935136e-05, 3.0853058923903765e-05, 2.4681685610127044e-05, 1.9744861139617994e-05, \\1.5795577024061257e-05, 1.2636262019046189e-05, 1.01088818751427e-05, 8.087023748519948e-06, 6.469566678853471e-06, \\5.175619858848368e-06, 4.140474457445956e-06, 3.3123658511337784e-06, 2.6498839034929973e-06, 2.1199015052866365e-06]
\end{aligned}
```
```math
\begin{aligned}
For \rho = 1.5 &ensp;   
x_{1..50} = [0.5, 0.375, 0.3515625, 0.341949462890625, 0.3375300415791571, \\0.3354052689160944, 0.33436286174912516, 0.3338465076480908, 0.33358952546889614, 0.3334613309494993, \\0.3333973075663317, 0.33336531431077876, 0.3333493222878816, 0.33334132742713746, 0.33333733028437706, \\0.33333533178489183, 0.33333433255312184, 0.33333383294172997, 0.3333335831371573, 0.33333345823515165, \\0.33333339578421906, 0.33333336455877033, 0.3333333489460503, 0.33333334113969143, 0.33333333723651226, \\0.3333333352849228, 0.3333333343091281, 0.33333333382123076, 0.33333333357728206, 0.33333333345530763, \\0.3333333333943204, 0.3333333333638268, 0.33333333334858, 0.3333333333409567, 0.33333333333714504, \\0.3333333333352391, 0.3333333333342863, 0.3333333333338098, 0.3333333333335716, 0.3333333333334525, \\0.33333333333339293, 0.33333333333336307, 0.33333333333334825, 0.3333333333333408, 0.3333333333333371, \\0.33333333333333526, 0.3333333333333343, 0.33333333333333376, 0.3333333333333336, 0.3333333333333335]
\end{aligned}
```
