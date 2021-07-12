# NotesAppAAC

A sample Notes app that uses Android Achitecture Components MVVM architecture.

## Diagram

![](app/src/main/res/drawable/AAC.png)

### High Level Explanation

Activity (*MainActivity.kt*) talks with *ViewModel* ->  *ViewModel* talks with *Repository* ->   *Repository* talks to *DAO* (data access object)


### Definition of the components 

#### MainActivity.kt
MainActivity.kt in this architecture is only concerned with inflating the layout manager and showing the data in the UI. It's not worrying how or where the data is coming from?

#### ViewModel
ViewModel work is to get data from repository. Whatever MainAcitivty.kt needs is accessible to ViewModel and it could provide. Activity keeps on observing the ViewModel because the data in it is LiveData.

#### LiveData
LiveData keeps tab on any update that happens on your data. It keeps on updating the activity if any change happened to your data.

#### Repository
Repository's work is only to fetch Data. Fetching of the data can be from an API or from the Data Base.

#### DAO
All the Room DB operations are handled by the DAO e.g. insert, delete, querying of data (with SQLite) happens in an interface within DAO.