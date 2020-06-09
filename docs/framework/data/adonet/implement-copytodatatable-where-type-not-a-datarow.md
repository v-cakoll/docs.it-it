---
title: 'Procedura: implementare CopyToDataTable<T> in cui il tipo generico T non un oggetto DataRow'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
ms.openlocfilehash: a1427747d03f01e52f1ee7ad1fc11d47d310edbe
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590605"
---
# <a name="how-to-implement-copytodatatablet-where-the-generic-type-t-is-not-a-datarow"></a><span data-ttu-id="3bc0e-102">Procedura: implementare CopyToDataTable\<T> in cui il tipo generico T non un oggetto DataRow</span><span class="sxs-lookup"><span data-stu-id="3bc0e-102">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>
<span data-ttu-id="3bc0e-103">L'oggetto <xref:System.Data.DataTable> viene spesso usato per l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-103">The <xref:System.Data.DataTable> object is often used for data binding.</span></span> <span data-ttu-id="3bc0e-104">Il metodo <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> copia i dati dei risultati di una query in un oggetto <xref:System.Data.DataTable> che può essere quindi usato per il data binding.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-104">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method takes the results of a query and copies the data into a <xref:System.Data.DataTable>, which can then be used for data binding.</span></span> <span data-ttu-id="3bc0e-105">I metodi <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>, tuttavia, funzionano solo su un'origine <xref:System.Collections.Generic.IEnumerable%601> in cui il parametro generico `T` è di tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-105">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> methods, however, only operate on an <xref:System.Collections.Generic.IEnumerable%601> source where the generic parameter `T` is of type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="3bc0e-106">Sebbene sia utile, questa funzionalità non consente di creare tabelle da una sequenza di tipi scalari, da query che proiettano tipo anonimi o da query che eseguono join di tabelle.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-106">Although this is useful, it does not allow tables to be created from a sequence of scalar types, from queries that project anonymous types, or from queries that perform table joins.</span></span>  
  
 <span data-ttu-id="3bc0e-107">In questo argomento viene descritto come implementare due metodi di estensione `CopyToDataTable<T>` personalizzati che accettano un parametro generico `T` di un tipo diverso da <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-107">This topic describes how to implement two custom `CopyToDataTable<T>` extension methods that accept a generic parameter `T` of a type other than <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="3bc0e-108">La logica per creare un oggetto <xref:System.Data.DataTable> da un'origine <xref:System.Collections.Generic.IEnumerable%601> è contenuto nella classe `ObjectShredder<T>`, di cui viene eseguito il wrapping in due metodi di estensione `CopyToDataTable<T>` di overload.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-108">The logic to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source is contained in the `ObjectShredder<T>` class, which is then wrapped in two overloaded `CopyToDataTable<T>` extension methods.</span></span> <span data-ttu-id="3bc0e-109">Il metodo `Shred` della classe `ObjectShredder<T>` restituisce l'oggetto <xref:System.Data.DataTable> compilato e accetta tre parametri di input: un'origine <xref:System.Collections.Generic.IEnumerable%601>, un oggetto <xref:System.Data.DataTable> e un'enumerazione <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-109">The `Shred` method of the `ObjectShredder<T>` class returns the filled <xref:System.Data.DataTable> and accepts three input parameters: an <xref:System.Collections.Generic.IEnumerable%601> source, a <xref:System.Data.DataTable>, and a <xref:System.Data.LoadOption> enumeration.</span></span> <span data-ttu-id="3bc0e-110">Lo schema iniziale dell'oggetto <xref:System.Data.DataTable> restituito è basato sullo schema del tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-110">The initial schema of the returned <xref:System.Data.DataTable> is based on the schema of the type `T`.</span></span> <span data-ttu-id="3bc0e-111">Se viene fornita una tabella esistente come input, lo schema deve essere coerente con lo schema del tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-111">If an existing table is provided as input, the schema must be consistent with the schema of the type `T`.</span></span> <span data-ttu-id="3bc0e-112">Tutte le proprietà e i campi pubblici del tipo `T` vengono convertiti in <xref:System.Data.DataColumn> nella tabella restituita.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-112">Each public property and field of the type `T` is converted to a <xref:System.Data.DataColumn> in the returned table.</span></span> <span data-ttu-id="3bc0e-113">Se la sequenza di origine contiene un tipo derivato da `T`, lo schema della tabella restituita viene espanso per includere eventuali proprietà o campi pubblici aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-113">If the source sequence contains a type derived from `T`, the returned table schema is expanded for any additional public properties or fields.</span></span>  
  
 <span data-ttu-id="3bc0e-114">Per esempi di uso dei metodi `CopyToDataTable<T>` personalizzati, vedere [Creazione di un oggetto DataTable da una query](creating-a-datatable-from-a-query-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="3bc0e-114">For examples of using the custom `CopyToDataTable<T>` methods, see [Creating a DataTable From a Query](creating-a-datatable-from-a-query-linq-to-dataset.md).</span></span>  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a><span data-ttu-id="3bc0e-115">Per implementare i metodi CopyToDataTable personalizzati \<T> nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="3bc0e-115">To implement the custom CopyToDataTable\<T> methods in your application</span></span>  
  
1. <span data-ttu-id="3bc0e-116">Implementare la classe `ObjectShredder<T>` per creare un oggetto <xref:System.Data.DataTable> da un'origine <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="3bc0e-116">Implement the `ObjectShredder<T>` class to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  

    <span data-ttu-id="3bc0e-117">Nell'esempio precedente si presuppone che le proprietà e i campi di `DataColumn` non siano tipi di valore Nullable.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-117">The preceding example assumes that the properties and fields of the `DataColumn` are not nullable value types.</span></span> <span data-ttu-id="3bc0e-118">Per gestire proprietà e campi con tipi di valore Nullable, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="3bc0e-118">To handle properties and fields with nullable value types, use the following code:</span></span>

    ```csharp
    // Nullable-aware code for properties.
    DataColumn dc = table.Columns.Contains(p.Name) ? table.Columns[p.Name] : table.Columns.Add(p.Name, Nullable.GetUnderlyingType(p.PropertyType) ?? p.PropertyType);

    // Nullable-aware code for fields.
    DataColumn dc = table.Columns.Contains(f.Name) ? table.Columns[f.Name] : table.Columns.Add(f.Name, Nullable.GetUnderlyingType(f.FieldType) ?? f.FieldType);
    ```

2. <span data-ttu-id="3bc0e-119">Implementare i metodi di estensione `CopyToDataTable<T>` personalizzati in una classe:</span><span class="sxs-lookup"><span data-stu-id="3bc0e-119">Implement the custom `CopyToDataTable<T>` extension methods in a class:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3. <span data-ttu-id="3bc0e-120">Aggiungere la classe `ObjectShredder<T>` e i metodi di estensione `CopyToDataTable<T>` all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3bc0e-120">Add the `ObjectShredder<T>` class and `CopyToDataTable<T>` extension methods to your application.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
    End Sub  
End Module  
  
Public Module CustomLINQtoDataSetMethods  
…  
End Module  
  
Public Class ObjectShredder(Of T)  
…  
End Class
```
  
```csharp
class Program  
{  
    static void Main(string[] args)  
    {  
        // Your application code using CopyToDataTable<T>.  
    }  
}  
public static class CustomLINQtoDataSetMethods  
{  
…  
}  
public class ObjectShredder<T>  
{  
…  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="3bc0e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bc0e-121">See also</span></span>

- [<span data-ttu-id="3bc0e-122">Creazione di un oggetto DataTable da una query</span><span class="sxs-lookup"><span data-stu-id="3bc0e-122">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)
- [<span data-ttu-id="3bc0e-123">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="3bc0e-123">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)
