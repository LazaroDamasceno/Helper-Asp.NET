# Helper-Asp.NET

## Adding packages

```
Install-Package Microsoft.EntityFrameworkCore;
Install-Package Microsoft.EntityFrameworkCore.Tools;
Install-Package Microsoft.EntityFrameworkCore.Design;
Install-Package Microsoft.EntityFrameworkCore.Sqlite;
```

## Setting SQLITE and the DbSets

```
using Microsoft.EntityFrameworkCore;
using v1.BookBorrows;
using v1.Books;
using v1.Borrowers;

namespace v1;

public class AppDbContext : DbContext
{

    public DbSet<Borrower> Borrowers { get; set; }
    public DbSet<Book> Books { get; set; }
    public DbSet<BookBorrow> BookBorrows { get; set; }

    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        optionsBuilder.UseSqlite("DataSource=mydb;Cache=Shared");
    }
}
```
