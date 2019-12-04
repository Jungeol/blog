---
title: csharp-linq
tag: csharp
category: csharp
date: 2019-12-04 21:40:29
---
# Linq
## FullOuterJoin
method 방식으로는 한번에 가능
```
static void Main(string[] args)
{
    var ax = new[] { 
        new { id = 1, name = "John" },
        new { id = 2, name = "Sue" } };
    var bx = new[] { 
        new { id = 1, surname = "Doe" },
        new { id = 3, surname = "Smith" } };

    ax.FullOuterJoin(bx, a => a.id, b => b.id, (a, b, id) => new {a, b})
        .ToList().ForEach(Console.WriteLine);
}
```
query 방식으로는 union method로 가능
```
var firstNames = new[]
{
    new { ID = 1, Name = "John" },
    new { ID = 2, Name = "Sue" },
};
var lastNames = new[]
{
    new { ID = 1, Name = "Doe" },
    new { ID = 3, Name = "Smith" },
};
var leftOuterJoin = from first in firstNames
                    join last in lastNames
                    on first.ID equals last.ID
                    into temp
                    from last in temp.DefaultIfEmpty(new { first.ID, Name = default(string) })
                    select new
                    {
                        first.ID,
                        FirstName = first.Name,
                        LastName = last.Name,
                    };
var rightOuterJoin = from last in lastNames
                     join first in firstNames
                     on last.ID equals first.ID
                     into temp
                     from first in temp.DefaultIfEmpty(new { last.ID, Name = default(string) })
                     select new
                     {
                         last.ID,
                         FirstName = first.Name,
                         LastName = last.Name,
                     };
var fullOuterJoin = leftOuterJoin.Union(rightOuterJoin);
```