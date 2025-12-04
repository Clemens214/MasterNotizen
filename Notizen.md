# Formula
## Green's function
Definitions of the Green's function $G_D$ for an Operator $D$:
$$
\begin{align}
    D \cdot G_D (\Vec{r}, \Vec{r'}) = \delta (\Vec{r} - \Vec{r'})
\end{align}
$$
Definition of the Green's function of the Schrödinger equation, using the Dyson Equation:
$$
\begin{align}
    G &= \frac{G_0}{1-G_0 \Sigma} \\
    G^{-1} &= \frac{1-G_0 \Sigma}{G_0} = G_0^{-1} - \Sigma 
\end{align}
$$
with $G_0$ in the frequency domain $G_0 (\omega)$ being:
$$
\begin{align}
    G_0^r (\omega) &= \frac{1}{\omega - \hat{H} + i\eta}
\end{align}
$$
Giving us a definition for the Green's function $G$:
$$
\begin{align}
    G^{-1} &= G_0^{-1} - \Sigma = \omega - \hat{H} + i\eta - \Sigma \approx \omega - \hat{H} - \Sigma \\
    G &= \frac{1}{\omega - \hat{H} - \Sigma}
\end{align}
$$

## Self energy and Green's function of the semi-infinite lead}
### Total Hamiltonian and sub-Hamiltonians
Combined Hamiltonian of the Sample and the Leads:
$$
\begin{align}
    \hat{H} &= \left[ \begin{array}{c*{13}{c}c}
        y       & t_L   &       &       &       &       &       &       &       &       &       &       &       &       &       \\
        t_L     & y     & \ddots&       &       &       &       &       &       &       &       &       &       &       &       \\
                & \ddots& y     & t_L   &       &       &       &       &       &       &       &       &       &       &       \\
                &       & t_L   & y     & t^c_1 & \hdots& t^c_N &       &       &       &       &       &       &       &       \\
                &       &       & t^c_1 & y     & 0     & 0     & t_S   &       &       &       &       &       &       &       \\
                &       &       & \vdots& 0     & \ddots& 0     & 0     & t_S   &       &       &       &       &       &       \\
                &       &       & t^c_N & 0     & 0     & y     & 0     & \ddots& t_S   &       &       &       &       &       \\
                &       &       &       & t_S   & 0     & 0     & \ddots& 0     & 0     & t_S   &       &       &       &       \\
                &       &       &       &       & t_S   & \ddots& 0     & y     & 0     & 0     & t^c_N &       &       &       \\
                &       &       &       &       &       & t_S   & 0     & 0     & \ddots& 0     & \vdots&       &       &       \\
                &       &       &       &       &       &       & t_S   & 0     &       & y     & t^c_1 &       &       &       \\
                &       &       &       &       &       &       &       & t^c_N & \hdots& t^c_1 & y     & t_R   &       &       \\
                &       &       &       &       &       &       &       &       &       &       & t_R   & y     & \ddots&       \\
                &       &       &       &       &       &       &       &       &       &       &       & \ddots& y     & t_R   \\
                &       &       &       &       &       &       &       &       &       &       &       &       & t_R   & y     \\
    \end{array} \right] \\
    &= \left[ \begin{array}{lcr}
        \hat{H}_{L}     & \hat{H}_{LS}^\dagger  & 0                     \\
        \hat{H}_{LS}    & \hat{H}_{S}           & \hat{H}_{SR}          \\
        0               & \hat{H}_{SR}^\dagger  & \hat{H}_{R}           \\
    \end{array} \right]
\end{align}
$$
Sub-Hamiltonian of the Sample: 
$$
\begin{align}
    \hat{H}_S &= \left[ \begin{array}{c*{5}{c}c}
        y       & 0     & 0     & t_S   &       &       &       \\
        0       & \ddots& 0     & 0     & t_S   &       &       \\
        0       & 0     & y     & 0     & \ddots& t_S   &       \\
        t_S     & 0     & 0     & \ddots& 0     & 0     & t_S   \\
                & t_S   & \ddots& 0     & y     & 0     & 0     \\
                &       & t_S   & 0     & 0     & \ddots& 0     \\
                &       &       & t_S   & 0     &       & y     \\
    \end{array} \right] 
\end{align}
$$
Sub-Hamiltonian of the left/right Lead:
$$
\begin{align}
    \hat{H}_{L/R} &= \left[ \begin{array}{c*{5}{c}c}
        y           & t_{L/R}   &           &           \\
        t_{L/R}     & y         & \ddots    &           \\
                    & \ddots    & y         & t_{L/R}   \\
                    &           & t_{L/R}   & y         \\
    \end{array} \right] 
\end{align}
$$
With the structure of the hopping sub-Hamiltonians:
$$
\begin{align}
    \hat{H}_{LS} = \left[ \begin{array}{*{3}{c}}
        \hdots  & 0     & t^{LS}_1\\
        \hdots  & 0     & \vdots\\
        \hdots  & 0     & t^{LS}_N\\
        \hdots  & 0     & 0     \\
        \rddots & \vdots& \vdots\\
    \end{array} \right] ; 
    \hat{H}_{LS}^\dagger &= \left[ \begin{array}{*{5}{c}}
        \vdots  & \vdots& \vdots& \vdots& \rddots\\
        0       & 0     & 0     & 0     & \hdots\\
        t^{LS}_1& \hdots& t^{LS}_N  & 0     & \hdots\\
    \end{array} \right] 
\end{align}
$$
$$
\begin{align}
    \hat{H}_{SR} = \left[ \begin{array}{*{3}{c}}
        \vdots  & \vdots& \rddots\\
        0       & 0     & \hdots\\
        t^{SR}_N& 0     & \hdots\\
        \vdots  & 0     & \hdots\\
        t^{SR}_1& 0     & \hdots\\
    \end{array} \right] ; 
    \hat{H}_{SR}^\dagger &= \left[ \begin{array}{*{5}{c}}
        \hdots  & 0     &t^{SR}_N& \hdots& t^{SR}_1\\
        \hdots  & 0     & 0     & 0     & 0     \\
        \rddots & \vdots& \vdots& \vdots& \vdots\\
    \end{array} \right] 
\end{align}
$$

### Green's function
We know that the Green's function $G$ can be defined as:
$$
\begin{align}
    G_0^{Full} = \left( \omega + i\eta - \hat{H} \right)^{-1}
    &= \left[ \begin{array}{*{3}{c}}
        \omega + i\eta - \hat{H}_{L}    & \hat{H}_{LS}^\dagger  & 0                     \\
        \hat{H}_{LS}    & \omega + i\eta - \hat{H}_{S}          & \hat{H}_{SR}  \\
        0               & \hat{H}_{SR}^\dagger          & \omega + i\eta - \hat{H}_{R}          \\
    \end{array} \right]^{-1} \\
    \left[ \begin{array}{*{3}{c}}
        G_0^{L}     & G_0^{LS}  & 0         \\
        G_0^{SL}    & G_0^{S}   & G_0^{SR}  \\
        0           & G_0^{RS}  & G_0^{R}   \\
    \end{array} \right]
    &= \left[ \begin{array}{*{3}{c}}
        \omega + i\eta - \hat{H}_{L}    & \hat{H}_{LS}^\dagger  & 0                     \\
        \hat{H}_{LS}    & \omega + i\eta - \hat{H}_{S}          & \hat{H}_{SR}  \\
        0               & \hat{H}_{SR}^\dagger          & \omega + i\eta - \hat{H}_{R}          \\
    \end{array} \right]^{-1}
\end{align}
$$
This allows us to obtain these relations:
$$
\begin{align}
    G_0^{LS} &= -\left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot G_0^{S} \\
    G_0^{SL} &= -\left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{LS} \cdot G_0^{L} \\
    G_0^{RS} &= -\left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger \cdot G_0^{S} \\
    G_0^{SR} &= -\left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} \cdot G_0^{R} 
\end{align}
$$
$$
\begin{align}
    {G_0^{L}}^{-1} &= \left( \omega + i\eta - \hat{H}_{L} \right) 
    - \hat{H}_{LS}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{LS} \\
    {G_0^{L}}^{-1} &= G_{L_0}^{-1} - \hat{H}_{LS}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS} 
    = G_{L_0}^{-1} - \Sigma^L_S\\
    \vspace{1cm} \notag \\
    {G_0^{S}}^{-1} &=  \left( \omega + i\eta - \hat{H}_{L} \right) 
    - \hat{H}_{LS} \cdot \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger 
    - \hat{H}_{SR} \cdot \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger \\
    {G_0^{S}}^{-1} &= G_{S_0}^{-1} 
    - \hat{H}_{LS} \cdot G_{L_0} \cdot \hat{H}_{LS}^\dagger 
    - \hat{H}_{SR} \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger 
    = G_{S_0}^{-1} - \Sigma_L - \Sigma_R \\
    \vspace{1cm} \notag \\
    {G_0^{R}}^{-1} &= \left( \omega + i\eta - \hat{H}_{R} \right) 
    - \hat{H}_{SR}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} \\
    {G_0^{R}}^{-1} &= G_{R_0}^{-1} - \hat{H}_{SR}^\dagger \cdot G_{S_0} \cdot \hat{H}_{SR} 
    = G_{R_0}^{-1} - \Sigma^R_S \\
\end{align}
$$

