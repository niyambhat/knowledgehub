---
sidebar_position: 2
---

# Most used 

https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli

1. How to connect ASP app to PostgreSql?

Install these packages, 
Microsoft.EntityFrameworkCore, Npgsql.EntityFrameworkCore.PostgreSQL


Create  Data folder,
Inside add a class, 
```
using System;
using Microsoft.EntityFrameworkCore;

namespace BulkyWeb.Data
{
	public class ApplicationDbContext : DbContext
	{
		public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options) : base(options)
		{
		
		}
	}
}

```

Then on appsettings json, use this format and add db creds,
```
"ConnectionStrings": {
    "DefaultConnection": "User ID=uxb0gug9ylnc3hocbqbl;Password=p1FMnyYrLuX3fbuuKLrt9nrqX3dRSg;Server=bopfkcyzvl3yabnmihc8-postgresql.services.clever-cloud.com;Port=5432;Database=bopfkcyzvl3yabnmihc8;Integrated Security=true;Pooling=true;"
}
```

Then on Program.cs,
```
using Microsoft.EntityFrameworkCore;
using Npgsql.EntityFrameworkCore.PostgreSQL;
builder.Services.AddControllersWithViews();
builder.Services.AddEntityFrameworkNpgsql().AddDbContext<ApplicationDbContext>(opt => opt.UseNpgsql(builder.Configuration.GetConnectionString("DefaultConnection")));

```

Creatig Modal,

```

```


Creating Table using DbSet,
```
using System;
using BulkyWeb.Models;
using Microsoft.EntityFrameworkCore;

namespace BulkyWeb.Data
{
	public class ApplicationDbContext : DbContext
	{
		public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options) : base(options)
		{
		
		}

		public DbSet<Category> Categories { get; set }
	}
}


```


Accesing the db from the controler,
