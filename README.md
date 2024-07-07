
# LINQ Nedir? 

## Giriş

LINQ (Language Integrated Query), C# dilinde veri kaynaklarına sorgular yazmak için kullanılan güçlü bir araçtır. LINQ, SQL'e benzer bir sözdizimi kullanarak koleksiyonlar, XML belgeleri, veritabanları ve daha fazlası üzerinde sorgular yapmanıza olanak tanır. Bu rehber, LINQ'yi yeni başlayanlar için açıklayacak ve temel kullanım örneklerini gösterecektir.

## LINQ'nin Temel Kavramları

### 1. Sorgu ve Yürütme
LINQ sorguları, veri kaynakları üzerinde işlem yapmanın bir yoludur. Sorgular, yürütülene kadar tanımlandıkları biçimde kalır. Bu, "deferred execution" olarak bilinir. Sorgular genellikle `IEnumerable<T>` veya `IQueryable<T>` arayüzlerini kullanır.

### 2. Sorgu Sözdizimi
LINQ sorguları, iki farklı şekilde yazılabilir: Sorgu sözdizimi (query syntax) ve method sözdizimi (method syntax).

**Sorgu Sözdizimi:**
```csharp
int[] numbers = { 2, 5, 10, 8, 6, 7 };
var evenNumbers = from num in numbers
                  where num % 2 == 0
                  select num;

foreach (var num in evenNumbers)
{
    Console.WriteLine(num);
}
```

**Method Sözdizimi:**
```csharp
int[] numbers = { 2, 5, 10, 8, 6, 7 };
var evenNumbers = numbers.Where(num => num % 2 == 0);

foreach (var num in evenNumbers)
{
    Console.WriteLine(num);
}
```

### 3. LINQ Operatörleri
LINQ, veri kaynakları üzerinde çeşitli işlemler yapmanızı sağlayan birçok yerleşik operatöre sahiptir. Bu operatörler arasında `Where`, `Select`, `OrderBy`, `GroupBy`, `Join` ve daha fazlası bulunur.

**Örnek - `Where` Operatörü:**
```csharp
string[] names = { "Ali", "Ayşe", "Ahmet", "Elif" };
var namesStartingWithA = names.Where(name => name.StartsWith("A"));

foreach (var name in namesStartingWithA)
{
    Console.WriteLine(name);
}
```

## LINQ'nin Faydaları

- **Konsolidasyon:** Farklı veri kaynaklarına erişim için tek bir sorgu dili sağlar.
- **Kolay Okunabilirlik:** SQL'e benzer yapısıyla okunması ve yazılması kolaydır.
- **Tip Güvenliği:** Derleme zamanında hata kontrolü yaparak daha güvenli kod yazmanızı sağlar.

## Sıkça Sorulan Sorular

### LINQ Hangi Veri Kaynaklarıyla Çalışır?
LINQ, diziler, koleksiyonlar, XML, veritabanları (Entity Framework ile) ve daha birçok veri kaynağıyla çalışabilir.

### LINQ ile SQL Arasındaki Farklar Nelerdir?
- **Kapsam:** LINQ sadece veritabanları değil, her tür veri kaynağıyla çalışabilir.
- **Dil Entegrasyonu:** LINQ, C# dili ile tamamen entegredir ve C#'ın tüm özelliklerinden yararlanabilir.

## Sonuç

LINQ, veri kaynakları üzerinde etkili ve okunabilir sorgular yazmanıza olanak tanıyan güçlü bir araçtır. Bu rehber, LINQ'nin temel kavramlarını ve kullanımını açıklamayı amaçladı. Daha ileri seviye kullanımlar ve örnekler için resmi [Microsoft dokümantasyonuna](https://docs.microsoft.com/tr-tr/dotnet/csharp/programming-guide/concepts/linq/) göz atabilirsiniz.