### Self-Energies
We can now define the self-energies of the left and right semi-infinite leads:
$$
\begin{align}
    \Sigma_L &= \hat{H}_{LS} \cdot \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger 
    = \hat{H}_{LS} \cdot G_{L_0} \cdot \hat{H}_{LS}^\dagger \\
    \Sigma_R &= \hat{H}_{SR} \cdot \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger 
    = \hat{H}_{SR} \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger \\
    \vspace{1cm} \notag \\
    \Sigma^L_S &= \hat{H}_{LS}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{LS} 
    = \hat{H}_{LS}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS} \\
    \Sigma^R_S &= \hat{H}_{SR}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} 
    = \hat{H}_{SR}^\dagger \cdot G_{R_0} \cdot \hat{H}_{SR} 
\end{align}
$$
This allows us to rewrite $\Sigma_L$ and $\Sigma_R$ as:
$$
\begin{align}
    \Sigma_L &= \hat{H}_{LS} \cdot G_{L_0} \cdot \hat{H}_{LS}^\dagger = 
    = \sum_{i,j} \sum_{k,l}^L \left( \hat{H}_{LS} \right)_{ik} \cdot \left( G_{L_0} \right)_{kl} \cdot \left( \hat{H}_{LS}^\dagger \right)_{lj} \\
    &= \left( \begin{array}{*{1}{c}} t^{LS}_1 \\ \vdots \\ t^{LS}_N \\ \end{array} \right) 
    \cdot \left( G_{L_0} \right)_{MM} \cdot
    \left( \begin{array}{*{3}{c}} t^{LS}_1 & \hdots & t^{LS}_N \\ \end{array} \right)
\end{align}
$$
$$
\begin{align}
    \Sigma_R &= \hat{H}_{SR} \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger = 
    = \sum_{i,j} \sum_{k,l}^L \left( \hat{H}_{SR} \right)_{ik} \cdot \left( G_{R_0} \right)_{kl} \cdot \left( \hat{H}_{SR}^\dagger \right)_{lj} \\
    &= \left( \begin{array}{*{1}{c}} t^{SR}_N \\ \vdots \\ t^{SR}_1 \\ \end{array} \right) 
    \cdot \left( G_{R_0} \right)_{11} \cdot 
    \left( \begin{array}{*{5}{c}} t^{SR}_N & \hdots& t^{SR}_1 \\ \end{array} \right) 
\end{align}
$$
With size of the sample's sub-Hamiltonian $\hat{H}_S$: $L\times L$ 
and the lead's sub-Hamiltonian $\hat{H}_{L}$ and $\hat{H}_{R}$: $M\times M$ 
and the hopping sub-Hamiltonians $\hat{H}_{LS}$ and $\hat{H}_{SR}$: $L\times M$, 
where $M \rightarrow \infty$ since we are dealing with semi-infinite leads. 

### Restructuring of Sample and Lead sub-Hamiltonians
Sub-Hamiltonian of the Sample: 
$$
\begin{align}
    \hat{H}_S^{new} &= \left[ \begin{array}{c*{7}{c}c}
        y           &t^{LS}_1   & \hdots    & t^{LS}_N  &           &           &           &           &           \\
        t^{LS}_1    & y         & 0         & 0         & t_S       &           &           &           &           \\
        \vdots      & 0         & \ddots    & 0         & 0         & t_S       &           &           &           \\
        t^{LS}_N    & 0         & 0         & y         & 0         & \ddots    & t_S       &           &           \\
                    & t_S       & 0         & 0         & \ddots    & 0         & 0         & t_S       &           \\
                    &           & t_S       & \ddots    & 0         & y         & 0         & 0         & t^{SR}_N  \\
                    &           &           & t_S       & 0         & 0         & \ddots    & 0         & \vdots    \\
                    &           &           &           & t_S       & 0         & 0         & y         & t^{SR}_1  \\
                    &           &           &           &           & t^{SR}_N  & \hdots    & t^{SR}_1  & y         \\
    \end{array} \right] 
\end{align}
$$
Sub-Hamiltonian of the left/right Lead:
$$
\begin{align}
    \hat{H}_{L/R}^{new} = \hat{H}_{L/R} &= \left[ \begin{array}{c*{5}{c}c}
        y           & t_{L/R}   &           &           \\
        t_{L/R}     & y         & \ddots    &           \\
                    & \ddots    & y         & t_{L/R}   \\
                    &           & t_{L/R}   & y         \\
    \end{array} \right] 
\end{align}
$$
With the structure of the hopping sub-Hamiltonians:
$$
\begin{align}
    \hat{H}_{LS}^{new} = \left[ \begin{array}{*{3}{c}}
        \hdots  & 0     & t_L\\
        \hdots  & 0     & 0     \\
        \rddots & \vdots& \vdots\\
    \end{array} \right] ; 
    \hat{H}_{LS}^{new\dagger} &= \left[ \begin{array}{*{3}{c}}
        \vdots  & \vdots& \rddots\\
        0       & 0     & \hdots\\
        t_L     & 0     & \hdots\\
    \end{array} \right] 
\end{align}
$$
$$
\begin{align}
    \hat{H}_{SR}^{new} = \left[ \begin{array}{*{3}{c}}
        \vdots  & \vdots& \rddots\\
        0       & 0     & \hdots\\
        t_R     & 0     & \hdots\\
    \end{array} \right] ; 
    \hat{H}_{SR}^{new\dagger} &= \left[ \begin{array}{*{3}{c}}
        \hdots  & 0     & t_R   \\
        \hdots  & 0     & 0     \\
        \rddots & \vdots& \vdots\\
    \end{array} \right] 
\end{align}
$$
With size of the new sub-Hamiltonian of the sample $\hat{H}_S^{new}$: $(L+2)\times (L+2)$ 
and the new sub-Hamiltonian of the lead $\hat{H}_{L}^{new}$ and $\hat{H}_{R}^{new}$: $(M-1)\times (M-1)$ 
and the new hopping sub-Hamiltonians $\hat{H}_{LS}^{new}$ and $\hat{H}_{SR}^{new}$: $(L+2) \times (M-1)$, 
where $M$ is still defined as $M \rightarrow \infty$. \\
It follows now that:
$$
\begin{align}
    \Sigma_L^{new} &= \hat{H}_{LS}^{new} \cdot G_{L_0}^{new} \cdot \hat{H}_{LS}^{new\dagger} \\
    \left( \Sigma_L^{new} \right)_{ij} 
    &= \delta_{iN} \delta_{jN} \; t_L^2 \cdot \left( G_{L_0}^{new} \right)_{MM} \\
    \text{with: } G_{L_0}^{new} &= G_{L_0} = \left( \omega + i\eta - \hat{H}_{L} \right)^{-1}
\end{align}
$$
$$
\begin{align}
    \Sigma_R^{new} &= \hat{H}_{SR}^{new} \cdot G_{R_0}^{new} \cdot \hat{H}_{SR}^{new\dagger} \\
    \left( \Sigma_R^{new} \right)_{ij} 
    &= \delta_{iN} \delta_{jN} \; t_R^2\cdot \left( G_{R_0}^{new} \right)_{11} \\
    \text{with: } G_{R_0}^{new} &= G_{R_0} = \left( \omega + i\eta - \hat{H}_{R} \right)^{-1}
\end{align}
$$
### Green's function entries
In order to calculate the self-energies we need to know the last entry of the $G_{L_0}$ Green's function, 
and the first entry of the $G_{R_0}$ Green's function.  We know that $G_{L_0/R_0}^{-1} \cdot G_{L_0/R_0} = 1$, and with the definition of $G_{L_0/R_0}^{-1}$: $\left( \omega + i\eta - \hat{H}_{L/R} \right) G_{L_0/R_0} = 1$, we can now write:
Recalling the definition of these Green's functions $G_{L_0/R_0}$: 
$$
\begin{align}
    G_{L_0/R_0} = \left( \omega + i\eta - \hat{H}_{L/R} \right)^{-1}
    &= \left( \begin{array}{*{3}{c}}
        \omega + i\eta - \hat{H}_{L/R}^{11}   & \hat{H}_{L/R}^{1x}  & \hat{H}_{L/R}^{1M}  \\
        \hat{H}_{L/R}^{x1}    & \omega + i\eta - \hat{H}_{L/R}^{xx} & \hat{H}_{L/R}^{xM}  \\
        \hat{H}_{L/R}^{M1}    & \hat{H}_{L/R}^{Mx}  & \omega + i\eta - \hat{H}_{L/R}^{MM} 
    \end{array} \right)^{-1} \\
    \left( \begin{array}{c*{1}{c}c}
        G_{L_0/R_0}^{11}    & G_{L_0/R_0}^{1x}  & G_{L_0/R_0}^{1M}  \\
        G_{L_0/R_0}^{x1}    & G_{L_0/R_0}^{xx}  & G_{L_0/R_0}^{xM}  \\
        G_{L_0/R_0}^{M1}    & G_{L_0/R_0}^{Mx}  & G_{L_0/R_0}^{MM}  
    \end{array} \right)
    &= \left( \begin{array}{*{3}{c}}
        \omega + i\eta - \hat{H}_{L/R}^{11}   & \hat{H}_{L/R}^{1x}  & \hat{H}_{L/R}^{1M}  \\
        \hat{H}_{L/R}^{x1}    & \omega + i\eta - \hat{H}_{L/R}^{xx} & \hat{H}_{L/R}^{xM}  \\
        \hat{H}_{L/R}^{M1}    & \hat{H}_{L/R}^{Mx}  & \omega + i\eta - \hat{H}_{L/R}^{MM} 
    \end{array} \right)^{-1} 
\end{align}
$$
This allows us to obtain these relations: 
$$
\begin{align}
    ohsj
