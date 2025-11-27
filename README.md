# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![WhatsApp Image 2025-11-27 at 23 17 10_fda4ab1f](https://github.com/user-attachments/assets/2a883b37-f820-47a7-80cf-d993d620addd)
![WhatsApp Image 2025-11-27 at 23 17 11_d066b9c7](https://github.com/user-attachments/assets/11540799-9108-4075-b870-977e701faa4c)
![WhatsApp Image 2025-11-27 at 23 17 11_e1073c4d](https://github.com/user-attachments/assets/357c291f-2cd4-43e4-8844-f2326429fbf2)
![WhatsApp Image 2025-11-27 at 23 17 12_1fdeebc2](https://github.com/user-attachments/assets/6e146661-fdaa-400d-b8a1-be13dc328d30)



## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 

num = [10]<br>
den = [0.1 0.7 1 0]<br>
sys = tf(num, den)<br>
[mag, phase, W] = bode(sys)<br>
mag = squeeze(mag)<br>
phase = squeeze(phase)<br>
phase1 = deg2rad(phase)<br>
polarplot(phase1, mag, 'linewidth', 1.5)<br>
grid on<br>
[Gm Pm Wpc Wgc] = margin(sys)<br>
if (Wpc > Wgc)<br>
    disp('stable')<br>
elseif (Wpc == Wgc)<br>
    disp('marginally stable')<br>
else<br>
    disp('unstable')<br>
end<br>
## Output:
<img width="713" height="640" alt="image" src="https://github.com/user-attachments/assets/e41e6aaa-dbe8-4a05-934b-e1ad1e6f7d90" />


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin =0.7 <br>
Phase Margin =-8.8865 <br>
Gain crossover frequency =3.7565 <br>
Phase crossover frequency =3.1623 <br>
The system is unstable.
