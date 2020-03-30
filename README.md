# Stateful versus functional component perf test

## Results

### Without children

| Repetitions | Functional | Stateful  |
| ----------: | ---------: | --------: |
| 100         | ~ 4 ms     | ~ 7 ms    |
| 100000      | ~ 850 ms   | ~ 2500 ms |

### With a functional child component

| Repetitions | Functional | Stateful  |
| ----------: | ---------: | --------: |
| 100         | ~ 6 ms     | ~ 13 ms   |
| 100000      | ~ 2200 ms  | ~ 8750 ms |

### With a stateful child component

| Repetitions | Functional | Stateful  |
| ----------: | ---------: | --------: |
| 100         | ~ 10 ms    | ~ 13 ms   |
| 100000      | ~ 4000 ms  | ~ 5500 ms |

## Conclusion

- There is a visible performance benefit in using functional components.
- When functional component inserts stateful child component, the performance benefit is negligable.
- Performance hit for stateful component with functional child is surprising. I'll probably re-run the tests to make sure.

## Recommendation

- Use functional components for simple components that are displayed hundreds of times.
- When functional component needs children, make sure the children are also functional.
- If child components need to be stateful, don't bother with functional parent compnent.
