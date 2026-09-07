# FIR-FILTER-DESIGN
# EXP 4 c: Design-of-FIR-Digital-Filter-using-Hanning-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hanning-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
<br>clc ; 
<br>close ; 
<br>M=input('Enter the Odd Filter Length ='); 
<br>Wc=input('Enter the Digital Cut off frequency ='); 
<br>alpha= (M -1)/2 // Center Value 
<br>for n = 1:M 
<br>if (n ==alpha+1) 
<br>hd(n) = Wc/ %pi ; 
<br>else 
<br>hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
<br>end 
<br>end 
<br>// hanning Window 
<br>for n = 1:M 
<br>W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
<br>end 
<br>//Windowing filter coefficients 
<br>h = hd.*W; 
<br>disp(h,'Filter Coefficients are') 
<br>[hzm,fr]= frmag (h,256) ; 
<br>subplot(2 ,1 ,1) 
<br>plot(2*fr, hzm) 
<br>xlabel( ' Normalized Digital Frequency w'); 
<br>ylabel( 'Magnitude '); 
<br>title( ' Frequency Response of  FIR LPF using Hanning Window ') 
<br>hzm_dB = 20* log10 (hzm); 
<br>subplot (2 ,1 ,2); 
<br>plot(2*fr , hzm_dB); 
<br>xlabel( ' Normalized Digital Frequency W' ); 
<br>ylabel( 'Magnitude in dB'); 
<br>title('Frequency Response of FIR LPF using Hanning Window');

# OUTPUT: 
<img width="557" height="363" alt="image" src="https://github.com/user-attachments/assets/9a0d75fb-af9e-4591-b650-d9095e9d199f" />

<img width="455" height="377" alt="image" src="https://github.com/user-attachments/assets/28cc38a1-d2e3-474b-bed2-8b4d73e7e89b" />

# RESULT: 

Thus design of low pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
<br>clc ; 
<br>close ; 
<br>M=input('Enter the Odd Filter Length ='); 
<br>Wc=input('Enter the Digital Cut off frequency ='); 
<br>alpha= (M -1)/2 // Center Value 
<br>for n = 1:M 
<br>if (n ==alpha+1) 
<br>hd(n) = 1-Wc/ %pi ; 
<br>else 
<br>hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
<br>end 
<br>end 
<br>// Hanning Window 
<br>for n = 1:M 
<br>W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
<br>end 
<br>//Windowing filter coefficients 
<br>h = hd.*W; 
<br>disp(h,'Filter Coefficients are') 
<br>[hzm,fr]= frmag (h,256) ; 
<br>subplot(2 ,1 ,1) 
<br>plot(2*fr, hzm) 
<br>xlabel( ' Normalized Digital Frequency w'); 
<br>ylabel( 'Magnitude '); 
<br>title( ' Frequency Response of FIR HPF using Hanning Window ') 
<br>hzm_dB = 20* log10 (hzm); 
<br>subplot (2 ,1 ,2); 
<br>plot(2*fr , hzm_dB); 
<br>xlabel( ' Normalized Digital Frequency W' ); 
<br>ylabel( 'Magnitude in dB'); 
<br>title('Frequency Response of FIR HPF using Hanning Window');

# OUTPUT: 
<img width="427" height="389" alt="image" src="https://github.com/user-attachments/assets/3fc1b15e-94cf-40a8-931e-d4216c830b51" />

<img width="457" height="369" alt="image" src="https://github.com/user-attachments/assets/062ad28c-973d-4348-b2d5-125b35128c7b" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
//Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Hanning Window');
```

# Manual  Calculations :
<img width="1600" height="1553" alt="image" src="https://github.com/user-attachments/assets/083ddcbb-71c1-4226-b4f1-a4f7bd458b85" />
<img width="932" height="1501" alt="image" src="https://github.com/user-attachments/assets/3b4aa123-71c0-433c-af63-b42d5418b3f1" />


# OUTPUT: 
<img width="762" height="697" alt="image" src="https://github.com/user-attachments/assets/cbbefbf1-4d24-4fe3-a523-e294f06a2057" />
<img width="565" height="793" alt="image" src="https://github.com/user-attachments/assets/1a514ff2-13f1-44e1-9c29-672f1e03df85" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi); 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
//Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Hanning Window');
```
# OUTPUT: 
<img width="760" height="697" alt="image" src="https://github.com/user-attachments/assets/5def34f1-a161-4b52-9222-4c7d5182d883" />
<img width="552" height="727" alt="image" src="https://github.com/user-attachments/assets/3b8d2581-a326-4224-9e4b-4f8da495498a" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# Manual  Calculations :
<img width="1600" height="1553" alt="image" src="https://github.com/user-attachments/assets/083ddcbb-71c1-4226-b4f1-a4f7bd458b85" />
<img width="932" height="1501" alt="image" src="https://github.com/user-attachments/assets/3b4aa123-71c0-433c-af63-b42d5418b3f1" />


# OUTPUT: 
<img width="762" height="697" alt="image" src="https://github.com/user-attachments/assets/cbbefbf1-4d24-4fe3-a523-e294f06a2057" />
<img width="552" height="727" alt="image" src="https://github.com/user-attachments/assets/3b8d2581-a326-4224-9e4b-4f8da495498a" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.
