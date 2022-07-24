---
title: The Hunt Rages On
date: 2022-07-24 11:48
---

<!-- markdownlint-disable -->

I have shifted down into overdrive my job hunt. Not only am I enrolled to start a technical prep course through <a href="https://codepath.com">CodePath.com</a> but I am following an Udemy <a href="https://www.udemy.com/course/python-for-data-structures-algorithms-and-interviews/">course</a> that not only helping be more comfortable with Python but also has given me great tips for job interviews and how to organize my job hunt.

Since I have been getting insta-rejected I decided to make some changes to my personal site and resume, hoping that could make a difference.

Besides these changes I have also subscribed for a <a href="https://lockheedmartin.com/en-us/index.html/">Lockeed Martin</a> hiring event, coming up the following week, and for a Tech Career Fair at FIU this coming September.

I need to keep this energy, if anything, I need to pump it up.

For the CodePath program I had to take a <a href="https://www.hackerrank.com">HackerRank</a> assessment. This consisted of 9 questions: 6 multiple choice, which were pretty easy, and 3 coding problems (which were also pretty easy). The programming language to choose was either Java (7 or 8) and Python3. The one coding problem that I feel somewhat ashamed that took me too long to solve was to merge two sorted lists, though I have solved this problem several times before (Java, Go, and even F#(script)). I haven't coded in Java in a little while and hanker rank likes to use the List/ArrayList Java Collection (granted, it is easier to work with).

The problem was solved but my solution was, well, embarrassing. I just used one pointer variable to traverse through BOTH sorted list and added to the new List an element of List1 then from List2 or vice versa depending of the condition (in ascending order). I then flushed both Lists added any remaining elements to the new List. I then called the `Arrays.sort()` sort function. This was ALL unnecessary! As soon as I submitted the assessment I thought of the TWO POINTER SOLUTION. Basically the same, but I would have 1 pointer `i` traversing `List1` and another pointer `j` traversing `List2`. In a `while` loop (as long as (`i < List1.size() && j < List2.size()`) I tested the condition: `List1.get(i) <= List2.get(j)`. If so, then I'd add the element at `List1.get(i)` to the new list and move the `i` pointer forward. Otherwise, I'd add the element at `List2.get(j)` to the new list and move the `j` pointer forward. Once I break from `while` loop (once `i >= List1.size() OR j >= List2.size()`) then I'd flush both lists (if there are elements on either lists then just add them to new list). Then I'd return the new list. That's IT.

<pre><code class="container language-java">static List&lt;Integer&gt; mergeList(List&lt;Integer&gt; nums1, List&lt;Integer&gt; nums2){

        int i = 0, j = 0;

        List&lt;Integer&gt; resultList = new ArrayList<>();
        
        while (i < nums1.size() && j < nums2.size()){
            
            if (nums1.get(i) <= nums2.get(j)){
                resultList.add(nums1.get(i));
                i++;
            }else{
                resultList.add(nums2.get(j));
                j++;
            }
        }
        
        while (i < nums1.size()){
            resultList.add(nums1.get(i));
            i++;
        }
        
        while(j < nums2.size()){
            resultList.add(nums2.get(j));
            j++;
        }
        
        return resultList;
    }</code></pre>
