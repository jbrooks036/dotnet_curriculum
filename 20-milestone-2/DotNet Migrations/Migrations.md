# Migrations

### Migrations Setup
https://gist.github.com/jcockhren/4d58d603920c39f29f45
[Migrations_Setup.md]
    1. From the menu, Go to Tools -> NuGet Package Manager -> Package Manager Console
    2. Follow Steps in commits to ready project for migrations [ https://github.com/NashvilleSoftwareSchool/jitter-juniper/compare/625cb9f9a339e243fb1d3c3a1f03d3d301cb9c60...103d40c?diff=split&name=103d40c ]
    `PM> Enable-Migrations -ContextTypeName` Jitter.Models.JitterContext
      This only ever needs to be done once (do not need to redo for scorched earth)
    3. In order to Create an initial migration :
	`PM> Add-Migration InitialCreate`
    4. To apply that migration:
	`PM> Update-Database`

### Initial Migration
https://gist.github.com/jcockhren/243d76d925d51abcb3df [instructions.md]
    1. `Update-Database -TargetMigration $InitialDatabase` (Deletes all tables in database, but keeps Database file)
    2. If you have a file with the name "InitialCreate1" delete it. If it's not there, no worries.
    3. `Add-Migration InitialCreate` (re-create InitialCreate migration file with your new model's changes)
    4. `Update-Database` (now apply the newly created migration)

### Adding a Migration
    0. Make any necessary changes to your model
    1. `Add-Migration <NameForNewMigration>` ('NameForNewMigration' should reflect your new model's changes)
    2. `Update-Database` (now apply the newly created migration)

### To Re-Create Database File ("Scorched Earth")
https://gist.github.com/jcockhren/d92140ce675e0b62fa4f  [database_file_recreate.md]
    1. Go to your project and right-Click on App_Data Then select Open in File Explorer
    2. In your Server Explorer, under Data Connections, delete both connections (DefaultConnection and Jitter.mdf)
    3. Delete the Database FILES in the directory from #1.
    4. In your Package Manager Console Run -> Update-Database


************
#### Microsoft Data Developer Website on Code-First Migrations

* https://msdn.microsoft.com/en-us/data/jj591621.aspx#generating
