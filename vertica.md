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
     -  Enterprise Mode is less scalable than Eon Mode, it is harder to add nodes to or remove nodes from an Enterprise Mode database. 
     -  When adding or removing nodes, Vertica must redistribute the locally-stored data between the nodes.
     -  Enterprise Mode has more platform options than Eon Mode. 
     -  You can use Enterprise Mode in any environment that Vertica supports: locally installed or co-located hardware, virtual machines, or in one of the major vendor's clouds (Amazon AWS, Google Cloud Platform, or Microsoft Azure).

      <img src="https://www.vertica.com/docs/9.2.x/HTML/Content/Resources/Images/Eon/enterprise-mode-basic_diagram.png" width=500px height=500px>
  
