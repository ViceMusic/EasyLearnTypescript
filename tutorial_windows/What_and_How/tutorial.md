# What and How 

In this tutorial, I will tell you what is ts and the relationship with javascript. Then we will talk about the usage of ts.

Firstly, what and why? we select Typescript.

Depended on the method of running a program, code languages are divided into two types: compiled language and interpreted language.

These names are strangerous? Right? So let look how to run them so that we can understand these ailas.

* compiled languages usually will be compiled and turned into a target file(in chinese environment, we call it "intermediate file"), and run this target file. Although this process include sequences of complex tasks, we focus on the result of compliance and name it as "compiled". On the other hand, compiled language means its original code file can not be directly executed. 

* interpreted language executing process not includes target file, and original file can be executed directly. On early notion of this type of language, code had been executed sequentially row by row, without pre-checking like type check.

Typical compiled languages consist of c++ etc.

Another type includes javascript, python

> 📕NOTICE： Nowadays，many languages begin to mix features across interpret and compile. We can discuss further at later time 😀

> ❓In fact, Many languages can compile and create target files automatically thouth they are regarded as interpreted language. For instance, Javascript used to be executed directly can be compiled into machine code(although without checking) by V8 engine(used in some famous software such as Node.js).

For typescipt, it can not be executed directly, to some extent, some people argue that it isn't a programing language. Acturlly, typescript is a normalization of javascript, with type and compile pre checking.

And Why we call it compiled language while javascript is regarded as interpreted language? We can execute a javascript file by Node.js runtime or brower's core(both in V8). And if you want to launch a project written by typescript, you need to turn this project into javascript. Like below 😛:

```
// this terminal code may be not useful, we will explain this situation in below.

tsc index.ts
node index.js
```

In this section, we want not to concentrate on how to write TS instead of the methods and processes how to run a project.

Are you ready😊?

## 1.How to install typescript🧐

we have various methods to deal with it.

**choice 1: domestical install**

If you just execute a typescript file in a local file, you can install the tsc compiler by this order:

```
npm init    #if you have not node_modules
npm -i typescript
```

Then you can convert you ts file into a js file. 

**choice 2: global install**

This is a unsuggested method that you need to set you environment in computer. you can install it by npm, or install original respority. 

## 2. How to use typescipt?

### 2.1 compile a js by youself

In this path， you can see a special file named "tsc.cmd". This is a footscrpit written by me and you can executor it:

```
./tsc --version  # show the version of ts compiler
./tsc index.js   # this file will be compiled into ts file.
```

In this folder, you can write a typescript file and try to compile it. 

### 2.2 if you can execute tsc in other paths?

Of course! Click tsc.cmd. you will see this codes:

```
@echo off
../../node_modules/.bin/tsc %*
```

I want not to explain how to write a windows script, but just tell you the loctaion of tsc and how to use it.

And , what can we do if we haven't this script in other project or folders? Please use this order:

```
npx tsc 
```

npx is a convenient order provided by npm, it can locate some libraries of node_module in this object.

## 3. what happened in this process

as you learn behind, you can run this order and I prepared a ts file.

```
./tsc index.ts
```

It will be compiled into a js file with same name. But in terminal window, maybe you can see this:

```
../../../../../node_modules/@types/node/globals.d.ts:126:13 - error TS2403: Subsequent variable declarations must have the same type.  Variable 'AbortSignal' must be of type '{ new (): AbortSignal; prototype: AbortSignal; abort(reason?: any): AbortSignal; any(signals: AbortSignal[]): AbortSignal; timeout(milliseconds: number): AbortSignal; }', but here has type '{ new (): AbortSignal; prototype: AbortSignal; abort(reason?: any): AbortSignal; timeout(milliseconds: number): AbortSignal; }'.

126 declare var AbortSignal: {
                ~~~~~~~~~~~

  ../../node_modules/typescript/lib/lib.dom.d.ts:2606:13
    2606 declare var AbortSignal: {
                     ~~~~~~~~~~~
    'AbortSignal' was also declared here.


Found 1 error in ../../../../../node_modules/@types/node/globals.d.ts:126
```

Don't worry, this is normal. The reason causing this error is type checking. We will explain it in next sections. In a word, this notice is unharmful.

if you are reluctant to see this， please try this：

```
npx tsc --skipLibCheck
```