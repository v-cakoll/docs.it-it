---
title: Metodo Load
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 82f840ab7dd26a4888ebf024d696f2c70701eb18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607232"
---
# <a name="the-load-method"></a>Metodo Load
È possibile usare il metodo <xref:System.Data.DataTable.Load%2A> per caricare un tipo <xref:System.Data.DataTable> con righe provenienti da un'origine dati. Si tratta di un metodo di overload che, nella sua forma più semplice, accetta un singolo parametro, un **DataReader**. In questo formato, viene semplicemente caricata la **DataTable** con le righe. Facoltativamente, è possibile specificare il **LoadOption** parametro per controllare come si aggiungono dati alle **DataTable**.  
  
 Il **LoadOption** parametro è particolarmente utile nei casi in cui le **DataTable** già contiene righe di dati, perché descrive il modo in cui in ingresso dei dati dall'origine dati verrà combinato con i dati già nella tabella. Ad esempio, **PreserveCurrentValues** (predefinito) specifica che nei casi in cui una riga è contrassegnata come **Added** nel **DataTable**, il **originale** valore di ciascuna colonna è impostato sul contenuto della riga corrispondente dall'origine dati. Il **correnti** valore manterrà i valori assegnati quando la riga è stata aggiunta e il **RowState** della riga verrà impostato su **Changed**.  
  
 Nella tabella seguente viene fornita una breve descrizione dei valori di enumerazione di <xref:System.Data.LoadOption>.  
  
|Valore LoadOption|Descrizione|  
|----------------------|-----------------|  
|**OverwriteRow**|Se le righe in arrivo presentano lo stesso **PrimaryKey** valore come una riga già presente nella **DataTable**, il **originale** e **corrente** i valori della ognuno colonna vengono sostituiti con i valori nella riga in ingresso e il **RowState** è impostata su **Unchanged**.<br /><br /> Le righe dall'origine dati che non sono già presenti nel **DataTable** vengono aggiunti con un **RowState** pari a **Unchanged**.<br /><br /> Questa opzione attiva aggiorna il contenuto del **DataTable** in modo che corrisponda il contenuto dell'origine dati.|  
|**PreserveCurrentValues (impostazione predefinita)**|Se le righe in arrivo presentano lo stesso **PrimaryKey** valore come una riga già presente nella **DataTable**, il **originale** valore viene impostato sul contenuto della riga in arrivo e il **Correnti** valore non viene modificato.<br /><br /> Se il **RowState** viene **Added** oppure **Modified**, è impostato su **Modified**.<br /><br /> Se il **RowState** era **Deleted**, rimane **Deleted**.<br /><br /> Le righe dall'origine dati che non sono già presenti nel **DataTable** vengono aggiunti e il **RowState** è impostata su **Unchanged**.|  
|**UpdateCurrentValues**|Se le righe in arrivo presentano lo stesso **PrimaryKey** valore come la riga già presente nella **DataTable**, il **corrente** valore viene copiato il **originale**valore e il **corrente** valore viene quindi impostato sul contenuto della riga in arrivo.<br /><br /> Se il **RowState** nel **DataTable** era **Added**, il **RowState** rimane **Added**. Per le righe contrassegnate come **Modified** oppure **Deleted**, il **RowState** è **Modified**.<br /><br /> Le righe dall'origine dati che non esistono già nel **DataTable** vengono aggiunti e il **RowState** è impostata su **Added**.|  
  
 L'esempio seguente usa il **Load** per visualizzare un elenco delle date di nascita dei dipendenti nel metodo il **Northwind** database.  
  
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

- [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
