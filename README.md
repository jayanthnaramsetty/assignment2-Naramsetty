# assignment2-Naramsetty

# Jayanth Naramsetty

###### My favorite location in the world is Maldives

The Maldives is an island country known for its **rich water estate**. A tropical asylum of white sand sea shores, **The Maldives is situated in the Indian Ocean south of Sri Lanka** and is great water adventure , honeymoon, or leisure holiday.

***

# Directions From Maryville To Maldives

1. Take a cab from Maryville to kansas airport
2. From kansas airport take a flight to Dallas airport
3. Take a direct flight From Dallas to Male [capital city of maldives]
    1. When you landed in male you will be through ship to you destinations resorts or island which ever we booked


- Beach shirts
- All currency credit card
- DSLR camera
    - Long lens
    - Short lens
- Sunscreen lotion
- Beach vollyball
- Shades

![USA FLAG](images/usaflag.png)

[Link AboutMe](https://github.com/jayanthnaramsetty/assignment2-Naramsetty/blob/07d40a1da4b5a801ae63de973935fde861f9005b/AboutMe.md)

***

## recommendations

Below table contains the food items with their mentioned with their prices  and avalible location.

| Food Items | Location | Price | 
| :---: | :---: | :---: | 
| Tuna Fry | Male Island | $ 15  |
| Bis keemiya | Biyadhoo Island | $ 25 |
| Garudhiya | Fihalhohi Island | $ 30 |
| Huni roshi | Vaadhoo Island | $20|

***

## Pithy Quotes

> "I don’t need it to be easy, I need it to be worth it."  *Lil Wayne*

> "The time is always right to do what is right." *Martin Luther King Jr*

> "When words fail, music speaks."  *Shakespeare*

***

## Code Fencing

> The rank of a matrix is the largest number of linearly independent rows/columns of the matrix. The rank is not only defined for square matrices. The rank of a matrix can also be defined as the largest order of any non-zero minor in the matrix.

[Click](https://cp-algorithms.com/linear_algebra/rank-matrix.html)

[Click](https://cp-algorithms.com/linear_algebra/rank-matrix.html)

const double EPS = 1E-9;  
  
int compute_rank(vector<vector<double>> A) {  
    int n = A.size();  
    int m = A[0].size();  
  
    int rank = 0;  
    vector<bool> row_selected(n, false);  
    for (int i = 0; i < m; ++i) {  
        int j;  
        for (j = 0; j < n; ++j) {  
            if (!row_selected[j] && abs(A[j][i]) > EPS)  
                break;  
        }  
  
        if (j != n) {  
            ++rank;  
            row_selected[j] = true;  
            for (int p = i + 1; p < m; ++p)  
                A[j][p] /= A[j][i];  
            for (int k = 0; k < n; ++k) {  
                if (k != j && abs(A[k][i]) > EPS) {  
                    for (int p = i + 1; p < m; ++p)  
                        A[k][p] -= A[j][p] * A[k][i];  
                }  
            }  
        }  
    }  
    return rank;  
}  