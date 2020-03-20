---
title: Metodo Load
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150727"
---
# <a name="the-load-method"></a><span data-ttu-id="0e5d8-102">Metodo Load</span><span class="sxs-lookup"><span data-stu-id="0e5d8-102">The Load Method</span></span>
<span data-ttu-id="0e5d8-103">È possibile usare il metodo <xref:System.Data.DataTable.Load%2A> per caricare un tipo <xref:System.Data.DataTable> con righe provenienti da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="0e5d8-104">Si tratta di un metodo di overload che, nella sua forma più semplice, accetta un singolo parametro, un **oggetto DataReader**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="0e5d8-105">In questo formato, carica semplicemente il **DataTable** con righe.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="0e5d8-106">Facoltativamente, è possibile specificare il parametro **LoadOption** per controllare la modalità di aggiunta dei dati all'oggetto **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="0e5d8-107">Il parametro **LoadOption** è particolarmente utile nei casi in cui il **DataTable** contiene già righe di dati, perché descrive come i dati in ingresso dall'origine dati verranno combinati con i dati già presenti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="0e5d8-108">Ad esempio, **PreserveCurrentValues** (impostazione predefinita) specifica che nei casi in cui una riga è contrassegnata come **Added** in **DataTable**, il valore **Original** o ogni colonna viene impostata sul contenuto della riga corrispondente dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="0e5d8-109">Il **valore Current** manterrà i valori assegnati quando la riga è stata aggiunta e **RowState** della riga verrà impostato su **Changed**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="0e5d8-110">Nella tabella seguente viene fornita una breve descrizione dei valori di enumerazione di <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="0e5d8-111">Valore LoadOption</span><span class="sxs-lookup"><span data-stu-id="0e5d8-111">LoadOption value</span></span>|<span data-ttu-id="0e5d8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e5d8-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="0e5d8-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="0e5d8-113">**OverwriteRow**</span></span>|<span data-ttu-id="0e5d8-114">Se le righe in arrivo hanno lo stesso valore **PrimaryKey** di una riga già presente nella **DataTable**, i valori **Original** e **Current** di ogni colonna vengono sostituiti con i valori nella riga in arrivo e la proprietà **RowState** viene impostata su **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="0e5d8-115">Le righe dell'origine dati che non esistono già nel **DataTable** vengono aggiunte con un valore **RowState** **pari a Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="0e5d8-116">Questa opzione aggiorna in effetti il contenuto del **DataTable** in modo che corrisponda al contenuto dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="0e5d8-117">**PreserveCurrentValues (impostazione predefinita)**</span><span class="sxs-lookup"><span data-stu-id="0e5d8-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="0e5d8-118">Se le righe in arrivo hanno lo stesso valore **PrimaryKey** di una riga già presente nella **DataTable**, il valore **Original** viene impostato sul contenuto della riga in ingresso e il valore **Current** non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="0e5d8-119">Se **RowState** è **Added** o **Modified**, viene impostato su **Modified**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="0e5d8-120">Se **RowState** è stato **eliminato**, rimane **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="0e5d8-121">Le righe dell'origine dati che non esistono già nel **DataTable** vengono aggiunte e **RowState** è impostato su **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="0e5d8-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="0e5d8-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="0e5d8-123">Se le righe in arrivo hanno lo stesso valore **PrimaryKey** della riga già presente in **DataTable**, il valore **Current** viene copiato nel valore **Original** e il valore **Current** viene quindi impostato sul contenuto della riga in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="0e5d8-124">Se il **RowState** nel **DataTable** è stato **aggiunto**, il **RowState** rimane **Added**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="0e5d8-125">Per le righe contrassegnate come **Modificato** o **Eliminato**, **RowState** è **Modified**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="0e5d8-126">Le righe dell'origine dati che non esistono già nel **DataTable** vengono aggiunte e **RowState** è impostato su **Added**.</span><span class="sxs-lookup"><span data-stu-id="0e5d8-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="0e5d8-127">Nell'esempio seguente viene utilizzato il **metodo Load** per visualizzare un elenco di compleanni per i dipendenti del database **Northwind.**</span><span class="sxs-lookup"><span data-stu-id="0e5d8-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0e5d8-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e5d8-128">See also</span></span>

- [<span data-ttu-id="0e5d8-129">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="0e5d8-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="0e5d8-130">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0e5d8-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
