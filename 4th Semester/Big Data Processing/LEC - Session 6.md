Class: [[COMP6579001 - Big Data Processing]]
Session: 6
Topics: 
Date: 2023-03-31
Lecturer: [[D5544 - WAWAN CENGGORO, S.Kom., M.TI]]

# NoSQL, No ACID

RDBMSs are based on ACID (Atomicity, Connsistency, Isolation, and Durability) properties

NoSQL
- Does not give importance to ACID properties
- In some cases completely ignores them

In distributed parallel systems it is difficult to ensure ACID properties (Long-running transactions don't work because keeping resources blocked for a long time is not practical)

# BASE Transactions

Acronym contrived tobe the opposite of ACID
- **B**asically **A**vailable (Even if the data is incorrect it still can be accessed)
- **S**oft state
- **E**ventually Consistent

Characteristics of BASE are
- Weak consistency - stale data OK
- Availability first
- Best effor
- Approximate answers are acceptable
- Aggresive (optimistic)
- Simpler and faster

https://arxiv.org/abs/2209.07663

# CAP Theorem

CAP Theorem stands for
- Consistency
- Availability
- Partition tolerance

![[Pasted image 20230331174439.png]]


# Batch Processing Tools

- Apache yarn
- Apache Oozie / Airflow
- Apache SOLR