\end{align}
$$
$$
\begin{align}
    G_{L_0/R_0} = \left( \omega + i\eta - \hat{H}_{L/R} \right)^{-1}
    &= \left( \begin{array}{c*{5}{c}c}
        y + \omega + i\eta  & t_{L/R}           & \hdots            & 0                 \\
        t_{L/R}             & y + \omega + i\eta& \ddots            & \vdots            \\
        \vdots              & \ddots            & y + \omega + i\eta& t_{L/R}           \\
        0                   & \hdots            & t_{L/R}           & y + \omega + i\eta
    \end{array} \right)^{-1} \\
\end{align}
$$
Self energy $\Sigma$ of the semi-infinite leads:
$$
\begin{align}
    \Sigma_{ij}(\omega) = 
\end{align}
$$

## Torque
Formula for Torque:
$$
\begin{align}
    \delta\Vec{R}_i = \delta\theta \Vec{n}\times\Vec{R}_i
\end{align}
$$
describes the change in atomic coordinates $\delta\Vec{R}_i$ for the rotation of an infinitesimal angle $\delta\theta$ around the axis $\Vec{n}$. \\
Since the total energy $U$ of the system changes over the course of rotation, a work $\delta W$ needs to be performed to rotate the molecule.
$$
\begin{align}
    \delta W &= -\sum_i \frac{\delta U}{\delta\Vec{R}_i} \cdot \delta\Vec{R}_i \\
    &= -\sum_i \frac{\delta U}{\delta\Vec{R}_i} \cdot \left( \delta\theta \Vec{n}\times\Vec{R}_i \right) \\
    &= \delta\theta \Vec{n} \cdot \sum_i \Vec{R}_i \times \left( -\frac{\delta U}{\delta\Vec{R}_i} \right) \\
    &= \delta\theta \Vec{n} \cdot \Vec{\tau}_c
\end{align}
$$
With $\Vec{\tau}_c$ defined as:
$$
\begin{align}
    \Vec{\tau}_c = \sum_i \Vec{R}_i \times \left( -\frac{\delta U}{\delta\Vec{R}_i} \right)
\end{align}
$$
being the classical torque. 
Since the total energy $U$ can be expressed as the expectation value of the Hamiltonian $H$, we can rewrite the torque.
$$
\begin{align}
    \Vec{\tau} &= -\sum_i \Vec{R}_i \times \frac{\delta U}{\delta\Vec{R}_i} \\
    \Vec{n} \cdot \Vec{\tau} &= \frac{\delta U}{\delta \theta}
\end{align}
$$

# Adiabatic Expansion and Time-Evolution of Operators
In the density matrix formulation of quantum mechanics, the expectation value of an observable $O$ is obtained from:
$$
\begin{align}
    \braket{\mathcal{O}(t)} = \trace{\rho(t) \mathcal{O}}
\end{align}
$$
With the density matrix $\rho(t)$ at the time $t_0$ given by:
$$
\begin{align}
    \rho(t_0) = \sum_{n,l} f\left(\epsilon_n - \mu_l \right) \ket{\phi_n(t_0)}\bra{\phi_n(t_0)}
\end{align}
$$
and the time evolution:
$$
\begin{align}
    \rho(t) = U(t,t_0) \rho(t_0) U(t_0, t)
\end{align}
$$
with the time evolution operator $U(t,t_0)$:
$$
\begin{align}
    U(t,t_0) &= U_0(t,t_0)+\sum_n \ket{\phi_n(t)} \int_{t_0}^t dt' e^{-i(\alpha_n(t)-\alpha_n(t'))} 
    \bra{\Dot{\phi}_n(t')}U(t',t_0) \\
    U_0(t,t_0) &= \sum_n e^{-i\alpha_n(t)} \ket{\phi_n(t)} \bra{\phi_n(t_0)} e^{i\alpha_n(t_0)}
\end{align}
$$
$$
\begin{align}
    U(t_0,t) &= U_0(t_0,t) + \sum_n \int_{t_0}^t dt' e^{i(\alpha_n(t)-\alpha_n(t'))} 
    U(t_0,t') \ket{\Dot{\phi}_n(t')} \bra{\phi_n(t)} \\
    U_0(t_0,t) &= \sum_n e^{-i\alpha_n(t_0)} \ket{\phi_n(t_0)} \bra{\phi_n(t)} e^{i\alpha_n(t)}
