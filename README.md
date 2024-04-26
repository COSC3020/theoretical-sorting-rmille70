[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/9YUeXH71)
# Theoretical Sorting

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.

Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.

Add your answers to this markdown file.

## Response

I would test this claim by getting some number lists of size n and recording the algorithms average runtime with those lists. Then I would repeat the process several times with lists of size Sn (where S is some positive scalar). If for each batch of lists of sized Sn, $averageRuntime(listsOfSize(Sn)) \approx S*averageRuntime(listsOfSize(n))$ and the algorithm sorts all of the lists correctly, it would then be indicative of an $O(n)$ complexity. I would however be extremely skeptical of any sorting algorithm claiming to have $O(n)$ complexity. I would predict the charted runtimes to be fairly different for different permutations of a given list. The reason I would be skeptical of sorting algorithm claiming $O(n)$ complexity is because for every comparison based sorting algorithm, in order to sort every permutation of a list the binary tree tracking the comparisons (e.i. $arr[i] < arr[i+1] \implies left; else \implies right$ ) must have a depth of at least $\log(n!).$ This essentially means our worst case scenario of a comparison based sorting algorithm is bounded by $\Omega(n\log(n))$ In this case, $O(n)$ would violate this theoretical bound.