# AIM:
To implement Shannon Fano coding schemes using MATLAB.

# SOFTWARE REQUIRED:
MATLAB

# PROGRAM:
# SHANNON FANO :
```
clc;

clear all;

close all;

m = input('Enter the no. of message ensembles : ');

z = [];

h = 0;

l = 0;

display('Enter the probabilities in descending order');


for i = 1:m

    fprintf('Ensemble %d\n', i);

    p(i) = input('');

end

a(1) = 0;

for j = 2:m

    a(j) = a(j-1) + p(j-1);

end

fprintf('\n Alpha Matrix');

display(a);

for i = 1:m

    n(i) = ceil(-1 * (log2(p(i))));

end

fprintf('\n Code length matrix');

display(n);

for i = 1:m

    int = a(i);

    for j = 1:n(i)

        frac = int * 2;

        c = floor(frac);

        frac = frac - c;

        z = [z c];

        int = frac;

    end

    fprintf('Codeword %d : ', i);

    disp(z);

    z = [];

end

fprintf('Avg. Code Length : ');

for i = 1:m

    x = p(i) * n(i);

    l = l + x;

    x = p(i) * log2(1 / p(i));

    h = h + x;

end

display(l);

fprintf('Entropy : ');

display(h);

fprintf('Efficiency : ');

display(100 * h / l);

fprintf('Redundancy : ');

display(100 - (100 * h / l));
```
# Input:
Enter the Number of message ensembles: 4
Enter the probabilities in ascending order Ensemble 1
0.2
Ensemble 2
0.3
Ensemble 4
0.4
Ensemble 5
0.4

# OUTPUT:

<img width="1071" height="617" alt="image" src="https://github.com/user-attachments/assets/dbe8924e-7dda-44e6-a32f-17d63a5c055d" />

# RESULT:
Thus Shannon Fano coding are performed using MATLAB.

