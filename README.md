# Universal stemming algorithm according to the CSE morphological model

Main concept of lexicon-free stemming on CSE-model of morphology is next. In first to find an assumed ending of maximum length for the given word, which will be two symbols less than the length of the word; it is assumed that the stem cannot contain less than two symbols. The assumed ending of given word is searched in a list of endings. If the assumed ending not found in the list of endings, then one decreases the length of the assumed ending.  Accordingly, the assumed ending of the word is decreased by one symbol on the left side, and this symbol is added to the assumed stem of the word. The received ending is searched again in the list of endings until the stemming procedure is complete or the word has no ending.

In the following, e(w) is the ending of analysed word w, st(w) is the stem of w, L(w) is the length of w, L[e(w)] is the calculated length of the ending.

The steps of the algorithm for splitting the stem and ending are as follows.

1. Calculation L(w).

2. Calculation the maximum length of an ending of the analyzed word: L[e(w)] = L(w) – 2, where 2 is the minimum length of the word stem.

3. Selection of the ending e(w) of the length L[e(w)] for analyzed word w.

4.  Seach e(w) on matching with the ending from the list of endings. If it matches, then the stem of the word is determined: st(w) = w – e(w). Go to step 7.

5. Otherwise, the calculated length of the ending of the analyzed word is decreased by one: L[e(w)] = L[e(w)] - 1.

6. If L[e(w)] < 1, then word w is without the ending. Go to step 7. Otherwise, go to step 3.

7. End.