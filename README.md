# Homework - Static Viz


Homework for Static Viz module.  Please place all of your code in
one file named `static_viz.py`.


## Problem 1

Consider the COVID-19 data explored in the lesson on Matplotlib, which you can
download and turn into a `pandas` DataFrame using this code:

```python
import pandas
import urllib.request
url = "https://api.covidtracking.com/v1/states/daily.csv"
urllib.request.urlretrieve(url, "./covid.csv")
covid = pandas.read_csv('./covid.csv')
```

If you download that file today, the most recent date will be today
or yesterday (depending on the time of day).  In class, my data stopped
with 10/29/2020 numbers.  For the number of KS positive cases as a function
of days following the emergence of COVID-19 in the United States:

```
def positive_estimated(t):
   from numpy import exp
   a, b, c  = [-2.45627783e-05,  2.43950058e-02,  6.40949365e+00]
   return exp(a*t**2 + b*t**1 + c*t**0)
```

Create a single figure with the actual KS positives and the *estimated*
KS positives versus time.  On the same figure, show the difference
in these values.  Make sure the viewer needs to do as little work
as possible to understand the data.

## Problem 2

In the Matplotlib lesson, an exercise is proposed base on a
a contour plot (rom D.S. McGregor et al. NIM A 343 (1994).
In that same lesson, I give some starter code, but it's not
quite there.

Things that need fixin':

   - *appropriate axis labels* (e.g., `Electron Extraction Factor')
   - correct contour levels (i.e., 0.1, 0.2, 0.5, 1%, and so on).
     Hint: look up the documentation for `plt.contour`.
   - *correct $x$  and $y$ tick values* (e.g., -1 should be 0.1 and 2
       should be 100). Hint: look up, e.g.,`plt.xticks`.
   - *annotations for each contour line*. Hint: look up
       `plt.text`, paying specific attention to `fontsize`,
      `horizontalalignment`, and `verticalalignment`.
       You might also want to consider using `scipy.optimize.newton`
       to help you automatically find where text should be located,
       e.g., you know that the upper-left 40% box should be located where
       $F(x) = 100 - R(\rho_e, 100) = 0$.  However, you may simply
       place each text annotation manually.
   - *logarithmic minor tick marks*.   Note the
       original has minor tick marks spaced logarithmically, whereas
       my solution has no minor tick marks.  Hint: look
       up `plt.gca().yaxis`.
