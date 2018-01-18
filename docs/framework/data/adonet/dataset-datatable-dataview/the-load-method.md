---
title: Metodo Load
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a54eda8d96468d4506a5f7dafc342fa5ff128c2a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="the-load-method"></a><span data-ttu-id="ec0f7-102">Metodo Load</span><span class="sxs-lookup"><span data-stu-id="ec0f7-102">The Load Method</span></span>
<span data-ttu-id="ec0f7-103">È possibile usare il metodo <xref:System.Data.DataTable.Load%2A> per caricare un tipo <xref:System.Data.DataTable> con righe provenienti da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="ec0f7-104">Si tratta di un metodo di overload che, nella sua forma più semplice, accetta un solo parametro, un **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="ec0f7-105">In questo modulo, viene semplicemente caricata la **DataTable** con righe.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="ec0f7-106">Facoltativamente, è possibile specificare il **LoadOption** parametro per controllare come aggiungere i dati per il **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="ec0f7-107">Il **LoadOption** parametro è particolarmente utile nei casi in cui il **DataTable** già contiene righe di dati, perché viene descritto come i dati provenienti dai file di dati vengono combinati con i dati già nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="ec0f7-108">Ad esempio, **PreserveCurrentValues** (predefinito) specifica che nei casi in cui una riga è contrassegnata come **Added** nel **DataTable**, **originale** valore o ogni colonna è impostato per il contenuto della riga corrispondente dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="ec0f7-109">Il **corrente** valore manterrà i valori assegnati quando la riga è stata aggiunta e **RowState** della riga verrà impostato su **Changed**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="ec0f7-110">Nella tabella seguente viene fornita una breve descrizione dei valori di enumerazione di <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="ec0f7-111">Valore LoadOption</span><span class="sxs-lookup"><span data-stu-id="ec0f7-111">LoadOption value</span></span>|<span data-ttu-id="ec0f7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec0f7-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="ec0f7-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="ec0f7-113">**OverwriteRow**</span></span>|<span data-ttu-id="ec0f7-114">Se le righe in arrivo presentano lo stesso **PrimaryKey** valore di una riga già presente nella **DataTable**, **originale** e **corrente** i valori di ogni colonna vengono sostituiti con i valori della riga in arrivo e **RowState** è impostata su **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="ec0f7-115">Le righe dall'origine dati che non esistono già nel **DataTable** vengono aggiunti con una **RowState** valore **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="ec0f7-116">Questa opzione attiva aggiorna il contenuto del **DataTable** in modo che corrisponda il contenuto dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="ec0f7-117">**PreserveCurrentValues (impostazione predefinita)**</span><span class="sxs-lookup"><span data-stu-id="ec0f7-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="ec0f7-118">Se le righe in arrivo presentano lo stesso **PrimaryKey** valore di una riga già presente nella **DataTable**, **originale** è impostato per il contenuto della riga in arrivo e il **Corrente** valore non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="ec0f7-119">Se il **RowState** è **Added** o **Modified**, viene impostato su **Modified**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="ec0f7-120">Se il **RowState** stato **Deleted**, rimane **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="ec0f7-121">Le righe dall'origine dati che non esistono già nel **DataTable** vengono aggiunti e **RowState** è impostato su **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="ec0f7-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="ec0f7-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="ec0f7-123">Se le righe in arrivo presentano lo stesso **PrimaryKey** valore come la riga già presente nella **DataTable**, **corrente** valore viene copiato il **originale**valore e **corrente** valore viene quindi impostato per il contenuto della riga in arrivo.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="ec0f7-124">Se il **RowState** nel **DataTable** è stata **Added**, **RowState** rimane **aggiunto**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="ec0f7-125">Per le righe contrassegnate come **Modified** o **Deleted**, **RowState** è **Modified**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="ec0f7-126">Le righe dall'origine dati che non sono già presenti nel **DataTable** vengono aggiunti e **RowState** è impostato su **aggiunto**.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="ec0f7-127">L'esempio seguente usa il **carico** metodo per visualizzare un elenco delle date di nascita dei dipendenti nel **Northwind** database.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec0f7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec0f7-128">See Also</span></span>  
 [<span data-ttu-id="ec0f7-129">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="ec0f7-129">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="ec0f7-130">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="ec0f7-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
