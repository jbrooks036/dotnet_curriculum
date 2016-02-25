# Migrations

### Migrations Setup
https://gist.github.com/jcockhren/4d58d603920c39f29f45
[Migrations_Setup.md]
  1. From the menu, Go to `Tools -> NuGet Package Manager -> Package Manager Console`
  2. Follow Steps in commits to ready project for migrations [ https://github.com/NashvilleSoftwareSchool/jitter-juniper/compare/625cb9f9a339e243fb1d3c3a1f03d3d301cb9c60...103d40c?diff=split&name=103d40c ] and then:

    `PM> Enable-Migrations -ContextTypeName ProjectName.Models.ProjectNameContext`

      where "ProjectName" is your project's name.  
      N.B.  This step only ever needs to be done once (do not need to redo for scorched earth below)
  3. In order to Create an initial migration :
	`PM> Add-Migration InitialCreate`
  4. To apply that migration:
	`PM> Update-Database`

### Initial Migration
https://gist.github.com/jcockhren/243d76d925d51abcb3df [instructions.md]
  1. `PM> Update-Database -TargetMigration $InitialDatabase` (Deletes all tables in database, but keeps Database file)
  2. If you have a file with the name `InitialCreate1` delete it. If it's not there, no worries.
  3. `PM> Add-Migration InitialCreate` (re-create `InitialCreate` migration file with your new model's changes)
  4. `PM> Update-Database` (apply the newly created migration)

### Adding a Migration
  0. Make any necessary changes to your model
  1. `PM> Add-Migration NameForNewMigration` ('NameForNewMigration' should reflect your new model's changes)
  2. `PM> Update-Database` (apply the newly created migration)

### To Completely Re-Create Database File
This "scorched earth" approach may be necessary when all else fails, since Visual Studio has some glitches wrt migrations.

https://gist.github.com/jcockhren/d92140ce675e0b62fa4f  [database_file_recreate.md]
  1. In Server Explorer, under your `Data Connections`, delete both connections (`DefaultConnection` and `ProjectName.mdf`)
  2. Go to your project and right-Click on `App_Data`, then select `Open in File Explorer`.  
  3. Delete the Database FILES in the directory from #1, and copy the full path at the top of the `File Explorer` onto your clipboard.
  4. In Server Explorer right click on `Data Connections` and select `Add Connection`.  In the open field for `Database File Name`, paste the path from your clipboard and append the name of your project at the end of that path.  Click `OK`.
  5. In Package Manager Console, run
  `PM> Update-Database`


************
### Additional Resources
* Microsoft Data Developer Website on Code-First Migrations
 * https://msdn.microsoft.com/en-us/data/jj591621.aspx#generating
