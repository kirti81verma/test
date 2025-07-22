1.

Scaffold-DbContext "Server=DESKTOP-QSI2HBS\SQLEXPRESS;Database=studentdb1;Trusted_Connection=True;TrustServerCertificate=True;" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Models


2. "ConnectionStrings": {
   "db": "Server=DESKTOP-QSI2HBS\\SQLEXPRESS; Database=hospital; trusted_Connection=true; TrustServerCertificate=true"
 },


3.   var provider = builder.Services.BuildServiceProvider();
   var config = provider.GetRequiredService<IConfiguration>();
   builder.Services.AddDbContext<HospitalContext>(items => items.UseSqlServer(config.GetConnectionString("db")));


1.Scaffold-DbContext "server=localhost;port=3306;user=root;password=@Kirti12345;database=studentdb" Pomelo.EntityFrameworkCore.MySql -OutputDir Models -f


2. "ConnectionStrings": {
   "DefaultConnection": "server=localhost;port=3306;user=root;password=@Kirti12345;database=studentdb"
 },


3.builder.Services.AddDbContext<StudentDbContext>(options =>
    options.UseMySql(builder.Configuration.GetConnectionString("DefaultConnection"),
    new MySqlServerVersion(new Version(8, 0, 36)))); // Change version as per your MySQL
