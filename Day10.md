### Day10 栈与队列01

## 232. Implement Queue using Stacks (用栈实现队列)
> **Tags**: [`#栈与队列`](/search?q=栈与队列)
为了实现队列 first in first out（先入先出）的功能，需要使用两个栈来实现，一个负责入。另一个负责出，而在python中需要使用 list的 append()和pop()来模拟栈.其中实现队列的 pop()功能比较巧妙，并不需要将请放进out中的元素再放回in，只需要写一个判断，如果out为空则将in中的元素pop进out中，因为除了push意外的所有操作都只需要使用哦out，一旦元素被push进in，后面的所有其余操作都只在out中发生。

## 225. Implement Stack using Queues (用队列实现栈)
> **Tags**: [`#栈与队列`](/search?q=栈与队列)
首先想到了使用一个队列来模拟栈的方法，代码和思路都比较简单。值得注意的是推荐使用deque来作为队列使用，因为其append() 和 popleft() 都是 O(1) 复杂度，不需要移动其他元素。而且Python 的 deque 允许你通过 d[0] 直接访问队首元素，这就完美解决了没有 peek 的问题。

## 20. Valid Parentheses (有效的括号)
> **Tags**: [`#栈与队列`](/search?q=栈与队列)
我的做法是使用deque模拟一个栈，将s中的字符逐个放入队列中，直到栈顶顶元素可以和s的下一个元素能够组合为一个括号，就对栈做 pop()，如果最终栈为空，则证明所有的括号都被正确匹配了。但是需要注意一半python中使用list来表示栈会比deque更好。随后看了讲解，发现其思路虽然跟我比较相似，但更为巧妙，高效。在写代码时我们要思考目前的写法是否会导致一些本可以提前被判False的行为被运行。

## 1047. Remove All Adjacent Duplicates In String（删除字符串中的所有相邻重复项）
> **Tags**: [`#栈与队列`](/search?q=栈与队列)
本题我采取的方法和上一道题最初我的方法一致，或者说似乎更适合这道题，并且改方法与讲解使用的方法一致。
