---
title: Metodo Load
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 06666e069f20bc06f303c4e829d1c69c185a8a84
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602481"
---
# <a name="the-load-method"></a><span data-ttu-id="ae211-102">Metodo Load</span><span class="sxs-lookup"><span data-stu-id="ae211-102">The Load Method</span></span>
<span data-ttu-id="ae211-103">È possibile usare il metodo <xref:System.Data.DataTable.Load%2A> per caricare un tipo <xref:System.Data.DataTable> con righe provenienti da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ae211-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="ae211-104">Si tratta di un metodo di overload che, nella sua forma più semplice, accetta un singolo parametro, un **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="ae211-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="ae211-105">In questo formato, viene semplicemente caricata la **DataTable** con le righe.</span><span class="sxs-lookup"><span data-stu-id="ae211-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="ae211-106">Facoltativamente, è possibile specificare il **LoadOption** parametro per controllare come si aggiungono dati alle **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="ae211-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="ae211-107">Il **LoadOption** parametro è particolarmente utile nei casi in cui le **DataTable** già contiene righe di dati, perché descrive il modo in cui in ingresso dei dati dall'origine dati verrà combinato con i dati già nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ae211-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="ae211-108">Ad esempio, **PreserveCurrentValues** (predefinito) specifica che nei casi in cui una riga è contrassegnata come **Added** nel **DataTable**, il **originale** valore di ciascuna colonna è impostato sul contenuto della riga corrispondente dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ae211-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="ae211-109">Il **correnti** valore manterrà i valori assegnati quando la riga è stata aggiunta e il **RowState** della riga verrà impostato su **Changed**.</span><span class="sxs-lookup"><span data-stu-id="ae211-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="ae211-110">Nella tabella seguente viene fornita una breve descrizione dei valori di enumerazione di <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="ae211-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="ae211-111">Valore LoadOption</span><span class="sxs-lookup"><span data-stu-id="ae211-111">LoadOption value</span></span>|<span data-ttu-id="ae211-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae211-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="ae211-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="ae211-113">**OverwriteRow**</span></span>|<span data-ttu-id="ae211-114">Se le righe in arrivo presentano lo stesso **PrimaryKey** valore come una riga già presente nella **DataTable**, il **originale** e **corrente** i valori della ognuno colonna vengono sostituiti con i valori nella riga in ingresso e il **RowState** è impostata su **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="ae211-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="ae211-115">Le righe dall'origine dati che non sono già presenti nel **DataTable** vengono aggiunti con un **RowState** pari a **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="ae211-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="ae211-116">Questa opzione attiva aggiorna il contenuto del **DataTable** in modo che corrisponda il contenuto dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ae211-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="ae211-117">**PreserveCurrentValues (impostazione predefinita)**</span><span class="sxs-lookup"><span data-stu-id="ae211-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="ae211-118">Se le righe in arrivo presentano lo stesso **PrimaryKey** valore come una riga già presente nella **DataTable**, il **originale** valore viene impostato sul contenuto della riga in arrivo e il **Correnti** valore non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="ae211-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="ae211-119">Se il **RowState** viene **Added** oppure **Modified**, è impostato su **Modified**.</span><span class="sxs-lookup"><span data-stu-id="ae211-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="ae211-120">Se il **RowState** era **Deleted**, rimane **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="ae211-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="ae211-121">Le righe dall'origine dati che non sono già presenti nel **DataTable** vengono aggiunti e il **RowState** è impostata su **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="ae211-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="ae211-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="ae211-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="ae211-123">Se le righe in arrivo presentano lo stesso **PrimaryKey** valore come la riga già presente nella **DataTable**, il **corrente** valore viene copiato il **originale**valore e il **corrente** valore viene quindi impostato sul contenuto della riga in arrivo.</span><span class="sxs-lookup"><span data-stu-id="ae211-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="ae211-124">Se il **RowState** nel **DataTable** era **Added**, il **RowState** rimane **Added**.</span><span class="sxs-lookup"><span data-stu-id="ae211-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="ae211-125">Per le righe contrassegnate come **Modified** oppure **Deleted**, il **RowState** è **Modified**.</span><span class="sxs-lookup"><span data-stu-id="ae211-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="ae211-126">Le righe dall'origine dati che non esistono già nel **DataTable** vengono aggiunti e il **RowState** è impostata su **Added**.</span><span class="sxs-lookup"><span data-stu-id="ae211-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="ae211-127">L'esempio seguente usa il **Load** per visualizzare un elenco delle date di nascita dei dipendenti nel metodo il **Northwind** database.</span><span class="sxs-lookup"><span data-stu-id="ae211-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ae211-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae211-128">See also</span></span>
- [<span data-ttu-id="ae211-129">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="ae211-129">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="ae211-130">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="ae211-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
