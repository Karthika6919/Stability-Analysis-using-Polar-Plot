# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software<img width="837" height="1280" alt="image" 

## Theory:

![WhatsApp Image 2025-11-17 at 8 57 01 PM](https://github.com/user-attachments/assets/402a3277-9e8e-4c61-80ce-d6fa863b7c0f)
![WhatsApp Image 2025-11-17 at 8 57 01 PM (1)](https://github.com/user-attachments/assets/bf87cc05-303a-4c26-b43c-7b0e6bc98318)
<img width="944" height="1280" alt="image" src="https://github.com/user-attachments/assets/9fba8486-2485-46be-bacc-46e4b2e7241a" />




## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[1]
den = conv([1 0], conv([0.5 1], [0.2 1]));
sys=tf(num,den)
w=logspace(-1,2,1000);
[mag phase]=bode(sys,w);
mag=squeeze(mag);
phase=squeeze(phase);
theta=deg2rad(phase);
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:

<img width="1210" height="997" alt="image" src="https://github.com/user-attachments/assets/9582a9ba-f5e6-456a-bf7e-9527871bd7ca" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. 

Gain margin = 7.0000

Phase Margin = 55.6412 degree

Gain crossover frequency = 0.8979 rad/s

Phase crossover frequency = 3.1623

The system is Stable.
