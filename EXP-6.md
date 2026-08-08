# AIM:
To implement FSK using MATLAB.

# SOFTWARE REQUIRED:
MATLAB

# PROGRAM:

clc;

clear;

close all;

t = 0:0.0001:0.15;

m = square(2*pi*10*t);

c1 = sin(2*pi*60*t);

c2 = sin(2*pi*120*t);

s1 = zeros(size(t));

for i = 1:length(t)

    if m(i) == 1
    
        s1(i) = c1(i);
        
    else
    
        s1(i) = c2(i);
        
    end
    
end

figure;

subplot(4,1,1);

plot(t,m);

xlabel('Time (s)');

ylabel('Amplitude');

title('Message Signal');

subplot(4,1,2);

plot(t,c1);

xlabel('Time (s)');

ylabel('Amplitude');

title('Carrier 1 (60 Hz)');

subplot(4,1,3);

plot(t,c2);

xlabel('Time (s)');

ylabel('Amplitude');

title('Carrier 2 (120 Hz)');

subplot(4,1,4);

plot(t,s1);

xlabel('Time (s)');

ylabel('Amplitude');

title('BFSK Modulated Output');

# OUTPUT:
<img width="1075" height="602" alt="image" src="https://github.com/user-attachments/assets/340190d5-4eee-4aab-9ee5-05bff6e3f3f5" />


# RESULT:
Thus, generation of FSK was implemented using MATLAB.



