```mermaid
flowchart TD
A([Start])-->B[Sleep]
B-->C[Wake up]
C-->D{Too early?}
D--No-->E[Brush your teeth]
D--Yes-->B
E-->F[Eat something]
F-->G[Put your clothes on]
G-->H{Cold?}
H--No-->I[Go out and do your stuff]
H--Yes-->J[Take your Coat]
J-->I
I-->K([End])
