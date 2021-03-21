Select p.ProductName As [Ürün Adı], Sum(p.UnitPrice*od.Quantity) As [Kazanılan Toplam Miktar]
From ((Products As p 
Inner Join [Order Details] As od On p.ProductID=od.ProductID)
Inner Join Orders As o On o.OrderID=od.OrderID)
Group By ProductName
Order By ProductName
