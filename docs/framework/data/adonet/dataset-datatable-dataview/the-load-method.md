---
title: Metodo Load
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 04defffc724875e691fd7b87331c28e6b6c0cd28
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758308"
---
# <a name="the-load-method"></a>Metodo Load
È possibile usare il metodo <xref:System.Data.DataTable.Load%2A> per caricare un tipo <xref:System.Data.DataTable> con righe provenienti da un'origine dati. Si tratta di un metodo di overload che, nella sua forma più semplice, accetta un solo parametro, un **DataReader**. In questo modulo, viene semplicemente caricata la **DataTable** con righe. Facoltativamente, è possibile specificare il **LoadOption** parametro per controllare come aggiungere i dati per il **DataTable**.  
  
 Il **LoadOption** parametro è particolarmente utile nei casi in cui il **DataTable** già contiene righe di dati, perché viene descritto come i dati provenienti dai file di dati vengono combinati con i dati già nella tabella. Ad esempio, **PreserveCurrentValues** (predefinito) specifica che nei casi in cui una riga è contrassegnata come **Added** nel **DataTable**, **originale** valore o ogni colonna è impostato per il contenuto della riga corrispondente dall'origine dati. Il **corrente** valore manterrà i valori assegnati quando la riga è stata aggiunta e **RowState** della riga verrà impostato su **Changed**.  
  
 Nella tabella seguente viene fornita una breve descrizione dei valori di enumerazione di <xref:System.Data.LoadOption>.  
  
|Valore LoadOption|Descrizione|  
|----------------------|-----------------|  
|**OverwriteRow**|Se le righe in arrivo presentano lo stesso **PrimaryKey** valore di una riga già presente nella **DataTable**, **originale** e **corrente** i valori di ogni colonna vengono sostituiti con i valori della riga in arrivo e **RowState** è impostata su **Unchanged**.<br /><br /> Le righe dall'origine dati che non esistono già nel **DataTable** vengono aggiunti con una **RowState** valore **Unchanged**.<br /><br /> Questa opzione attiva aggiorna il contenuto del **DataTable** in modo che corrisponda il contenuto dell'origine dati.|  
|**PreserveCurrentValues (impostazione predefinita)**|Se le righe in arrivo presentano lo stesso **PrimaryKey** valore di una riga già presente nella **DataTable**, **originale** è impostato per il contenuto della riga in arrivo e il **Corrente** valore non viene modificato.<br /><br /> Se il **RowState** è **Added** o **Modified**, viene impostato su **Modified**.<br /><br /> Se il **RowState** stato **Deleted**, rimane **Deleted**.<br /><br /> Le righe dall'origine dati che non esistono già nel **DataTable** vengono aggiunti e **RowState** è impostato su **Unchanged**.|  
|**UpdateCurrentValues**|Se le righe in arrivo presentano lo stesso **PrimaryKey** valore come la riga già presente nella **DataTable**, **corrente** valore viene copiato il **originale**valore e **corrente** valore viene quindi impostato per il contenuto della riga in arrivo.<br /><br /> Se il **RowState** nel **DataTable** è stata **Added**, **RowState** rimane **aggiunto**. Per le righe contrassegnate come **Modified** o **Deleted**, **RowState** è **Modified**.<br /><br /> Le righe dall'origine dati che non sono già presenti nel **DataTable** vengono aggiunti e **RowState** è impostato su **aggiunto**.|  
  
 L'esempio seguente usa il **carico** metodo per visualizzare un elenco delle date di nascita dei dipendenti nel **Northwind** database.  
  
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
 [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
