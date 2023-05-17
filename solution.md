30 Days JS leetcode Solutions

1. Array Reduce Transformation
   [Question Link](https://leetcode.com/problems/array-reduce-transformation/?gio_link_id=nPN45jD9)

  - Approach We will implement our own reduce method.

  1. Initialize val=init
  ```for(var v of nums)
  {
      val=fn(val,v);
  }
```
  1. val is our result.
 - Complexity
  - Time complexity: O(N)
  - Space complexity: O(1)

 ```
 Solution : var reduce = function(nums, fn, init) {
    let val=init;
    for(var x of nums)
    {
        val=fn(val,x);
    }
    return val;
};
 ```

2. Create Hello World Function
    [Question Link](https://leetcode.com/problems/create-hello-world-function/?gio_link_id=QPDw0kJR)
    - Intuition Need to reture Hello World.
    - Approach Add return "Hello World" in the given function.

 - Complexity
  - Time complexity: O(1)
  - Space complexity: O(1)

 ```
 Solution : /**
 * @return {Function}
 */
var createHelloWorld = function() {
    return function(...args) {
           return "Hello World";
    }
};

/**
 * const f = createHelloWorld();
 * f(); // "Hello World"
 */
 ```

3. Counter
    [Question Link](https://leetcode.com/problems/counter/?gio_link_id=xogkVqBo)

    - Intuition 
      - n is local to createCounter function.
      - n is global to counter function.
      Since in every call we have to return n and in next call we have to
      return n+1 so what we do is we will first store value of n in temp variable and then we increase value of n by 1 and return temporary value and since n is global to counter so change in value of n will be reflect in next call (In the next call value of n will be curr value+1 and that will be our ans).
    - Approach 
      - let temp=n
      -  n+=1
 - Complexity
  - Time complexity: O(1)
  - Space complexity: O(1)

 ```
 Solution : /**
 * @param {number} n
 * @return {Function} counter
 */
var createCounter = function counter(n) {
    return function() {
           let curr=n;
           n+=1;
           return curr;
    };
};

/** 
 * const counter = createCounter(10)
 * counter() // 10
 * counter() // 11
 * counter() // 12
 */
 ``` 

4. Counter ||
    [Question Link](https://leetcode.com/problems/counter-ii/?gio_link_id=xRxVYOXo)

    - Intuition 
      - The intuition behind this code is to create a counter object that allows you to perform three actions: incrementincrementincrement the counter by 111, decrementdecrementdecrement the counter by 111, and resetresetreset the counter to its initial value.
      Since in every call we have to return n and in next call we have to
      return n+1 so what we do is we will first store value of n in temp variable and then we increase value of n by 1 and return temporary value and since n is global to counter so change in value of n will be reflect in next call (In the next call value of n will be curr value+1 and that will be our ans).

    - Approach 
      - The approach used in the code is to create a closure. The variable ansansans is declared within the createCounter()createCounter()createCounter() function and is assigned the initial value initinitinit. The returned object contains three functions that have access to this ansansans variable through closure.

      Here's an explanation of each function:

      1.increment()increment()increment(): This function increments the ansansans variable by 111 using the pre-increment operator (++)(++)(++). It returns the incremented value of ansansans.
      2.decrement()decrement()decrement(): This function decrements the ansansans variable by 111 using the pre-decrement operator (−−)(--)(−−). It returns the decremented value of ansansans.
      3.reset()reset()reset(): This function assigns the initinitinit value to the ansansans variable, effectively resetting it to its initial value. It does not return any value.

 - Complexity
  - Time complexity:
   The time complexity of the increment()increment()increment() and decrement()decrement()decrement() functions is O(1)O(1)O(1) because they only involve a single arithmetic operation. The reset()reset()reset() function also has a time   complexity of O(1)O(1)O(1) as it simply assigns a value to a variable.

  - Space complexity:
   The space complexity of the code is O(1)O(1)O(1) because it does not use any additional data structures that grow with the input. The ansansans variable and the returned object are the only variables created, and they occupy constant space regardless of the input value.

 ```
 Solution : /**
 * @param {integer} init
 * @return { increment: Function, decrement: Function, reset: Function }
 */
var createCounter = function(init) {
    //creating ans variable
    var ans = init;
    //returning object to a function
    return{
        increment: () => ++ans,
        decrement: () => --ans,
        reset: () => ans = init
    }  
};

/**
 * const counter = createCounter(5)
 * counter.increment(); // 6
 * counter.reset(); // 5
 * counter.decrement(); // 4
 */

/** 
 * const counter = createCounter(10)
 * counter() // 10
 * counter() // 11
 * counter() // 12
 */
 ```  

5. Apply Transform Over Each Element in Array
      [Question Link](https://leetcode.com/problems/apply-transform-over-each-element-in-array/?gio_link_id=noqbNOv9)

    - Intuition 
      - If go through the question in better way then we will found that we have to basically implement the predefined map method of javascript.
     
    - Approach 
      - We Implement the map method of javascript.

   - map method of javascript
    - It is an array method which is widely used for list rendering in React.
    - It take fn as arguments and calls fn(arr[i]) for each element of arr
    - It return new array of element returned by fn.
    - newArr=arr.map(fn);
    - 
 - Complexity
  - Time complexity: O(N)
  - Space complexity: O(N)

 ```
 Solution : /**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var map = function(arr, fn) {
          let newArr=[];
          for(let i=0;i<arr.length;i++)
          {
              newArr.push(fn(arr[i],i));
          }
          return newArr;
};
 ``` 

6. Filter Elements from Array
    [Question Link](https://leetcode.com/problems/filter-elements-from-array/?gio_link_id=a9a5VZr9)

    - Intuition 
      - Call fn method on each array element and if fn for current element return true then push that element into new arr.
     
    - Approach 
      - using our own filter method.

  - Time complexity: O(N)
  - Space complexity: O(N)

 ```
 Solution : /**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var filter = function(arr, fn) {
    let newArr=[];
    for(let i=0;i<arr.length;i++)
    {
        if(fn(arr[i],i))
        {
           newArr.push(arr[i]);
        }
    }
    return newArr;
};
 ``` 

7. Function Composition
[Question Link](https://leetcode.com/problems/function-composition/?gio_link_id=4PY7wZM9)

    - Intuition 
      - The compose function takes an array of functions and returns a new function that applies each function in the array, from right to left, to the input value. This is useful when we want to apply a series of transformations to some input data.
     
    - Approach 
      - The compose function first checks if the input array is empty, and returns a function that simply returns its input if it is. Otherwise, it uses the reduceRight method of the array to apply the functions in reverse order. reduceRight is used instead of reduce to ensure that the functions are applied from right to left.

  - Time complexity: O(N) , where n is the number of functions in the input array.
  - Space complexity: O(N), because it creates a new function for each function in the input array.

    - What is ReduceRight
     - reduceRight is a method available on arrays in JavaScript.
     - It works like the reduce method, but starts from the right-hand side of the array instead of the left.
     - It takes a callback function as its first argument, which takes two arguments: the accumulator and the current value.
     - The callback function is called once for each element in the array, in reverse order.

  - Here's an example code for reduceRight to explain how it works:
  
  ```
  const arr = [1, 2, 3, 4, 5];

const sum = arr.reduceRight((prev, curr) => {
  return prev + curr;
});

console.log(sum); // Output: 15
```

In this example, the reduceRight method is used to compute the sum of the elements of an array in reverse order. The function passed to reduceRight takes two arguments: prev and curr, which represent the previous accumulated result and the current element of the array, respectively.

```
 Solution :/**
 * @param {Function[]} functions
 * @return {Function}
 */
var compose = function(functions) {
	if (functions.length === 0) {
    return function(x) { return x; };
  }

  return functions.reduceRight(function(prevFn, nextFn) {
    return function(x) {
      return nextFn(prevFn(x));
    };
  });

};


const fn = compose([x => x + 1, x => 2 * x]);
console.log(fn(4)); // 9
 ``` 

8. Allow one funciton call
[Question Link](https://leetcode.com/problems/allow-one-function-call/?gio_link_id=a9By01Oo)

    - Intuition 
      - We will use a variable which handle the count of times function has been called .
      - On the basis of count ,we will return result.
     
    - Approach 
      - Declare a variable ``times`` and intialize it with zero.//This will holds number of times given function is called.
      - If ``times`` is one,fn() will be ans.
      - Else undefined will return.

  - Time complexity: O(1) 
  - Space complexity: O(1)

```
 Solution :/**
 * @param {Function} fn
 * @return {Function}
 */
var once = function(fn) {
    let times=0;
    return function(...args){
           times+=1;     
           if(times==1)
               return fn(...args);
           return undefined;
    }
};

/**
 * let fn = (a,b,c) => (a + b + c)
 * let onceFn = once(fn)
 *
 * onceFn(1,2,3); // 6
 * onceFn(2,3,6); // returns undefined without calling fn
 */
 ``` 

9. Memoize
[Question Link](https://leetcode.com/problems/allow-one-function-call/?gio_link_id=a9By01Oo)

    - Intuition 
      - Using Map in Javascript we first check wheather we compute result for corresponding parameters earliar or not , if yes then we simple return value corresponding to parameters that we have store in Map.
     
    - Approach 
      - Declare the Map , this will store value of fn(parameters) .
      ``let m=new Map()``
      - Declare callcount, this will store count of times given function has been called.
        ``callcount=0``
      - Declare the key .
        ``key="``
      - Intialize the key.
        - if Memoize of sum(a,b) is called then key will be "a+b".
        - if fact(n) is called then key will be "n".
        - if fib(n) is called then key will be "n".
      - if(m.has(key)) is true that means we have already compute it's value so no need to compute once again,simply return m.get(key).
      - Otherwise we will compute its value and store it in map.

  - Time complexity: O(Nlog(N)) 
  - Space complexity: O(N)

```
 Solution :/**
 * @param {Function} fn
 */
function memoize(fn) {
    let callcount=0;
    let Mp=new Map();
    return function(...args) {
           let key;
            key=`${args[0]}`;   
           if(args.length==2)
           {
              key+="+"+`${args[1]}`;
           }
           if(Mp.has(key))
           {
              return Mp.get(key);  
           }
           callcount+=1;
           let res=fn(...args);  
           Mp.set(key,res);
           return res;
    }
}


/** 
 * let callCount = 0;
 * const memoizedFn = memoize(function (a, b) {
 *	 callCount += 1;
 *   return a + b;
 * })
 * memoizedFn(2, 3) // 5
 * memoizedFn(2, 3) // 5
 * console.log(callCount) // 1 
 */
 ``` 


10. Curry
[Question Link](https://leetcode.com/problems/curry/?gio_link_id=QRekxgjogi )

    - Intuition 
      - The above code implements a function curry which takes in a function fn and returns a curried version of fn. A curried function is a function that takes multiple arguments one at a time, rather than taking them all at once.

      - The intuition behind currying is to make it easier to create reusable functions that can be partially applied and composed. For example, a curried function can be partially applied to some arguments to create a new function that is specialized to a specific use case.
     
    - Approach 
      - The approach of the curry function is to create a new function curried that takes in any number of arguments using the spread operator (...args). If the number of arguments passed to curried is greater than or equal to the number of arguments expected by fn, then fn is called with those arguments and the result is returned. Otherwise, curried returns a new function that takes in additional arguments using the spread operator and calls itself with the combined set of arguments.

  - Time complexity: The time complexity of the curry function is O(1), as it simply creates a new function and returns it.

  - Space complexity: The space complexity of the curry function depends on the number of arguments passed to the returned curried function. Each call to the curried function creates a new closure that captures the current set of arguments, which can potentially take up a large amount of memory if many closures are created. However, this is generally not a concern unless the curried function is called with a large number of arguments

```
 Solution :/**
 * @param {Function} fn
 * @return {Function}
 */
const curry = function(fn) {
  return function curried(...args) {
    if(args.length >= fn.length) return fn(...args)
    return (...params) => curried(...args, ...params)
  };
};

/**
 * function sum(a, b) { return a + b; }
 * const csum = curry(sum);
 * csum(1)(2) // 3
 */
 ``` 

11. Sleep
[Question Link](https://leetcode.com/problems/sleep/?gio_link_id=5Rp2Wmzo)
     
    - Approach 
      - let T=Date.now();
      - Eat five Star and Do Nothing till currTime-T+1<Millis
      - Once over , eturn anything.

   - Time complexity: O(millis)
   - Space complexity: O(1)

```



 Solution :/**
 * @param {number} millis
 */
async function sleep(millis) {
      let T=Date.now();
      while(Date.now()-T+1<millis)
      {   
            //do nothing
      }
      return Promise.resolve({});
}

/** 
 * let t = Date.now()
 * sleep(100).then(() => console.log(Date.now() - t)) // 100
 */
 ```


12. Promise Time Limit
[Question Link](https://leetcode.com/problems/promise-time-limit/?gio_link_id=nombN5Z9)

    - Intuition : The intuition behind this code is to enforce a time limit on a given function. It wraps the function in a new function that returns a promise. If the wrapped function exceeds the specified time limit, it rejects the promise with a "Time Limit Exceeded" error.
     
    - Approach 
      - The timeLimit function takes two parameters: fn, which is the function to be time-limited, and t, which is the time limit in milliseconds.
      - It returns an async function that accepts any number of arguments (...args) and returns a promise.
      - Within the returned async function, a new promise is created to handle the time limit.
      - A timeout is set using setTimeout, which will reject the promise after t milliseconds if it hasn't been resolved or rejected before that.
      - The wrapped function (fn) is invoked with the provided arguments using await.
      - If the wrapped function resolves successfully, the result is passed to resolve of the promise created in step 3.
      - If an error occurs during the execution of the wrapped function, it is caught, and the promise is rejected with the error.
      - Regardless of whether the wrapped function resolves or rejects, the timeout is cleared using clearTimeout to prevent it from triggering after the function has completed.
      - The time-limited function returns the promise.

   - Time complexity: The time complexity of this code is dependent on the time complexity of the wrapped function (fn). The time limit is enforced by setting a timeout, which doesn't affect the time complexity of the wrapped function itself. Therefore, the time complexity of the code can be considered the same as the time complexity of the wrapped function.

  - Space complexity: The space complexity of this code is determined by the memory required to store the wrapped function and the promise. Since the wrapped function and promise are created within the returned function and not stored outside, the space complexity is minimal and mainly depends on the wrapped function and its internal operations.

```
 Solution :/**
 * @param {Function} fn
 * @param {number} t
 * @return {Function}
 */
var timeLimit = function(fn, t) {
  return async function(...args) {
    return new Promise(async (resolve, reject) => {
      const timeout = setTimeout(() => {
        reject("Time Limit Exceeded");
      }, t);

      try {
        const result = await fn(...args);
        resolve(result);
      } catch(err) {
        reject(err);
      }
      clearTimeout(timeout);
    });
  };
};
/**
 * const limited = timeLimit((t) => new Promise(res => setTimeout(res, t)), 100);
 * limited(150).catch(console.log) // "Time Limit Exceeded" at t=100ms
 */
 ``` 


13. Promise Time Limit
[Question Link](https://leetcode.com/problems/promise-time-limit/?gio_link_id=nombN5Z9)

    - Intuition : The given promisePool function executes an array of asynchronous functions in parallel up to a specified concurrency level (n). It uses recursion to evaluate the functions in a depth-first manner.
     
    - Approach 
      - The promisePool function receives an array of asynchronous functions (functions) and a concurrency level (n).
      - It defines an inner evaluateNext function that performs the evaluation of the functions.
      - Within evaluateNext, the function checks if there are any functions remaining in the functions array. If not, it returns.
      - If there are remaining functions, it removes the first function from the functions array and assigns it to fn.
      - It then awaits the execution of fn() to ensure that the function completes before proceeding.
      - After fn() completes, it recursively calls evaluateNext() to evaluate the next function in the array.
      - The promisePool function creates an array of promises (nPromises) using Array(n).fill().map(evaluateNext) to initiate the parallel execution.
      - It awaits the resolution of all promises in nPromises using Promise.all(nPromises) to ensure that all functions have been executed.

   - Time complexity: The time complexity of the promisePool function depends on the number of functions (functions) and the concurrency level (n). The function uses recursion to evaluate the functions, and each function is executed once. Therefore, the time complexity is O(k), where k is the total number of functions in the functions array.

   - Space complexity: The space complexity of the promisePool function is determined by the number of functions (functions) and the concurrency level (n). The function creates an array of promises (nPromises) to track the parallel execution, which requires space proportional to the concurrency level. Additionally, the recursion depth depends on the number of functions. Therefore, the space complexity is O(max(n, k)), where n is the concurrency level and k is the total number of functions.

```
 Solution :/**
 * @param {Function[]} functions
 * @param {number} n
 * @return {Function}
 */
var promisePool = async function(functions, n) {
    async function evaluateNext() {
        if (functions.length === 0) return;
        const fn = functions.shift();
        await fn();
        await evaluateNext();
    }
    const nPromises = Array(n).fill().map(evaluateNext);
    await Promise.all(nPromises);
};

/**
 * const sleep = (t) => new Promise(res => setTimeout(res, t));
 * promisePool([() => sleep(500), () => sleep(400)], 1)
 *   .then(console.log) // After 900ms
 */
 ``` 