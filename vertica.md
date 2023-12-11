# Vertica Notes

## Vertica Architecture

### Basics

- Column Storage

  - reduces i/o compared to row based storage.
  - ideal for read intensive workloads.
  - In below example, column store reads only three columns while a row store would have to read all columns.
  - Example: => SELECT avg(price) FROM tickstore WHERE symbol = 'AAPL' and date = '5/31/13';
  
    <img src="https://www.vertica.com/docs/9.2.x/HTML/Content/Resources/Images/ConceptsGuide/cluster_storage.png" width=500px height=500px>

- Data Encoding and Compression

- Clustering

- Projections

- Logical and Physical Schema

- Terminology

  -  Host
  -  Instance
  -  Node
  -  Cluster
  -  Database

- Database Modes

  - Enterprise Mode:
     -  Default Vertica database mode (the only mode available until the version 9.1 release).
     -  In Enterprise Mode, the data in your database is distributed across all of the nodes in your cluster in ROS containers.
     -  Queries normally operate on data stored locally.
     -  It is best suited for constant workloads on data sets that include "hot" data (data stored within the database) and "cold" data (data stored externally, such as on a Hadoop file system).

      <img src="https://www.vertica.com/docs/9.2.x/HTML/Content/Resources/Images/Eon/enterprise-mode-basic_diagram.png" width=500px height=500px>

  - Eon Mode:
    -  Eon Mode (introduced in Vertica version 9.1) optimizes your database for scalability.
    -  It lets you dynamically adjust the number of nodes in your database based on your workload.
    -  An Eon Mode database's data is stored in a central communal repository.
    -  As the nodes do not store data, it is much easier for you to add or remove them.
    -  As all of the data is stored centrally, the nodes in the Vertica cluster do not have to spend time exchanging data to rebalance their storage when nodes join or leave the database. 
    -  Adding and removing nodes does not disturb your running queries. You can even pause the entire database and later revive it to resume running queries.
    -  Currently, Eon Mode is only available on Amazon Web Services.
      
      <img src="https://www.vertica.com/docs/9.2.x/HTML/Content/Resources/Images/Eon/eon-mode-basic_diagram.png" width=500px height=500px>
  
