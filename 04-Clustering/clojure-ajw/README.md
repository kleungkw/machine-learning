# Contents

andrew.wood9@ntlworld.com

1. an implementation of k-means clustering in haskell
2. an implementation of hierarchical k-menas clustering in clojure
3. an implementation of DBSCAN clustering in clojure

---------------------
1. k-means clustering
---------------------

The code is developed from the demo code in

  Mena: Beginning Haskell - Chapter 6: Data Mining 

The code runs straightforwardly in the GUI Leksah 
  
  (which is quite adequate in my experience 
    - better that web reviews suggest -
    but slghtly confusing at first.)

   Workspace: Open Workspace: DM4.lksh
   Package:   Add: DM.cabal
   Package:   Clean
   Package:   Configure
   Package:   Build
   Package:   Run  (or Open Debug Window: main)

   

----------------------------------
2. hierarchical k-means clustering
----------------------------------

This is in the form of a Leiningen project.

The iris code is spun off from demo code in 

		Akhil Wali: Clojure for Machine Learning - Chapter 7: Clustering Data

In core the command:   

> (iris-hi-cluster 3) 

will gnerate thee clusters and print a report on the results.
The first run takes some time but it generates a map 
  from which other clusterings can be gnerated immediately

It prints out the results.

The results are anomalous.

> (hc/fisher-pca) 
> (hc/hi-pca)

print out 2D principal component incanter charts to check what is goin on.

The incanter code is based on:

   Eric Rochester: Clojure Data Analysis Cookbook - Chapter 10

The relevant code is in the namespace hierarchical.
The (imperfect) clustering is decided in 'closest-vectors'.
 
--------------------
3. DBSCAN clustering
--------------------

This is developed from the code on git: NeoTeo/DBScan
 amended to deal with vectors rather than single values 

From core:

(show-distances) and
(show-regions distance)

generate incanter histograms indicating the distances between points and the
number of points assocaited with each point given a specified distance.

Choosing eps and minPts On the basis of this information:

(iris-db-cluster eps minpts) generates an incanter pricipal components 2D scatter plot of 
  the resulting clustering.

(iris-db-cluster) defaults to (iris-db-cluster 0.5 15) 
 

  (db/show-distances))

; histogram

(defn show-regions [dist]
  (db/show-regions dist))



