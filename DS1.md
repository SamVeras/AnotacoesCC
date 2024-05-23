## Invariante de Loop

Uma invariante de loop é uma asserção lógica, uma propriedade do loop de software que é verdadeira
antes, e depois, de cada iteração.

### Coisas:

- Lista
- Fila
- Pilha
- Busca
- Ordenação
- N^2 e nlogn
- Merge sort, bubble sort
- Análise e prova:
- Theta(n)
- Invariante de loop
- Indução
- Recursão

## Introduction to Algorithms (Cormen) 2022

### 1.2 Efficiency

> [...] insertion sort, takes time roughly equal to $c_1 n^2$ to sort $n$ items, where $c_1$ is a
> constant that does not depend on $n$. That is, it takes time roughly proportional to $n^2$. The
> second, merge sort, takes time roughly equal to $c_2n\lg n$, where $\lg n$ stands for $log_2 n$
> and $c_2$ is another constant that also does not depend on $n$. Insertion sort typically has a
> smaller constant factor than merge sort, so that $c_1 < c_2$. We’ll see that the constant factors
> can have far less of an impact on the running time than the dependence on the input size $n$.
> Let’s write insertion sort’s running time as $c_1 n \cdot n$ and merge sort’s running time as $c_2
> n \cdot \lg n$. Then we see that where insertion sort has a factor of $n$ in its running time,
> merge sort has a factor of $\lg n$, which is much smaller. For example, when $n$ is $1000$, $\lg
> n$ is approximately $10$, and when $n$ is $1,000,000$, $\lg n$ is approximately only $20$.
> Although insertion sort usually runs faster than merge sort for small input sizes, once the input
> size $n$ becomes large enough, merge sort’s advantage of $\lg n$ versus $n$ more than compensates
> for the difference in constant factors. No matter how much smaller $c_1$ is than $c_2$, there is
> always a crossover point beyond which merge sort is faster. (p.12)

### 2.1 Insertion Sort

> [...] Insertion sort works the way you might sort a hand of playing cards. Start with an empty
> left hand and the cards in a pile on the table. Pick up the ûrst card in the pile and hold it with
> your left hand. Then, with your right hand, remove one card at a time from the pile, and insert it
> into the correct position in your left hand. As Figure 2.1 illustrates, you find the correct
> position for a card by comparing it with each of the cards already in your left hand, starting at
> the right and moving left. As soon as you see a card in your left hand whose value is less than or
> equal to the card you’re holding in your right hand, insert the card that you’re holding in your
> right hand just to the right of this card in your left hand. If all the cards in your left hand
> have values greater than the card in your right hand, then place this card as the leftmost card in
> your left hand. At all times, the cards held in your left hand are sorted, and these cards were
> originally the top cards of the pile on the table. (p.18)

> ```C++
> for i = 2 to n
>   key = A[i]
>   // Insert A[i] into the sorted subarray A[i:i-1]
>   j = i - 1
>   while j > 0 and A[j] > key
>     A[j+1] = A[j]
>     j = j - 1
>   A[j+1] = key
> ```
>
> (p.19)

> [...] At the beginning of each iteration of the **for** loop, which is indexed by $i$ , the
> **_subarray_** (a contiguous portion of the array) consisting of elements $A[1:i-1]$ (that is,
> $A[1]$ through $A[i-1]$) constitutes the currently sorted hand, and the remaining subarray
> $A[i+1:n]$ (elements $A[i+1]$ through $A[n]$) corresponds to the pile of cards still on the table.
> In fact, elements $A[1:i-1]$ are the elements _originally_ in positions $1$ through $i-1$, but now
> in sorted order. We state these properties of $A[i:i-1]$ formally as a **_loop invariant_**:
>
> > At the start of each iteration of the **for** loop of lines 1-8, the subarray $A[i:i-1]$
> > consists of the elements originally in $A[i:i-1]$, but in sorted order.
>
> Loop invariants help us understand why an algorithm is correct. When you’re using a loop
> invariant, you need to show three things:
>
> - **Initialization**: It is true prior to the ûrst iteration of the loop.
> - **Maintenance**: If it is true before an iteration of the loop, it remains true before the next
>   iteration.
> - **Termination**: The loop terminates, and when it terminates, the invariant usually along with
>   the reason that the loop terminated gives us a useful property that helps show that the
>   algorithm is correct. (p.20)

> A loop-invariant proof is a form of mathematical induction, where to prove that a property holds,
> you prove a base case and an inductive step. Here, showing that the invariant holds before the
> first iteration corresponds to the base case, and showing that the invariant holds from iteration
> to iteration corresponds to the inductive step.
>
> The third property is perhaps the most important one, since you are using the loop invariant to
> show correctness. Typically, you use the loop invariant along with the condition that caused the
> loop to terminate. (p.20)

> **Initialization**: We start by showing that the loop invariant holds before the first loop
> iteration, when $i = 2$. The subarray A[1:i-1] consists of just the single element A[1], which is
> in fact the original element in A[1]. Moreover, this subarray is sorted (after all, how could a
> subarray with just one value not be sorted?), which shows that the loop invariant holds prior to
> the ûrst iteration of the loop.
>
> **Maintenance**: Next, we tackle the second property: showing that each iteration maintains the
> loop invariant. Informally, the body of the **for** loop works by moving the values in $A[i-1]$,
> $A[i-2]$, $A[i-3]$, and so on by one position to the right until it finds the proper position for
> $A[i]$ (lines 4-7), at which point it inserts the value of $A[i]$ (line 8). The subarray $A[1:i]$
> then consists of the elements originally in $A[1:i]$, but in sorted order. **_Incrementing_** $i$
> (increasing its value by $1$) for the next iteration of the **for** loop then preserves the loop
> invariant. A more formal treatment of the second property would require us to state and show a
> loop invariant for the **while** loop of lines 5-7. Let’s not get bogged down in such formalism
> just yet. Instead, we’ll rely on our informal analysis to show that the second property holds for
> the outer loop.
>
> **Termination**: Finally, we examine loop termination. The loop variable $i$ starts at 2 and
> increases by $1$ in each iteration. Once $i$’s value exceeds $n$ in line 1, the loop terminates.
> That is, the loop terminates once $i$ equals $n + 1$. Substituting $n + 1$ for $i$ in the wording
> of the loop invariant yields that the subarray $A[i:n]$ consists of the elements originally in
> $A[1:n]$, but in sorted order. Hence, the algorithm is correct. (p.21)