\end{align}
$$
We can now calculate the zeroth-order term of the adiabatic expansion.
$$
\begin{align*}
    \braket{\mathcal{O}(t)} &= \trace{\rho(t) \mathcal{O}} 
    = \trace{U(t,t_0) \rho(t_0) U(t_0, t) \mathcal{O}} \\
    &= \trace{\left( U_0(t,t_0) + \sum_n \ket{\phi_n(t)} \int_{t_0}^t dt' 
    e^{-i(\alpha_n(t)-\alpha_n(t'))} \bra{\Dot{\phi}_n(t')} U(t',t_0) \right) 
    \rho(t_0) U(t_0,t) \mathcal{O}} \\
    % first
    &= \trace{U_0(t,t_0) \rho(t_0) U(t_0,t) \mathcal{O}} \\
    &\quad + \trace{\left( \sum_n \ket{\phi_n(t)} \int_{t_0}^t dt' e^{-i(\alpha_n(t)-\alpha_n(t'))} 
    \bra{\Dot{\phi}_n(t')} U(t',t_0) \right) \rho(t_0) U(t_0,t) \mathcal{O}} \\
    % second
    &= \trace{U_0(t,t_0) \rho(t_0) U_0(t_0,t) \mathcal{O}} \\
    &\quad + \trace{U_0(t,t_0) \rho(t_0) \left( \sum_n \int_{t_0}^t dt' 
    e^{i(\alpha_n(t)-\alpha_n(t'))} U(t_0,t') 
    \ket{\Dot{\phi}_n(t')} \bra{\phi_n(t)} \right) \mathcal{O}} \\
    &\quad + \trace{\left( \sum_n \ket{\phi_n(t)} \int_{t_0}^t dt' 
    e^{-i(\alpha_n(t)-\alpha_n(t'))} \bra{\Dot{\phi}_n(t')} U(t',t_0) \right) \rho(t_0) U_0(t_0,t) 
    \mathcal{O}} \\
    &\quad + \TRAce{\left( \sum_n \ket{\phi_n(t)} \int_{t_0}^t dt' e^{-i(\alpha_n(t)-\alpha_n(t'))} \bra{\Dot{\phi}_n(t')} U(t',t_0) \right) \rho(t_0) } \\
    &\quad\quad \traCE{\left( \sum_n \int_{t_0}^t dt' e^{i(\alpha_n(t)-\alpha_n(t'))} 
    U(t_0,t') \ket{\Dot{\phi}_n(t')} \bra{\phi_n(t)} \right) \mathcal{O}}
\end{align*}
$$
With the zeroth-order term:
$$
\begin{align*}
    \braket{\mathcal{O}(t)}_0 
    &= \trace{U_0(t,t_0) \rho(t_0) U(t_0,t) \mathcal{O}} 
    =\footnote{See derivation in chapter \ref{ch:Calc_O(t)_0}.}
    \trace{U_0(t,t_0) \rho(t_0) U_0(t_0, t) \mathcal{O}} \\
    &= \trace{\sum_n e^{-i\alpha_n(t)} \ket{\phi_n(t)} \bra{\phi_n(t_0)} 
    e^{i\alpha_n(t_0)} \rho(t_0) \sum_{n'} e^{-i\alpha_{n'}(t_0)} \ket{\phi_{n'}(t_0)} 
    \bra{\phi_{n'}(t)} e^{i\alpha_{n'}(t)} \mathcal{O}} \\
    &= \trace{\sum_{n, n'} e^{-i\left(\alpha_n(t)-\alpha_{n'}(t)\right)} 
    \bra{\phi_n(t_0)} \rho(t_0) \ket{\phi_{n'}(t_0)} e^{i\left(\alpha_n(t_0)-\alpha_{n'}(t_0)\right)} \bra{\phi_{n'}(t)} \mathcal{O} \ket{\phi_n(t)} } \\
    &= \trace{\sum_{n, n'} e^{-i\left(\alpha_n(t)-\alpha_{n'}(t)\right)} 
    \bra{\phi_n(t_0)} \sum_{m,l} f\left(\epsilon_m - \mu_l \right) \ket{\phi_m(t_0)} \bra{\phi_m(t_0)} 
    \ket{\phi_{n'}(t_0)} e^{i\left(\alpha_n(t_0)-\alpha_{n'}(t_0)\right)} 
    \bra{\phi_{n'}(t)} \mathcal{O} \ket{\phi_n(t)} } \\
    &= \trace{\sum_{n, n', m, l} f\left(\epsilon_m - \mu_l \right) 
    e^{-i\left(\alpha_n(t)-\alpha_{n'}(t)\right)} e^{i\left(\alpha_n(t_0)-\alpha_{n'}(t_0)\right)} 
    \bra{\phi_n(t_0)}  \ket{\phi_m(t_0)} \bra{\phi_m(t_0)} \ket{\phi_{n'}(t_0)} 
    \bra{\phi_{n'}(t)} \mathcal{O} \ket{\phi_n(t)} } \\
    &= \trace{\sum_{n, n', m, l} f\left(\epsilon_m - \mu_l \right) 
    e^{-i\left(\alpha_n(t)-\alpha_{n'}(t)\right)} e^{i\left(\alpha_n(t_0)-\alpha_{n'}(t_0)\right)} 
    \delta_{n, m} \delta_{n', m} \bra{\phi_{n'}(t)} \mathcal{O} \ket{\phi_n(t)} } \\
    &= \trace{\sum_{n, l} f\left(\epsilon_n - \mu_l \right) 
    \bra{\phi_{n}(t)} \mathcal{O} \ket{\phi_n(t)} }
    = \sum_{n, l} f\left(\epsilon_n - \mu_l \right) 
    \bra{\phi_{n}(t)} \mathcal{O} \ket{\phi_n(t)} \\
\end{align*}
$$
We can describe the Eigenstates of the System in terms of the Møller-operator: 
$$
\begin{align}
    \ket{\psi(t)} = i\eta \Greens{E,t} \ket{\psi_0}
\end{align}
$$
With: $\Greens{E,t} = \frac{1}{E-H(t)+i\eta}$, and $\eta = \lim_{x \rightarrow 0^+}x$
$$
\begin{align*}
    \braket{\mathcal{O}(t)}_0 
    &= \sum_{n, l} f\left(\epsilon_n - \mu_l \right) \bra{\phi_{n}(t)} \mathcal{O} \ket{\phi_n(t)} \\
    &= \sum_l \trace{f\left(\epsilon_n - \mu_l \right) \bra{\phi_{n}(t)} \mathcal{O} \ket{\phi_n(t)}} \\
    &= \sum_l \trace{f\left(\epsilon_n - \mu_l \right) 
    \left( \bra{\phi_{n,0}} \GreensD{E,t} (-i\eta) \right) 
    \mathcal{O} \left( i\eta \Greens{E,t}\ket{\phi_{n, 0}} \right) } \\
    &= \sum_l \trace{f\left(\epsilon_n - \mu_l \right) \eta^2 
    \bra{\phi_{n,0}} \GreensD{E,t} \mathcal{O} 
    \Greens{E,t} \ket{\phi_{n, 0}} } \\
    &= \sum_l \trace{f\left(\epsilon_n - \mu_l \right) \mathcal{O} 
    \eta^2 \Greens{E,t} \ket{\phi_{n, 0}} 
    \bra{\phi_{n,0}} \GreensD{E,t} } \\
\end{align*}
$$
After rewrite:
$$
\begin{align*}
    \braket{\mathcal{O}(t)}_0 
    &= \sum_{l} \int dE f\left(E - \mu_l \right) 
    \trace{\mathcal{O} A_l(E,t,t)} \\
    \text{with: }
    A_l(E,t,t') &= 
    \eta^2 \Greens{E,t} \delta\left( E-H_l \right) \GreensD{E,t'} \\
    A_{Ml}(E,t,t') &= 2\pi \mathcal{P}_M A_l(E,t,t) \mathcal{P}_M \\
    &= \GreensMol{E,t} \Gamma_l \GreensMolD{E,t'}
\end{align*}
$$
# Transmission & Torque Calculation
Using the formula derived in Chapter \ref{ch:Formula} we can now use this to calculate transmission and torque.

## Transmission

## Torque
When a molecule rotates, we can describe the change in the atomic coordinates of an atom $i$ for a rotation around an axis $\Vec{n}$ with an infinitesimal angle $\delta\theta$.
$$
\begin{align}
    \delta\Vec{R}_i = \delta\theta \cdot \Vec{n} \times \Vec{R}_i
\end{align}
$$
If we consider changes in energy over the course of the molecules' rotation, we can recover the work performed to affect that rotation, though this is only true when the energy depends only on the position of the atoms.
$$
\begin{align}
    \delta W &= - \sum_i \pardiff{U}{\Vec{R}_i} \cdot \delta \Vec{R}_i 
     = - \sum_i \delta \Vec{R}_i \cdot \pardiff{U}{\Vec{R}_i} \\
    &= - \sum_i \left( \delta\theta \cdot \Vec{n} \times \Vec{R}_i\right) \cdot \pardiff{U}{\Vec{R}_i} 
\end{align}
$$
Using the Scalar triple product, we can rewrite this:
$$
\begin{align}
    \delta W &= - \sum_i 
    \left( \delta\theta \cdot \Vec{n} \times \Vec{R}_i \right) \cdot \pardiff{U}{\Vec{R}_i} \\
    &= - \sum_i \delta\theta \cdot 
    \left( \Vec{n} \times \Vec{R}_i \cdot \pardiff{U}{\Vec{R}_i} \right) \\
    &= - \sum_i \delta\theta \cdot 
    \left( \Vec{n} \cdot \Vec{R}_i \times \pardiff{U}{\Vec{R}_i} \right) \\
    &= \delta\theta \cdot \Vec{n} \cdot \sum_i \Vec{R}_i \times \left( -\pardiff{U}{\Vec{R}_i} \right)
\end{align}
$$
$$
\begin{align}
    \delta W &= \delta\theta \cdot \Vec{n} \cdot \sum_i \Vec{R}_i \times 
    \left( -\pardiff{U}{\Vec{R}_i} \right) \\
    &= \delta\theta \cdot \Vec{n} \cdot \Vec{\tau}_i \\
    \text{with: } \Vec{\tau}_i &= \sum_i \Vec{R}_i \times \left( -\pardiff{U}{\Vec{R}_i} \right)
\end{align}
$$
Since $-\pardiff{U}{\Vec{R}_i}$ is the force experienced by the atom $i$, $\Vec{\tau}_i$ describes the classical torque. We can now describe the total energy of the System $U$ as the expectation value of the system's Hamiltonian $H$.

# Appendices
## Appendix: A
$$
\begin{align*}
    \braket{\mathcal{O}(t)}_0 &= \trace{U_0(t,t_0) \rho(t_0) U(t_0, t) \mathcal{O}} \\
    &= \trace{U_0(t,t_0) \rho(t_0) U_0(t_0,t) \mathcal{O}} \\
    &\quad + \trace{U_0(t,t_0) 
    \rho(t_0) \left( \sum_{n'} \int_{t_0}^t dt' e^{i(\alpha_{n'}(t)-\alpha_{n'}(t'))} U(t_0,t') 
    \ket{\Dot{\phi}_{n'}(t')} \bra{\phi_{n'}(t)} \right) \mathcal{O}} \\
    &= \trace{U_0(t,t_0) \rho(t_0) U_0(t_0,t) \mathcal{O}} \\
    &\quad + \trace{\sum_n e^{-i\alpha_n(t)} \ket{\phi_n(t)} \bra{\phi_n(t_0)} e^{i\alpha_n(t_0)} 
    \rho(t_0) \left( \sum_{n'} \int_{t_0}^t dt' e^{i(\alpha_{n'}(t)-\alpha_{n'}(t'))} U(t_0,t') 
    \ket{\Dot{\phi}_{n'}(t')} \bra{\phi_{n'}(t)} \right) \mathcal{O}} \\
    &= \trace{U_0(t,t_0) \rho(t_0) U_0(t_0,t) \mathcal{O}} \\
    &\quad + \TRAce{\sum_{n, n'} \int_{t_0}^t dt' 
    e^{i\alpha_n(t_0)} e^{i(\alpha_{n'}(t)-\alpha_{n'}(t')-\alpha_n(t))} } \\
    &\quad\quad \traCE{\bra{\phi_n(t_0)} \rho(t_0) U(t_0,t') \ket{\Dot{\phi}_{n'}(t')} 
    \bra{\phi_{n'}(t)} \mathcal{O} \ket{\phi_n(t)} } \\
    &= \trace{U_0(t,t_0) \rho(t_0) U_0(t_0,t) \mathcal{O}} \\
    &\quad + \TRAce{\sum_{n, n'} \int_{t_0}^t dt' 
    e^{i\alpha_n(t_0)} e^{i(\alpha_{n'}(t)-\alpha_{n'}(t')-\alpha_n(t))} } \\
    &\quad\quad \traCE{\bra{\phi_n(t_0)} \rho(t_0) 
    \left( U_0(t_0,t') + \sum_n \int_{t_0}^{t'} dt'' e^{i(\alpha_n(t')-\alpha_n(t''))} 
    U(t_0,t'') \ket{\Dot{\phi}_n(t'')} \bra{\phi_n(t')} \right)
    \ket{\Dot{\phi}_{n'}(t')} \bra{\phi_{n'}(t)} \mathcal{O} \ket{\phi_n(t)} }
\end{align*}
$$
since: $\bra{\phi_n(t)} \ket{\Dot{\phi}_{n'}(t')} = 0$
$$
\begin{align*}
    \braket{\mathcal{O}(t)}_0 &= \trace{U_0(t,t_0) \rho(t_0) U_0(t_0,t) \mathcal{O}} \\
    &\quad + \TRAce{\sum_{n, n'} \int_{t_0}^t dt' 
    e^{i\alpha_n(t_0)} e^{i(\alpha_{n'}(t)-\alpha_{n'}(t')-\alpha_n(t))} } \\
    &\quad\quad \traCE{ \bra{\phi_n(t_0)} \rho(t_0) U_0(t_0,t') \ket{\Dot{\phi}_{n'}(t')} 
    \bra{\phi_{n'}(t)} \mathcal{O} \ket{\phi_n(t)} } \\
    &= \trace{U_0(t,t_0) \rho(t_0) U_0(t_0,t) \mathcal{O}} \\
    &\quad + \TRAce{\sum_{n, n'} \int_{t_0}^t dt' 
    e^{i\alpha_n(t_0)} e^{i(\alpha_{n'}(t)-\alpha_{n'}(t')-\alpha_n(t))} } \\
    &\quad\quad \traCE{ \bra{\phi_n(t_0)} \rho(t_0) 
    \left( \sum_m e^{-i\alpha_m(t_0)} \ket{\phi_m(t_0)} \bra{\phi_m(t'')} e^{i\alpha_m(t'')} \right) 
    \ket{\Dot{\phi}_{n'}(t')} \bra{\phi_{n'}(t)} \mathcal{O} \ket{\phi_n(t)} } \\
    &= \trace{U_0(t,t_0) \rho(t_0) U_0(t_0,t) \mathcal{O}} \\
    &\quad + \TRAce{\sum_{n, n', m} \int_{t_0}^t dt' e^{i(\alpha_n(t_0)-\alpha_m(t_0))} 
    e^{i(\alpha_{n'}(t)-\alpha_{n'}(t')-\alpha_n(t))} e^{i\alpha_m(t'')}} \\
    &\quad\quad \traCE{ \bra{\phi_n(t_0)} \rho(t_0) \ket{\phi_m(t_0)} 
    \bra{\phi_m(t'')} \ket{\Dot{\phi}_{n'}(t')} 
    \bra{\phi_{n'}(t)} \mathcal{O} \ket{\phi_n(t)} }
\end{align*}
$$
since: $\bra{\phi_m(t'')} \ket{\Dot{\phi}_{n'}(t')} = 0$
$$
\begin{align*}
    \braket{\mathcal{O}(t)}_0 &= \trace{U_0(t,t_0) \rho(t_0) U_0(t_0,t) \mathcal{O}} \\
\end{align*}
$$
## Appendix: B
Combined Hamiltonian of the Sample and the Leads:
$$
\begin{align}
    \hat{H} &= \left[ \begin{array}{c*{13}{c}c}
        y       & t_L   &       &       &       &       &       &       &       &       &       &       &       &       &       \\
        t_L     & y     & \ddots&       &       &       &       &       &       &       &       &       &       &       &       \\
                & \ddots& y     & t_L   &       &       &       &       &       &       &       &       &       &       &       \\
                &       & t_L   & y     & t^c_1 & \hdots& t^c_N &       &       &       &       &       &       &       &       \\
                &       &       & t^c_1 &\epsilon + y   & 0     & 0     & t_S   &       &       &       &       &       &       &       \\
                &       &       & \vdots& 0     & \ddots& 0     & 0     & t_S   &       &       &       &       &       &       \\
                &       &       & t^c_N & 0     & 0     & \epsilon + y  & 0     & \ddots& t_S   &       &       &       &       &       \\
                &       &       &       & t_S   & 0     & 0     & \ddots& 0     & 0     & t_S   &       &       &       &       \\
                &       &       &       &       & t_S   & \ddots& 0     & \epsilon + y  & 0     & 0     & t^c_N &       &       &       \\
                &       &       &       &       &       & t_S   & 0     & 0     & \ddots& 0     & \vdots&       &       &       \\
                &       &       &       &       &       &       & t_S   & 0     &       & \epsilon + y  & t^c_1 &       &       &       \\
                &       &       &       &       &       &       &       & t^c_N & \hdots& t^c_1 & y     & t_R   &       &       \\
                &       &       &       &       &       &       &       &       &       &       & t_R   & y     & \ddots&       \\
                &       &       &       &       &       &       &       &       &       &       &       & \ddots& y     & t_R   \\
                &       &       &       &       &       &       &       &       &       &       &       &       & t_R   & y     \\
    \end{array} \right] \\
    &= \left[ \begin{array}{lcr}
        \hat{H}_{L}     & \hat{H}_{LS}^\dagger  & 0                     \\
        \hat{H}_{LS}    & \hat{H}_{S}           & \hat{H}_{SR}          \\
        0               & \hat{H}_{SR}^\dagger  & \hat{H}_{R}           \\
    \end{array} \right]
\end{align}
$$
Sub-Hamiltonian of the Sample: 
$$
\begin{align}
    \hat{H}_S &= \left[ \begin{array}{c*{5}{c}c}
        \epsilon + y    & 0     & 0     & t_S   &       &       &       \\
        0       & \ddots& 0     & 0     & t_S   &       &       \\
        0       & 0     & \epsilon + y  & 0     & \ddots& t_S   &       \\
        t_S     & 0     & 0     & \ddots& 0     & 0     & t_S   \\
                & t_S   & \ddots& 0     & \epsilon + y  & 0     & 0     \\
                &       & t_S   & 0     & 0     & \ddots& 0     \\
                &       &       & t_S   & 0     &       & \epsilon + y  \\
    \end{array} \right] 
\end{align}
$$
Single dimensional Hamiltonian:
$$
\begin{align}
    \hat{H} &= \left[ \begin{array}{l*{10}{c}r}
        y       & t_L   &       &       &       &       &       &       &       &       &       &       \\
        t_L     & y     & \ddots&       &       &       &       &       &       &       &       &       \\
                & \ddots& y     & t_L   &       &       &       &       &       &       &       &       \\
                &       & t_L   & y     & t_c   &       &       &       &       &       &       &       \\
                &       &       & t_c   & y     & t_S   &       &       &       &       &       &       \\
                &       &       &       & t_S   & y     & \ddots&       &       &       &       &       \\
                &       &       &       &       & \ddots& y     & t_S   &       &       &       &       \\
                &       &       &       &       &       & t_S   & y     & t_c   &       &       &       \\
                &       &       &       &       &       &       & t_c   & y     & t_R   &       &       \\
                &       &       &       &       &       &       &       & t_R   & y     & \ddots&       \\
                &       &       &       &       &       &       &       &       & \ddots& y     & t_R   \\
                &       &       &       &       &       &       &       &       &       & t_R   & y     
    \end{array} \right] 
\end{align}
$$
## Appendix: C
We know that the Green's function $G$ can be defined as:
$$
\begin{align}
    G_0^{Full} = \left( \omega - \hat{H} + i\eta \right)^{-1}
    &= \left[ \begin{array}{*{3}{c}}
        \omega + i\eta - \hat{H}_{L}    & \hat{H}_{LS}^\dagger  & 0                     \\
        \hat{H}_{LS}    & \omega + i\eta - \hat{H}_{S}          & \hat{H}_{SR}  \\
        0               & \hat{H}_{SR}^\dagger          & \omega + i\eta - \hat{H}_{R}          \\
    \end{array} \right]^{-1} \\
    \left[ \begin{array}{*{3}{c}}
        G_0^{L}     & G_0^{LS}  & G_0^{LR}  \\
        G_0^{SL}    & G_0^{S}   & G_0^{SR}  \\
        G_0^{RL}    & G_0^{RS}  & G_0^{R}   \\
    \end{array} \right]
    &= \left[ \begin{array}{*{3}{c}}
        \omega + i\eta - \hat{H}_{L}    & \hat{H}_{LS}^\dagger  & 0                     \\
        \hat{H}_{LS}    & \omega + i\eta - \hat{H}_{S}          & \hat{H}_{SR}          \\
        0               & \hat{H}_{SR}^\dagger          & \omega + i\eta - \hat{H}_{R}  \\
    \end{array} \right]^{-1}
\end{align}
$$
This allows us to obtain these relations:
$$
\begin{align}
    \left( \omega + i\eta - \hat{H}_{L} \right) \cdot G_0^{L} + \hat{H}_{LS}^\dagger \cdot G_0^{SL} = 1 \\
    \hat{H}_{LS} \cdot G_0^{LS} + \left( \omega + i\eta - \hat{H}_{S} \right) \cdot G_0^{S} + \hat{H}_{SR} \cdot G_0^{RS} = 1 \\
    \hat{H}_{SR}^\dagger \cdot G_0^{SR} + \left( \omega + i\eta - \hat{H}_{R} \right) \cdot G_0^{R} = 1 \\
    \vspace{1cm} \notag \\
    \left( \omega + i\eta - \hat{H}_{L} \right) \cdot G_0^{LS} + \hat{H}_{LS}^\dagger \cdot G_0^{S} = 0 \\
    \left( \omega + i\eta - \hat{H}_{L} \right) \cdot G_0^{LR} + \hat{H}_{LS}^\dagger \cdot G_0^{SR} = 0 \\
    \vspace{1cm} \notag \\
    \hat{H}_{LS} \cdot G_0^{L} + \left( \omega + i\eta - \hat{H}_{S} \right) \cdot G_0^{SL} + \hat{H}_{SR} \cdot G_0^{RL} = 0 \\
    \hat{H}_{LS} \cdot G_0^{LR} + \left( \omega + i\eta - \hat{H}_{S} \right) \cdot G_0^{SR} + \hat{H}_{SR} \cdot G_0^{R} = 0  \\
    \vspace{1cm} \notag \\
    \hat{H}_{SR}^\dagger \cdot G_0^{S} + \left( \omega + i\eta - \hat{H}_{R} \right) \cdot G_0^{RS} = 0 \\
    \hat{H}_{SR}^\dagger \cdot G_0^{SL} + \left( \omega + i\eta - \hat{H}_{R} \right) \cdot G_0^{RL} = 0 
\end{align}
$$
$$
\begin{align}
    G_0^{LS} &= -\left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot G_0^{S} \\
    G_0^{LR} &= -\left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot G_0^{SR} \\
    G_0^{SL} &= -\left( \omega + i\eta - \hat{H}_{S} \right)^{-1} 
    \cdot \left( \hat{H}_{LS} \cdot G_0^{L} + \hat{H}_{SR} \cdot G_0^{RL}\right) \\
    G_0^{SR} &= -\left( \omega + i\eta - \hat{H}_{S} \right)^{-1} 
    \cdot \left( \hat{H}_{LS} \cdot G_0^{LR} + \hat{H}_{SR} \cdot G_0^{R} \right) \\
    G_0^{RS} &= -\left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger \cdot G_0^{S} \\
    G_0^{RL} &= -\left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger \cdot G_0^{SL}
\end{align}
$$
$$
\begin{align}
    G_0^{LS} &= -\left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot G_0^{S} \\
    G_0^{LR} &= \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot 
    \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot 
    \left( \hat{H}_{LS} \cdot G_0^{LR} + \hat{H}_{SR} \cdot G_0^{R} \right) \\
    \rightarrow G_0^{LR} &= \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot 
    \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{LS} \cdot G_0^{LR} \\
    &+ \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot 
    \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} \cdot G_0^{R} \\
    G_0^{SL} &= -\left( \omega + i\eta - \hat{H}_{S} \right)^{-1} 
    \cdot \left( \hat{H}_{LS} \cdot G_0^{L} - \hat{H}_{SR} \cdot \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} 
    \cdot \hat{H}_{SR}^\dagger \cdot G_0^{SL}\right) \\ 
    \rightarrow G_0^{SL} &= -\left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{LS} \cdot G_0^{L} \\ 
    &+ \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} \cdot 
    \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger \cdot G_0^{SL} \\
    G_0^{SR} &= -\left( \omega + i\eta - \hat{H}_{S} \right)^{-1} 
    \cdot \left( -\hat{H}_{LS} \cdot \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} 
    \cdot \hat{H}_{LS}^\dagger \cdot G_0^{SR} + \hat{H}_{SR} \cdot G_0^{R} \right) \\
    \rightarrow G_0^{SR} &= \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{LS} 
    \cdot \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot G_0^{SR} \\
    &- \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} \cdot G_0^{R} \\
    G_0^{RS} &= -\left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger \cdot G_0^{S} \\
    G_0^{RL} &= \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} 
    \cdot \hat{H}_{SR}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} 
    \cdot \left( \hat{H}_{LS} \cdot G_0^{L} + \hat{H}_{SR} \cdot G_0^{RL}\right) \\
    \rightarrow G_0^{RL} &= \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} 
    \cdot \hat{H}_{SR}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} 
    \cdot \hat{H}_{LS} \cdot G_0^{L} \\
    &+ \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} 
    \cdot \hat{H}_{SR}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} 
    \cdot \hat{H}_{SR} \cdot G_0^{RL} 
\end{align}
$$
Since for an equation of the form $x = a \cdot x + b$, the solution is: $x = (1-a)^-1 \cdot b$
$$
\begin{align}
    G_0^{LS} &= -\left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot G_0^{S} \\
    G_0^{LR} &= \left( 1 - \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot 
    \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{LS} \right)^{-1} 
    \cdot \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot 
    \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} \cdot G_0^{R} \\
    &= \left( 1 - G_{L_0} \cdot \hat{H}_{LS}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS} \right)^{-1} 
    \cdot G_{L_0} \cdot \hat{H}_{LS}^\dagger \cdot G_{S_0} \cdot \hat{H}_{SR} \cdot G_0^{R} 
    = \left( 1 - G_{L_0} \cdot \Sigma^L_S \right)^{-1} 
    \cdot G_{L_0} \cdot \hat{H}_{LS}^\dagger \cdot G_{S_0} \cdot \hat{H}_{SR} \cdot G_0^{R} \\
    G_0^{SL} &= -\left(1 - \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} \cdot 
    \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger \right)^{-1} 
    \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{LS} \cdot G_0^{L} \\
    &= -\left( 1 - G_{S_0} \cdot \hat{H}_{SR} \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger \right)^{-1} 
    \cdot G_{S_0} \cdot \hat{H}_{LS} \cdot G_0^{L} 
    = -\left( 1 - G_{S_0} \cdot \Sigma_R \right)^{-1} \cdot G_{S_0} \cdot \hat{H}_{LS} \cdot G_0^{L} \\
    G_0^{SR} &= -\left( 1 - \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{LS} 
    \cdot \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \right)^{-1} 
    \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} \cdot G_0^{R} \\
    &= -\left( 1 - G_{S_0} \cdot \hat{H}_{LS} \cdot G_{L_0} \cdot \hat{H}_{LS}^\dagger \right)^{-1} 
    \cdot G_{S_0} \cdot \hat{H}_{SR} \cdot G_0^{R} 
    = -\left( 1 - G_{S_0} \cdot \Sigma_L \right)^{-1} \cdot G_{S_0} \cdot \hat{H}_{SR} \cdot G_0^{R} \\
    G_0^{RS} &= -\left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger \cdot G_0^{S} \\
    G_0^{RL} &= \left( 1 - \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} 
    \cdot \hat{H}_{SR}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} 
    \cdot \hat{H}_{SR} \right)^{-1} \cdot \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} 
    \cdot \hat{H}_{SR}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} 
    \cdot \hat{H}_{LS} \cdot G_0^{L} \\
    &= \left( 1 - G_{R_0} \cdot \hat{H}_{SR}^\dagger \cdot G_{S_0} \cdot \hat{H}_{SR} \right)^{-1} 
    \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS} \cdot G_0^{L} 
    = \left( 1 - G_{R_0} \cdot \Sigma_S^R \right)^{-1} 
    \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS} \cdot G_0^{L} 
\end{align}
$$
$$
\begin{align}
    G_0^{LS} &= -\left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger \cdot G_0^{S} \\
    G_0^{RS} &= -\left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger \cdot G_0^{S} \\
    G_0^{SL} &= -\left( 1 - G_{S_0} \cdot \Sigma_R \right)^{-1} \cdot G_{S_0} \cdot \hat{H}_{LS} \cdot G_0^{L} \\
    G_0^{SR} &=  -\left( 1 - G_{S_0} \cdot \Sigma_L \right)^{-1} \cdot G_{S_0} \cdot \hat{H}_{SR} \cdot G_0^{R} \\
    G_0^{LR} &= \left( 1 - G_{L_0} \cdot \Sigma^L_S \right)^{-1} 
    \cdot G_{L_0} \cdot \hat{H}_{LS}^\dagger \cdot G_{S_0} \cdot \hat{H}_{SR} \cdot G_0^{R} \\
    G_0^{RL} &= \left( 1 - G_{R_0} \cdot \Sigma_S^R \right)^{-1} 
    \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS} \cdot G_0^{L} 
\end{align}
$$
$$
\begin{align}
    1 &= \left( \omega + i\eta - \hat{H}_{L} \right) \cdot G_0^{L} 
    - \hat{H}_{LS}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot 
    \left( \hat{H}_{LS} \cdot G_0^{L} + \hat{H}_{SR} \cdot \left( 1 - G_{R_0} \cdot \Sigma_S^R \right)^{-1} 
    \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS} \cdot G_0^{L} \right) 
    \notag\\
    \rightarrow &{G_0^{L}}^{-1} = \left( \omega + i\eta - \hat{H}_{L} \right) 
    - \hat{H}_{LS}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{LS}  
    - \hat{H}_{LS}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot  \hat{H}_{SR} \cdot 
    \left( 1 - G_{R_0} \cdot \Sigma_S^R \right)^{-1} \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS} \\
    &{G_0^{L}}^{-1} = G_{L_0}^{-1} - \hat{H}_{LS}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS}  
    - \hat{H}_{LS}^\dagger \cdot G_{S_0} \cdot  \hat{H}_{SR} \cdot \left( 1 - G_{R_0} \cdot \Sigma_S^R \right)^{-1} 
    \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS} \\
    &{G_0^{L}}^{-1} = G_{L_0}^{-1} - \Sigma_S^L 
    - \hat{H}_{LS}^\dagger \cdot G_{S_0} \cdot  \hat{H}_{SR} \cdot \left( 1 - G_{R_0} \cdot \Sigma_S^R \right)^{-1} 
    \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger \cdot G_{S_0} \cdot \hat{H}_{LS} \\
    \notag \\
    1 &= -\hat{H}_{LS} \cdot \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} 
    \cdot \hat{H}_{LS}^\dagger \cdot G_0^{S} 
    + \left( \omega + i\eta - \hat{H}_{S} \right) \cdot G_0^{S} 
    - \hat{H}_{SR} \cdot \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} 
    \cdot \hat{H}_{SR}^\dagger \cdot G_0^{S} 
    \notag\\
    \rightarrow &{G_0^{S}}^{-1} = 
    -\hat{H}_{LS} \cdot \left( \omega + i\eta - \hat{H}_{L} \right)^{-1} \cdot \hat{H}_{LS}^\dagger 
    + \left( \omega + i\eta - \hat{H}_{S} \right) 
    - \hat{H}_{SR} \cdot \left( \omega + i\eta - \hat{H}_{R} \right)^{-1} \cdot \hat{H}_{SR}^\dagger \\
    &{G_0^{S}}^{-1} = G_{S_0}^{-1} - \hat{H}_{LS} \cdot G_{L_0} \cdot \hat{H}_{LS}^\dagger 
    - \hat{H}_{SR} \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger \\
    \vspace{1cm} \notag \\
    1 &= -\hat{H}_{SR}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} 
    \cdot \left( \hat{H}_{LS} \cdot G_0^{LR} + \hat{H}_{SR} \cdot G_0^{R} \right) + \left( \omega + i\eta - \hat{H}_{R} \right) \cdot G_0^{R}
    1 &= 
    -\hat{H}_{SR}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} \cdot G_0^{R} 
    + \left( \omega + i\eta - \hat{H}_{R} \right) \cdot G_0^{R} \notag\\
    \rightarrow &{G_0^{R}}^{-1} = 
    -\hat{H}_{SR}^\dagger \cdot \left( \omega + i\eta - \hat{H}_{S} \right)^{-1} \cdot \hat{H}_{SR} 
    + \left( \omega + i\eta - \hat{H}_{R} \right) \\
    &{G_0^{R}}^{-1} = G_{R_0}^{-1} - \hat{H}_{SR}^\dagger \cdot G_{S_0} \cdot \hat{H}_{SR} \\
\end{align}
$$
## Appendix: D
We know that $G_{L_0/R_0}^{-1} \cdot G_{L_0/R_0} = 1$, and with the definition of $G_{L_0/R_0}^{-1}$: \\
$\left( \omega + i\eta - \hat{H}_{L/R} \right) G_{L_0/R_0} = 1$, we can now write:
Recalling the definition of these Green's functions $G_{L_0/R_0}$: 
$$
\begin{align}
    G_{L_0/R_0} = \left( \omega + i\eta - \hat{H}_{L/R} \right)^{-1}
    &= \left( \begin{array}{*{3}{c}}
        \omega + i\eta - \hat{H}_{L/R}^{11}   & \hat{H}_{L/R}^{1x}  & \hat{H}_{L/R}^{1M}  \\
        \hat{H}_{L/R}^{x1}    & \omega + i\eta - \hat{H}_{L/R}^{xx} & \hat{H}_{L/R}^{xM}  \\
        \hat{H}_{L/R}^{M1}    & \hat{H}_{L/R}^{Mx}  & \omega + i\eta - \hat{H}_{L/R}^{MM} 
    \end{array} \right)^{-1} \\
    \left( \begin{array}{c*{1}{c}c}
        G_{L_0/R_0}^{11}    & G_{L_0/R_0}^{1x}  & G_{L_0/R_0}^{1M}  \\
        G_{L_0/R_0}^{x1}    & G_{L_0/R_0}^{xx}  & G_{L_0/R_0}^{xM}  \\
        G_{L_0/R_0}^{M1}    & G_{L_0/R_0}^{Mx}  & G_{L_0/R_0}^{MM}  
    \end{array} \right)
    &= \left( \begin{array}{*{3}{c}}
        \omega + i\eta - \hat{H}_{L/R}^{11}   & \hat{H}_{L/R}^{1x}  & \hat{H}_{L/R}^{1M}  \\
        \hat{H}_{L/R}^{x1}    & \omega + i\eta - \hat{H}_{L/R}^{xx} & \hat{H}_{L/R}^{xM}  \\
        \hat{H}_{L/R}^{M1}    & \hat{H}_{L/R}^{Mx}  & \omega + i\eta - \hat{H}_{L/R}^{MM} 
    \end{array} \right)^{-1} 
\end{align}
$$
This allows us to obtain these relations: 
$$
\begin{align}
    \left( \omega + i\eta - \hat{H}_{L/R}^{11} \right) \cdot G_{L_0/R_0}^{11} + 
    \hat{H}_{L/R}^{1x} \cdot G_{L_0/R_0}^{x1} + \hat{H}_{L/R}^{1M} \cdot G_{L_0/R_0}^{M1} = 1 \\
    \hat{H}_{L/R}^{x1} \cdot G_{L_0/R_0}^{1x} + \left( \omega + i\eta - \hat{H}_{L/R}^{xx} \right) 
    \cdot G_{L_0/R_0}^{xx} + \hat{H}_{L/R}^{xM} \cdot G_{L_0/R_0}^{Mx} = 1 \\
    \hat{H}_{L/R}^{M1} \cdot G_{L_0/R_0}^{1M} + \hat{H}_{L/R}^{Mx} \cdot G_{L_0/R_0}^{xM} + 
    \left( \omega + i\eta - \hat{H}_{L/R}^{MM} \right) \cdot G_{L_0/R_0}^{MM} = 1 \\
    \vspace{1cm} \notag \\
    \left( \omega + i\eta - \hat{H}_{L/R}^{11} \right) \cdot G_{L_0/R_0}^{1x} + 
    \hat{H}_{L/R}^{1x} \cdot G_{L_0/R_0}^{xx} + \hat{H}_{L/R}^{1M} \cdot G_{L_0/R_0}^{Mx} = 0 \\
    \left( \omega + i\eta - \hat{H}_{L/R}^{11} \right) \cdot G_{L_0/R_0}^{1M} + 
    \hat{H}_{L/R}^{1x} \cdot G_{L_0/R_0}^{xM} + \hat{H}_{L/R}^{1M} \cdot G_{L_0/R_0}^{MM} = 0 \\
    \vspace{1cm} \notag \\
    \hat{H}_{L/R}^{x1} \cdot G_{L_0/R_0}^{11} + \left( \omega + i\eta - \hat{H}_{L/R}^{xx} \right) 
    \cdot G_{L_0/R_0}^{x1} + \hat{H}_{L/R}^{xM} \cdot G_{L_0/R_0}^{M1} = 0 \\
    \hat{H}_{L/R}^{x1} \cdot G_{L_0/R_0}^{1M} + \left( \omega + i\eta - \hat{H}_{L/R}^{xx} \right) 
    \cdot G_{L_0/R_0}^{xM} + \hat{H}_{L/R}^{xM} \cdot G_{L_0/R_0}^{MM} = 0 \\
    \vspace{1cm} \notag \\
    \hat{H}_{L/R}^{M1} \cdot G_{L_0/R_0}^{11} + \hat{H}_{L/R}^{Mx} \cdot G_{L_0/R_0}^{x1} + 
    \left( \omega + i\eta - \hat{H}_{L/R}^{MM} \right) + G_{L_0/R_0}^{M1} = 0 \\
    \hat{H}_{L/R}^{M1} \cdot G_{L_0/R_0}^{1x} + \hat{H}_{L/R}^{Mx} \cdot G_{L_0/R_0}^{xx} + 
    \left( \omega + i\eta - \hat{H}_{L/R}^{MM} \right) + G_{L_0/R_0}^{Mx} = 0 
\end{align}
$$
Recalling the definition of the lead Hamiltonians $\hat{H}_{L/R}$:
$$
\begin{align}
    \hat{H}_{L/R} &= \left[ \begin{array}{c*{1}{c}c}
        \hat{H}_{L/R}^{11}  & \hat{H}_{L/R}^{1x}& \hat{H}_{L/R}^{1M}\\
        \hat{H}_{L/R}^{x1}  & \hat{H}_{L/R}^{xx}& \hat{H}_{L/R}^{xM}\\
        \hat{H}_{L/R}^{M1}  & \hat{H}_{L/R}^{Mx}& \hat{H}_{L/R}^{MM}\\
    \end{array} \right] 
    = \left[ \begin{array}{c*{5}{c}c}
        y           & t_{L/R}   &           &           \\
        t_{L/R}     & y         & \ddots    &           \\
                    & \ddots    & y         & t_{L/R}   \\
                    &           & t_{L/R}   & y         \\
    \end{array} \right] 
\end{align}
$$
We can conclude that: $\hat{H}_{L/R}^{M1} = \hat{H}_{L/R}^{1M} = 0$ \\
This allows us to update the relations: 
$$
\begin{align}
    \left( \omega + i\eta - \hat{H}_{L/R}^{11} \right) \cdot G_{L_0/R_0}^{11} + 
    \hat{H}_{L/R}^{1x} \cdot G_{L_0/R_0}^{x1} = 1 \\
    \hat{H}_{L/R}^{x1} \cdot G_{L_0/R_0}^{1x} + \left( \omega + i\eta - \hat{H}_{L/R}^{xx} \right) 
    \cdot G_{L_0/R_0}^{xx} + \hat{H}_{L/R}^{xM} \cdot G_{L_0/R_0}^{Mx} = 1 \\
    \hat{H}_{L/R}^{Mx} \cdot G_{L_0/R_0}^{xM} + 
    \left( \omega + i\eta - \hat{H}_{L/R}^{MM} \right) \cdot G_{L_0/R_0}^{MM} = 1 \\
    \vspace{1cm} \notag \\
    \left( \omega + i\eta - \hat{H}_{L/R}^{11} \right) \cdot G_{L_0/R_0}^{1x} + 
    \hat{H}_{L/R}^{1x} \cdot G_{L_0/R_0}^{xx} = 0 \\
    \left( \omega + i\eta - \hat{H}_{L/R}^{11} \right) \cdot G_{L_0/R_0}^{1M} + 
    \hat{H}_{L/R}^{1x} \cdot G_{L_0/R_0}^{xM} = 0 \\
    \vspace{1cm} \notag \\
    \hat{H}_{L/R}^{x1} \cdot G_{L_0/R_0}^{11} + \left( \omega + i\eta - \hat{H}_{L/R}^{xx} \right) 
    \cdot G_{L_0/R_0}^{x1} + \hat{H}_{L/R}^{xM} \cdot G_{L_0/R_0}^{M1} = 0 \\
    \hat{H}_{L/R}^{x1} \cdot G_{L_0/R_0}^{1M} + \left( \omega + i\eta - \hat{H}_{L/R}^{xx} \right) 
    \cdot G_{L_0/R_0}^{xM} + \hat{H}_{L/R}^{xM} \cdot G_{L_0/R_0}^{MM} = 0 \\
    \vspace{1cm} \notag \\
    \hat{H}_{L/R}^{Mx} \cdot G_{L_0/R_0}^{x1} + 
    \left( \omega + i\eta - \hat{H}_{L/R}^{MM} \right) + G_{L_0/R_0}^{M1} = 0 \\
    \hat{H}_{L/R}^{Mx} \cdot G_{L_0/R_0}^{xx} + 
    \left( \omega + i\eta - \hat{H}_{L/R}^{MM} \right) + G_{L_0/R_0}^{Mx} = 0 
\end{align}
$$
$$
\begin{align}
    G_{L_0/R_0}^{1x} &= - \left( \omega + i\eta - \hat{H}_{L/R}^{11} \right)^{-1} 
    \cdot \hat{H}_{L/R}^{1x} \cdot G_{L_0/R_0}^{xx} \\
    G_{L_0/R_0}^{1M} &= - \left( \omega + i\eta - \hat{H}_{L/R}^{11} \right)^{-1} 
    \cdot \hat{H}_{L/R}^{1x} \cdot G_{L_0/R_0}^{xM} \\
    G_{L_0/R_0}^{x1} &= - \left( \omega + i\eta - \hat{H}_{L/R}^{xx} \right)^{-1} 
    \cdot \left( \hat{H}_{L/R}^{x1} \cdot G_{L_0/R_0}^{11} + \hat{H}_{L/R}^{xM} \cdot G_{L_0/R_0}^{M1} \right) \\
    G_{L_0/R_0}^{xM} &= - \left( \omega + i\eta - \hat{H}_{L/R}^{xx} \right)^{-1} 
    \cdot \left( \hat{H}_{L/R}^{x1} \cdot G_{L_0/R_0}^{1M} + \hat{H}_{L/R}^{xM} \cdot G_{L_0/R_0}^{MM} \right) \\
    G_{L_0/R_0}^{M1} &= - \left( \omega + i\eta - \hat{H}_{L/R}^{MM} \right)^{-1} 
    \cdot \hat{H}_{L/R}^{Mx} \cdot G_{L_0/R_0}^{x1} \\
    G_{L_0/R_0}^{Mx} &= - \left( \omega + i\eta - \hat{H}_{L/R}^{MM} \right)^{-1} 
    \cdot \hat{H}_{L/R}^{Mx} \cdot G_{L_0/R_0}^{xx} 
\end{align}
$$

## Appendix: E
### Left
With the structure of the left hopping sub-Hamiltonians:
$$
\begin{align}
    \hat{H}_{LS} = \left[ \begin{array}{*{3}{c}}
        \hdots  & 0     & t^{LS}_1\\
        \hdots  & 0     & \vdots\\
        \hdots  & 0     & t^{LS}_N\\
        \hdots  & 0     & 0     \\
        \rddots & \vdots& \vdots\\
    \end{array} \right] ; 
    \hat{H}_{LS}^\dagger &= \left[ \begin{array}{*{5}{c}}
        \vdots  & \vdots& \vdots& \vdots& \rddots\\
        0       & 0     & 0     & 0     & \hdots\\
        t^{LS}_1& \hdots& t^{LS}_N  & 0     & \hdots\\
    \end{array} \right] 
\end{align}
$$
And the size of the sample's sub-Hamiltonian $\hat{H}_S$: $L\times L$, the lead's sub-Hamiltonian $\hat{H}_{L}$ and $\hat{H}_{R}$: $M\times M$  and the hopping sub-Hamiltonians $\hat{H}_{LS}$ and $\hat{H}_{SR}$: $L\times M$.  
This allows us to rewrite $\Sigma_L$:
$$
\begin{align}
    \Sigma_L &= \hat{H}_{LS} \cdot G_{L_0} \cdot \hat{H}_{LS}^\dagger = \sum_{i,j} \left( \Sigma_L \right)_{ij} 
    = \sum_{i,j} \sum_{k,l}^L \left( \hat{H}_{LS} \right)_{ik} \cdot \left( G_{L_0} \right)_{kl} \cdot \left( \hat{H}_{LS}^\dagger \right)_{lj} \\
    &= \sum_{i,j=0}^N \sum_{k,l=0}^L \delta_{k,M} \delta_{l,M} \left( \hat{H}_{LS} \right)_{ik} \cdot \left( G_{L_0} \right)_{kl} \cdot \left( \hat{H}_{LS}^\dagger \right)_{lj} \\
    &= \sum_{i,j}^N \left( \hat{H}_{LS} \right)_{iM} \cdot \left( G_{L_0} \right)_{MM} \cdot \left( \hat{H}_{LS}^\dagger \right)_{Mj} \\
    &= \left( \begin{array}{*{1}{c}} t^{LS}_1 \\ \vdots \\ t^{LS}_N \\ \end{array} \right) 
    \cdot \left( G_{L_0} \right)_{MM} \cdot
    \left( \begin{array}{*{3}{c}} t^{LS}_1 & \hdots & t^{LS}_N \\ \end{array} \right) \\
    &= \left( \begin{array}{*{4}{c}}
        t^{LS}_1 (G_{L_0})_{MM} t^{LS}_1    & t^{LS}_1 (G_{L_0})_{MM} t^{LS}_2
        & \hdots                            & t^{LS}_1 (G_{L_0})_{MM} t^{LS}_N  \\
        t^{LS}_2 (G_{L_0})_{MM} t^{LS}_1    & t^{LS}_2 (G_{L_0})_{MM} t^{LS}_2
        & \hdots                            & t^{LS}_2 (G_{L_0})_{MM} t^{LS}_N  \\
        \vdots          & \vdots            & \ddots            & \vdots        \\
        t^{LS}_N (G_{L_0})_{MM} t^{LS}_1    & t^{LS}_N (G_{L_0})_{MM} t^{LS}_2
        & \hdots                            & t^{LS}_N (G_{L_0})_{MM} t^{LS}_N
    \end{array} \right)
\end{align}
$$
### Right
With the structure of the right hopping sub-Hamiltonians:
$$
\begin{align}
    \hat{H}_{SR} = \left[ \begin{array}{*{3}{c}}
        \vdots  & \vdots& \rddots\\
        0       & 0     & \hdots\\
        t^{SR}_N& 0     & \hdots\\
        \vdots  & 0     & \hdots\\
        t^{SR}_1& 0     & \hdots\\
    \end{array} \right] ; 
    \hat{H}_{SR}^\dagger &= \left[ \begin{array}{*{5}{c}}
        \hdots  & 0     &t^{SR}_N& \hdots& t^{SR}_1\\
        \hdots  & 0     & 0     & 0     & 0     \\
        \rddots & \vdots& \vdots& \vdots& \vdots\\
    \end{array} \right] 
\end{align}
$$
And the size of the sample's sub-Hamiltonian $\hat{H}_S$: $L\times L$,  the lead's sub-Hamiltonian $\hat{H}_{L}$ and $\hat{H}_{R}$: $M\times M$ and the hopping sub-Hamiltonians  $\hat{H}_{LS}$ and  $\hat{H}_{SR}$:  $L\times M$. 
This allows us to rewrite $\Sigma_R$ as:
$$
\begin{align}
    \Sigma_R &= \hat{H}_{SR} \cdot G_{R_0} \cdot \hat{H}_{SR}^\dagger = \sum_{i,j} \left( \Sigma_R \right)_{ij} 
    = \sum_{i,j} \sum_{k,l}^L \left( \hat{H}_{SR} \right)_{ik} \cdot \left( G_{R_0} \right)_{kl} \cdot \left( \hat{H}_{SR}^\dagger \right)_{lj} \\
    &= \sum_{i,j=L-N}^L \sum_{k,l=0}^L \delta_{k,1} \delta_{l,1} \left( \hat{H}_{SR} \right)_{ik} \cdot \left( G_{R_0} \right)_{kl} \cdot \left( \hat{H}_{SR}^\dagger \right)_{lj} \\
    &= \sum_{i,j=L-N}^L \left( \hat{H}_{SR} \right)_{i1} \cdot \left( G_{R_0} \right)_{11} \cdot \left( \hat{H}_{SR}^\dagger \right)_{1j} \\
    &= \left( \begin{array}{*{1}{c}} t^{SR}_N \\ \vdots \\ t^{SR}_1 \\ \end{array} \right) 
    \cdot \left( G_{R_0} \right)_{11} \cdot 
    \left( \begin{array}{*{5}{c}} t^{SR}_N & \hdots& t^{SR}_1 \\ \end{array} \right) \\
    &= \left( \begin{array}{*{4}{c}}
        t^{SR}_N (G_{L_0})_{MM} t^{SR}_N    & t^{SR}_N (G_{L_0})_{MM} t^{SR}_{N-1}
        & \hdots                            & t^{SR}_N (G_{L_0})_{MM} t^{SR}_1  \\
        t^{SR}_{N-1} (G_{L_0})_{MM} t^{SR}_N& t^{SR}_{N-1} (G_{L_0})_{MM} t^{SR}_{N-1}
        & \hdots                            & t^{SR}_{N-1} (G_{L_0})_{MM} t^{SR}_1  \\
        \vdots          & \vdots            & \ddots            & \vdots        \\
        t^{SR}_1 (G_{L_0})_{MM} t^{SR}_N    & t^{SR}_1 (G_{L_0})_{MM} t^{SR}_{N-1}
        & \hdots                            & t^{SR}_1 (G_{L_0})_{MM} t^{SR}_1
    \end{array} \right)
\end{align}
$$