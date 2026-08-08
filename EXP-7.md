# AIM:
To implement error control coding schemes with linear block codes using MATLAB.

# SOFTWARE REQUIRED: 
  MATLAB

# PROGRAM:
# ERROR CODING
# ENCODING:
clc;

close all;

n = 7;

k = 4;

msg = [1 0 0 1;

       1 0 1 0;
       
       1 0 1 1];
       
code = encode(msg, n, k, 'cyclic');

msg

code

# ENCODING OUTPUT:
<img width="597" height="262" alt="image" src="https://github.com/user-attachments/assets/cdc76659-20e1-4ec7-a0c5-e97d841a9f2d" />


# DECODING PROGRAM:
clc;

clear all;

close all;

q = 3;

n = 2^q - 1;

k = n - q;

parmat = hammgen(q);

trt = syndtable(parmat);

recd = [1 0 1 1 1 1 0];

syndrome = rem(recd * parmat', 2);

syndrome_de = bi2de(syndrome, 'left-msb');

disp(['syndrome = ', num2str(syndrome_de), ' (decimal) ', ...

      num2str(syndrome), ' (binary)']);

corrvect = trt(1 + syndrome_de, :);

correctedcode = rem(corrvect + recd, 2);

parmat

corrvect

correctedcode

# DECODING OUTPUT:
<img width="540" height="223" alt="image" src="https://github.com/user-attachments/assets/a57c894d-8dbe-4c97-bf80-4fd372858772" />

# RESULT:
Thus encoding and decoding of block codes are performed using MATLAB.

