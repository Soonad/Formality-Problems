# Formality Problems

Clone this repository and edit `Answers.fm`!

## Solving problems

TL;DR; The following commands will help you
- `fm -t Answers` - Check all started and solved answers
- `fm -t Answers/@` - Will check all problems and emit error (hole found) for missing answers (good to keep track of your progress)
- `fm -t Answers/{term}` - Will check only one term, good for checking one problem, where `{term}` is the term name, such as `get_pred`

All answers are already created on `Answers.fm` but they are filled with holes (`?`).

### Starting a new problem

1. Choose the problem you want to work on and find it on the `Answers.fm`. It should have a `?` on the body.
2. Uncomment the lines on the `main` type (something like `, :ProblemName`)
3. Uncomment the lines on the `main` body (something like `, problem_name`)
4. Run `fm -t Answers`. You should get a hole error.
5. Solve the problem.

> Why not just run `fm -t Answers/problem_name`?

There are 3 reasons for that:

- Sometimes is useful to change the type signature from `: ProblemName` to the expanded form of it, so you can, for example, add `case` on the arguments to get all those benefits. Or just to have the type there to check it. That would mean you could mess up the type and not solve the problem, since we are adding on `main` with the type there, we'll have that type checking as well.
- It helps having a checkin of which problems you started/solved.
- If there is a bug on the problem (a missing erasure annotation or something like that) and people update this repo with the fix you can easily run `fm -t Answers` and check all previous problems to ensure the solutions are up to date.

## Creating Problems

1. Add required definitions to `@Definitions.fm` (support types and functions)
2. Add a type defining the problem to `@Problems.fm`
3. Change the default `Answers.fm` to:
    - Create a default solution placeholder with hole and type annotation (as shown below)
    - Add a line to the type of the main with `, :ProblemName`
    - Add a line to the body of the main with `, problem_name`
    - Try to keep the same order position as within the `@Problems.fm`

Example default problem solution placeholder
```
// ProblemName
problem_name : ProblemName
  ?
```