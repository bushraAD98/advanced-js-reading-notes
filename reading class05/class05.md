# Reading subjects :
|Subject|
|:--------------------|
|Big O notation|
|Linked List|


********
# Big O notation :
notation is used to describe the efficiency of an algorithm or function. This efficiency is evaluated based on 2 factors:

Running Time (also known as time efficiency / complexity)
The amount of time a function needs to complete.

Memory Space (also known as space efficiency / complexity)
The amount of memory resources a function uses to store data and instructions.

## the big o depends in 4 majour keys :

- nput Size
- Units of Measurement
- Orders of Growth
- Best Case, Worst Case, and Average Case

the more these keys are increased the more complexity of time & memory increases.

*********

# Linked List : 

a linked list is data structure that contains nodes that links/points to the next node in the list.

it have 2 types :

1- singly linked list : in this type the navigation is forward only.
2- doubly linked list : here the forward an backward navigation is possible


mainlly the linked list consist of nodes in each node we have 2 parts, the first part is the actual data that is inside the node
and the second part is the address of the next node in the list we call this part (next) which will help us alot when dealing with the nodes & data inside it .

now since each node has the addres of the next node inside it how we can reach the first node?
simply by a pointer we called it Head it is only for the first node.

In JavaScript, a linked list looks like this:

const list = {
    head: {
        value: 6
        next: {
            value: 10                                             
            next: {
                value: 12
                next: {
                    value: 3
                    next: null	
                    }
                }
            }
        }
    }
};




