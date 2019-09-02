---
title: Metodo Load
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: b704deeffcd06bca09b6c26d60a66218b46fc55c
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203164"
---
# <a name="the-load-method"></a><span data-ttu-id="95075-102">Metodo Load</span><span class="sxs-lookup"><span data-stu-id="95075-102">The Load Method</span></span>
<span data-ttu-id="95075-103">È possibile usare il metodo <xref:System.Data.DataTable.Load%2A> per caricare un tipo <xref:System.Data.DataTable> con righe provenienti da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="95075-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="95075-104">Si tratta di un metodo di overload che, nella sua forma più semplice, accetta un solo parametro, un **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="95075-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="95075-105">In questo formato, viene semplicemente caricato il **DataTable** con righe.</span><span class="sxs-lookup"><span data-stu-id="95075-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="95075-106">Facoltativamente, è possibile specificare il parametro **LoadOption** per controllare la modalità di aggiunta dei dati alla **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="95075-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="95075-107">Il parametro **LoadOption** è particolarmente utile nei casi in cui la **DataTable** contiene già righe di dati, in quanto descrive il modo in cui i dati in arrivo dall'origine dati verranno combinati con i dati già presenti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="95075-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="95075-108">Ad esempio, **PreserveCurrentValues** (impostazione predefinita) specifica che nei casi in cui una riga è contrassegnata come **aggiunta** nella **DataTable**, il valore **originale** o ogni colonna viene impostata sul contenuto della riga corrispondente dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="95075-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="95075-109">Il valore **corrente** manterrà i valori assegnati al momento dell'aggiunta della riga e il valore di **RowState** della riga verrà impostato su **Changed**.</span><span class="sxs-lookup"><span data-stu-id="95075-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="95075-110">Nella tabella seguente viene fornita una breve descrizione dei valori di enumerazione di <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="95075-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="95075-111">Valore LoadOption</span><span class="sxs-lookup"><span data-stu-id="95075-111">LoadOption value</span></span>|<span data-ttu-id="95075-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="95075-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="95075-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="95075-113">**OverwriteRow**</span></span>|<span data-ttu-id="95075-114">Se le righe in ingresso hanno lo stesso valore **PrimaryKey** di una riga già presente nella **DataTable**, i valori **originali** e **correnti** di ogni colonna vengono sostituiti con i valori nella riga in arrivo e la proprietà **RowState** è impostata su Non **modificato**.</span><span class="sxs-lookup"><span data-stu-id="95075-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="95075-115">Le righe dell'origine dati che non esistono già nella **DataTable** vengono aggiunte con un valore di **RowState** invariato.</span><span class="sxs-lookup"><span data-stu-id="95075-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="95075-116">Questa opzione attiva l'aggiornamento del contenuto della **DataTable** in modo che corrisponda al contenuto dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="95075-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="95075-117">**PreserveCurrentValues (impostazione predefinita)**</span><span class="sxs-lookup"><span data-stu-id="95075-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="95075-118">Se le righe in ingresso hanno lo stesso valore **PrimaryKey** di una riga già presente nella **DataTable**, il valore **originale** viene impostato sul contenuto della riga in arrivo e il valore **corrente** non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="95075-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="95075-119">Se **RowState** viene **aggiunto** o **modificato**, viene impostato su **modified**.</span><span class="sxs-lookup"><span data-stu-id="95075-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="95075-120">Se il **RowState** è stato **eliminato**, rimane **eliminato**.</span><span class="sxs-lookup"><span data-stu-id="95075-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="95075-121">Vengono aggiunte le righe dell'origine dati che non esistono già nella **DataTable** e **RowState** viene impostato su Unchanged.</span><span class="sxs-lookup"><span data-stu-id="95075-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="95075-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="95075-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="95075-123">Se le righe in ingresso hanno lo stesso valore **PrimaryKey** della riga già presente nella **DataTable**, il valore **corrente** viene copiato nel valore **originale** e il valore **corrente** viene quindi impostato sul contenuto della riga in arrivo.</span><span class="sxs-lookup"><span data-stu-id="95075-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="95075-124">Se è stato **aggiunto il valore** **RowState** nella **DataTable** , il valore di **RowState** rimane **aggiunto**.</span><span class="sxs-lookup"><span data-stu-id="95075-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="95075-125">Per le righe contrassegnate come **modificate** o eliminate, **RowState** viene **modificato**.</span><span class="sxs-lookup"><span data-stu-id="95075-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="95075-126">Vengono aggiunte le righe dell'origine dati che non esistono già nella **DataTable** e l'oggetto **RowState** è impostato su **added**.</span><span class="sxs-lookup"><span data-stu-id="95075-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="95075-127">Nell'esempio seguente viene utilizzato il metodo **Load** per visualizzare un elenco di compleanni per i dipendenti nel database **Northwind** .</span><span class="sxs-lookup"><span data-stu-id="95075-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.   
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="95075-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95075-128">See also</span></span>

- [<span data-ttu-id="95075-129">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="95075-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="95075-130">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="95075-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
