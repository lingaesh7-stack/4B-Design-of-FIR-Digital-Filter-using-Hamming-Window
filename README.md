# FIR-FILTER-DESIGN
# EXP 4 b: Design-of-FIR-Digital-Filter-using-Hamming-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hamming-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=Wc/%pi;
else
hd(n)=sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=0.54-(0.46*cos((2*%pi*(n-1))/(M-1)));
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR LPF using Hamming Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR LPF using Hamming Window');
```
# OUTPUT: 
<img width="730" height="585" alt="image" src="https://github.com/user-attachments/assets/ae058699-74de-4b0b-bea9-a2e3ce87ec8e" />


# RESULT: 

Thus design of low pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=1-Wc/%pi;
else
hd(n)=-sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=0.54-(0.46*cos((2*%pi*(n-1))/(M-1)));
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR HPF using Hamming Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR HPF using Hamming Window');
```
# OUTPUT: 
<img width="712" height="578" alt="image" src="https://github.com/user-attachments/assets/51899cd9-d5aa-4f67-a6f0-eecd7c671e9f" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
Wc2=Wc(2);
Wc1=Wc(1);
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=(Wc2-Wc1)/%pi;
else
hd(n)=(sin(Wc2*((n-1)-alpha))-sin(Wc1*((n-1)-alpha)))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=0.54-(0.46*cos((2*%pi*(n-1))/(M-1)));
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR BPF using Hamming Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR BPF using Hamming Window');
```
# OUTPUT: 
<img width="711" height="581" alt="image" src="https://github.com/user-attachments/assets/1413cb0e-3b3b-4f11-ac2c-c708b68d13c0" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
Wc2=Wc(2);
Wc1=Wc(1);
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=1-((Wc2-Wc1)/%pi);
else
hd(n)=(sin(Wc1*((n-1)-alpha))-sin(Wc2*((n-1)-alpha)))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=0.54-(0.46*cos((2*%pi*(n-1))/(M-1)));
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR BSF using Hamming Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR BSF using Hamming Window');
```
# OUTPUT: 
<img width="736" height="582" alt="image" src="https://github.com/user-attachments/assets/9f6d4bd4-0f44-45f3-9c06-005fedda2f97" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.
