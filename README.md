# Simulating-Buffer-Management-Strategies

Objective:
The objective of the given project is to simulate a buffer pool that can be used for simple Join/Selection queries on a few small tables. The buffer pool supports buffer manager strategies like LRU/MRU/CLOCK blocks. The main purpose of the project is to compare the performance of these buffer manager strategies in terms of the number of disk I/O operations required. By simulating different buffer manager strategies and analysing their performance, this project aims to provide insights into the most efficient way of managing buffers for small tables in a database system.

Assumptions:
Only one block is transferred in one disk i/o
Size of block in buffer pool is same as size of block in page file
We assumed the block (or page) size 
All records of a table are in single page file
Considered only simple selection and join queries for this simulation 
Join query contains only two tables

Methodology:
SQLite was used to find the number of blocks (or pages ) in a table ( a page file)

Processing of Simple selection query:	

          for each block i of instructor do

                    Load i into buffer pool

          end

Processing of Simple Join query:				
          
          for each block i of instructor do

              Load i into buffer pool and pin, if already present just  pin 
    
              for each block d of department do
    
                  Load d into buffer pool  and pin, if already present  and pin	
        
              end 
          end
