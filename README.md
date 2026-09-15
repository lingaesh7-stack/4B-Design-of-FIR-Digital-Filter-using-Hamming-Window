# FIR-FILTER-DESIGN
# EXP 4 b: Design-of-FIR-Digital-Filter-using-Hamming-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hamming-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close;

N = 21;               
wc = %pi / 2;         
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = wc / %pi;
    else
        hd(n+1) = sin(wc * (n - alpha)) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.54 - 0.46 * cos((2 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="893" alt="image" src="https://github.com/user-attachments/assets/e9a28a32-6648-4fef-945c-f5df759ea741" />

# RESULT: 

Thus design of low pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```clc;
clear;
close;

N = 21;               
wc = %pi / 2;         
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = 1 - (wc / %pi);
    else
        hd(n+1) = -sin(wc * (n - alpha)) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.54 - 0.46 * cos((2 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="897" alt="image" src="https://github.com/user-attachments/assets/aa779ced-50ee-433e-aaa8-9f70e973f3cd" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close;

N = 21;               
wc1 = %pi / 4;        
wc2 = 3 * %pi / 4;    
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = (wc2 - wc1) / %pi;
    else
        hd(n+1) = (sin(wc2 * (n - alpha)) - sin(wc1 * (n - alpha))) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.54 - 0.46 * cos((2 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="893" alt="image" src="https://github.com/user-attachments/assets/850dba09-7afb-4915-818c-2d91543503d3" />

# RESULT: 
Thus design of BAND pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close;

N = 21;               
wc1 = %pi / 4;        
wc2 = 3 * %pi / 4;    
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = 1 - ((wc2 - wc1) / %pi);
    else
        hd(n+1) = (sin(wc1 * (n - alpha)) - sin(wc2 * (n - alpha))) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.54 - 0.46 * cos((2 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="891" alt="image" src="https://github.com/user-attachments/assets/919231d8-21cf-45cf-a1ea-70856625ced7" />

# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.
