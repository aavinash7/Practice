# Vertica Notes

## Vertica Architecture

### Basics

- Column Storage

  - reduces i/o compared to row based storage.
  - ideal for real intensive workloads.
  - Example: => SELECT avg(price) FROM tickstore WHERE symbol = 'AAPL' and date = '5/31/13';
  
  <img src="https://www.vertica.com/docs/9.2.x/HTML/Content/Resources/Images/ConceptsGuide/cluster_storage.png" width=250px height=250px>
