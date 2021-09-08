# Assignment2-Gunaganti
###### Favourite place details
#Sowjanya Gunaganti
######India 

---

**India** is my birth place and **I had many memories with my family and friends**,coming to traditions and customs I feel awesome about them.
Thank you
directions for travelling from maryville to india
1. first, should take a ride from maryville to kansas airport 
2. should take a flight from kansas to chicago and then again take a flight from chicago to delhi.
3. from delhi,need to take a domestic flight from delhi to hyderabad
    1. take a cab and go to home
* Chocolates 
* cooldrinks
* valuable things 
**Here is the AboutMe file link**
[AboutMe](https://github.com/SowjanyaGunaganti/Assignment2-Gunaganti/blob/main/AboutMe.md)
***Here is the teddy image link**
[teddy](https://github.com/SowjanyaGunaganti/Assignment2-Gunaganti/blob/main/image.jpg)

---

##### Table creation
Below is the table details that includes 
The first column is the food/drink item.
The second column will be a location where I can get the item.
The third column is the amount of money expect to pay

| Food/Drink | Location | Amount of money |
|          ---    |     ---    |   ---:   |
| Burger    | McDonald's  | $6       |
| coco cola | Tacobell    | $2       |
| Pizza     | Domino's    | $20      |
| pepsi     | Domino's    | $3       |

---

###### Quotes I Like


 > Education is not the learning of Facts,rather it's the training of the mind to think <br> 
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;- *Albert Einstein*


  *Neil Gaiman*

 > A book is a dream you hold in your hand

 ---

 #### Code Fencing
 >The algorithm first finds the leftmost and rightmost points A and B. In the event multiple such points exist, the lowest among the left (lowest Y-coordinate) is taken as A, and the highest among the right (highest Y-coordinate) is taken as B. Clearly, A and B must both belong to the convex hull as they are the farthest away and they cannot be contained by any line formed by a pair among the given points.

Now, draw a line through AB. This divides all the other points into two sets, S1 and S2, where S1 contains all the points above the line connecting A and B, and S2 contains all the points below the line joining A and B. The points that lie on the line joining A and B may belong to either set. The points A and B belong to both sets. Now the algorithm constructs the upper set S1 and the lower set S2 and then combines them to obtain the answer.

<https://cp-algorithms.com/geometry/grahams-scan-convex-hull.html>
~~~
struct pt {
    double x, y;
};

bool cmp(pt a, pt b) {
    return a.x < b.x || (a.x == b.x && a.y < b.y);
}

bool cw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) < 0;
}

bool ccw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) > 0;
}

void convex_hull(vector<pt>& a) {
    if (a.size() == 1)
        return;

    sort(a.begin(), a.end(), &cmp);
    pt p1 = a[0], p2 = a.back();
    vector<pt> up, down;
    up.push_back(p1);
    down.push_back(p1);
    for (int i = 1; i < (int)a.size(); i++) {
        if (i == a.size() - 1 || cw(p1, a[i], p2)) {
            while (up.size() >= 2 && !cw(up[up.size()-2], up[up.size()-1], a[i]))
                up.pop_back();
            up.push_back(a[i]);
        }
        if (i == a.size() - 1 || ccw(p1, a[i], p2)) {
            while(down.size() >= 2 && !ccw(down[down.size()-2], down[down.size()-1], a[i]))
                down.pop_back();
            down.push_back(a[i]);
        }
    }

    a.clear();
    for (int i = 0; i < (int)up.size(); i++)
        a.push_back(up[i]);
    for (int i = down.size() - 2; i > 0; i--)
        a.push_back(down[i]);
}
~~~
<https://cp-algorithms.com/geometry/grahams-scan-convex-hull.html>




    