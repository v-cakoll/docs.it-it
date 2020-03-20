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
# <a name="the-load-method"></a>Metodo Load
È possibile usare il metodo <xref:System.Data.DataTable.Load%2A> per caricare un tipo <xref:System.Data.DataTable> con righe provenienti da un'origine dati. Si tratta di un metodo di overload che, nella sua forma più semplice, accetta un singolo parametro, un **oggetto DataReader**. In questo formato, carica semplicemente il **DataTable** con righe. Facoltativamente, è possibile specificare il parametro **LoadOption** per controllare la modalità di aggiunta dei dati all'oggetto **DataTable**.  
  
 Il parametro **LoadOption** è particolarmente utile nei casi in cui il **DataTable** contiene già righe di dati, perché descrive come i dati in ingresso dall'origine dati verranno combinati con i dati già presenti nella tabella. Ad esempio, **PreserveCurrentValues** (impostazione predefinita) specifica che nei casi in cui una riga è contrassegnata come **Added** in **DataTable**, il valore **Original** o ogni colonna viene impostata sul contenuto della riga corrispondente dell'origine dati. Il **valore Current** manterrà i valori assegnati quando la riga è stata aggiunta e **RowState** della riga verrà impostato su **Changed**.  
  
 Nella tabella seguente viene fornita una breve descrizione dei valori di enumerazione di <xref:System.Data.LoadOption>.  
  
|Valore LoadOption|Descrizione|  
|----------------------|-----------------|  
|**OverwriteRow**|Se le righe in arrivo hanno lo stesso valore **PrimaryKey** di una riga già presente nella **DataTable**, i valori **Original** e **Current** di ogni colonna vengono sostituiti con i valori nella riga in arrivo e la proprietà **RowState** viene impostata su **Unchanged**.<br /><br /> Le righe dell'origine dati che non esistono già nel **DataTable** vengono aggiunte con un valore **RowState** **pari a Unchanged**.<br /><br /> Questa opzione aggiorna in effetti il contenuto del **DataTable** in modo che corrisponda al contenuto dell'origine dati.|  
|**PreserveCurrentValues (impostazione predefinita)**|Se le righe in arrivo hanno lo stesso valore **PrimaryKey** di una riga già presente nella **DataTable**, il valore **Original** viene impostato sul contenuto della riga in ingresso e il valore **Current** non viene modificato.<br /><br /> Se **RowState** è **Added** o **Modified**, viene impostato su **Modified**.<br /><br /> Se **RowState** è stato **eliminato**, rimane **Deleted**.<br /><br /> Le righe dell'origine dati che non esistono già nel **DataTable** vengono aggiunte e **RowState** è impostato su **Unchanged**.|  
|**UpdateCurrentValues**|Se le righe in arrivo hanno lo stesso valore **PrimaryKey** della riga già presente in **DataTable**, il valore **Current** viene copiato nel valore **Original** e il valore **Current** viene quindi impostato sul contenuto della riga in ingresso.<br /><br /> Se il **RowState** nel **DataTable** è stato **aggiunto**, il **RowState** rimane **Added**. Per le righe contrassegnate come **Modificato** o **Eliminato**, **RowState** è **Modified**.<br /><br /> Le righe dell'origine dati che non esistono già nel **DataTable** vengono aggiunte e **RowState** è impostato su **Added**.|  
  
 Nell'esempio seguente viene utilizzato il **metodo Load** per visualizzare un elenco di compleanni per i dipendenti del database **Northwind.**  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Manipolazione di dati in un oggetto DataTable](manipulating-data-in-a-datatable.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
