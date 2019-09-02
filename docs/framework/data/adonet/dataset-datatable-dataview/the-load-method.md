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
# <a name="the-load-method"></a>Metodo Load
È possibile usare il metodo <xref:System.Data.DataTable.Load%2A> per caricare un tipo <xref:System.Data.DataTable> con righe provenienti da un'origine dati. Si tratta di un metodo di overload che, nella sua forma più semplice, accetta un solo parametro, un **DataReader**. In questo formato, viene semplicemente caricato il **DataTable** con righe. Facoltativamente, è possibile specificare il parametro **LoadOption** per controllare la modalità di aggiunta dei dati alla **DataTable**.  
  
 Il parametro **LoadOption** è particolarmente utile nei casi in cui la **DataTable** contiene già righe di dati, in quanto descrive il modo in cui i dati in arrivo dall'origine dati verranno combinati con i dati già presenti nella tabella. Ad esempio, **PreserveCurrentValues** (impostazione predefinita) specifica che nei casi in cui una riga è contrassegnata come **aggiunta** nella **DataTable**, il valore **originale** o ogni colonna viene impostata sul contenuto della riga corrispondente dall'origine dati. Il valore **corrente** manterrà i valori assegnati al momento dell'aggiunta della riga e il valore di **RowState** della riga verrà impostato su **Changed**.  
  
 Nella tabella seguente viene fornita una breve descrizione dei valori di enumerazione di <xref:System.Data.LoadOption>.  
  
|Valore LoadOption|DESCRIZIONE|  
|----------------------|-----------------|  
|**OverwriteRow**|Se le righe in ingresso hanno lo stesso valore **PrimaryKey** di una riga già presente nella **DataTable**, i valori **originali** e **correnti** di ogni colonna vengono sostituiti con i valori nella riga in arrivo e la proprietà **RowState** è impostata su Non **modificato**.<br /><br /> Le righe dell'origine dati che non esistono già nella **DataTable** vengono aggiunte con un valore di **RowState** invariato.<br /><br /> Questa opzione attiva l'aggiornamento del contenuto della **DataTable** in modo che corrisponda al contenuto dell'origine dati.|  
|**PreserveCurrentValues (impostazione predefinita)**|Se le righe in ingresso hanno lo stesso valore **PrimaryKey** di una riga già presente nella **DataTable**, il valore **originale** viene impostato sul contenuto della riga in arrivo e il valore **corrente** non viene modificato.<br /><br /> Se **RowState** viene **aggiunto** o **modificato**, viene impostato su **modified**.<br /><br /> Se il **RowState** è stato **eliminato**, rimane **eliminato**.<br /><br /> Vengono aggiunte le righe dell'origine dati che non esistono già nella **DataTable** e **RowState** viene impostato su Unchanged.|  
|**UpdateCurrentValues**|Se le righe in ingresso hanno lo stesso valore **PrimaryKey** della riga già presente nella **DataTable**, il valore **corrente** viene copiato nel valore **originale** e il valore **corrente** viene quindi impostato sul contenuto della riga in arrivo.<br /><br /> Se è stato **aggiunto il valore** **RowState** nella **DataTable** , il valore di **RowState** rimane **aggiunto**. Per le righe contrassegnate come **modificate** o eliminate, **RowState** viene **modificato**.<br /><br /> Vengono aggiunte le righe dell'origine dati che non esistono già nella **DataTable** e l'oggetto **RowState** è impostato su **added**.|  
  
 Nell'esempio seguente viene utilizzato il metodo **Load** per visualizzare un elenco di compleanni per i dipendenti nel database **Northwind** .  
  
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
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
