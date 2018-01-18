---
title: Eventi di connessione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4d6a818f3173780cee2f8a01b9f66804cd2969b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="connection-events"></a>Eventi di connessione
Tutti i provider di dati .NET Framework dispongono di **connessione** oggetti con due eventi che è possibile utilizzare per recuperare i messaggi informativi da un'origine dati o per determinare se lo stato di un **connessione** è modificato. Nella tabella seguente vengono descritti gli eventi del **connessione** oggetto.  
  
|event|Descrizione|  
|-----------|-----------------|  
|**InfoMessage**|Si verifica quando un messaggio informativo viene restituito da un'origine dati. I messaggi informativi sono i messaggi di un'origine dati per cui non viene generata un'eccezione.|  
|**StateChange**|Si verifica quando lo stato del **connessione** le modifiche.|  
  
## <a name="working-with-the-infomessage-event"></a>Utilizzo dell'evento InfoMessage  
 È possibile recuperare avvisi e messaggi informativi da un'origine dati SQL Server usando l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> dell'oggetto <xref:System.Data.SqlClient.SqlConnection>. Gli errori restituiti da un'origine dati con un livello di gravità compreso tra 11 e 16 generano un'eccezione. Tuttavia, l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> consente di ottenere dall'origine dati i messaggi che non sono associati a un errore. Nel caso di Microsoft SQL Server i messaggi di errore con una gravità uguale o minore di 10 sono considerati informativi e vengono acquisiti usando l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>. Per altre informazioni, vedere l'argomento "Error Message Severity Levels" (Livelli di gravità dei messaggi di errore) nella documentazione online di SQL Server.  
  
 Il <xref:System.Data.SqlClient.SqlConnection.InfoMessage> evento riceve un <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> oggetto che contiene, nella relativa **errori** , una raccolta di messaggi dall'origine dati. È possibile eseguire una query di **errore** oggetti della raccolta per il testo di un numero e il messaggio di errore, nonché l'origine dell'errore. Il provider di dati .NET Framework per SQL Server include inoltre i dettagli sul database, sulla stored procedure e sul numero di riga da cui proviene il messaggio.  
  
### <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come aggiungere un gestore eventi per l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.  
  
```vb  
' Assumes that connection represents a SqlConnection object.  
  AddHandler connection.InfoMessage, _  
    New SqlInfoMessageEventHandler(AddressOf OnInfoMessage)  
  
Private Shared Sub OnInfoMessage(sender As Object, _  
  args As SqlInfoMessageEventArgs)  
  Dim err As SqlError  
  For Each err In args.Errors  
    Console.WriteLine("The {0} has received a severity {1}, _  
       state {2} error number {3}\n" & _  
      "on line {4} of procedure {5} on server {6}:\n{7}", _  
      err.Source, err.Class, err.State, err.Number, err.LineNumber, _  
    err.Procedure, err.Server, err.Message)  
  Next  
End Sub  
```  
  
```csharp  
// Assumes that connection represents a SqlConnection object.  
  connection.InfoMessage +=   
    new SqlInfoMessageEventHandler(OnInfoMessage);  
  
protected static void OnInfoMessage(  
  object sender, SqlInfoMessageEventArgs args)  
{  
  foreach (SqlError err in args.Errors)  
  {  
    Console.WriteLine(  
  "The {0} has received a severity {1}, state {2} error number {3}\n" +  
  "on line {4} of procedure {5} on server {6}:\n{7}",  
   err.Source, err.Class, err.State, err.Number, err.LineNumber,   
   err.Procedure, err.Server, err.Message);  
  }  
}  
```  
  
## <a name="handling-errors-as-infomessages"></a>Gestione di errori come InfoMessage  
 In genere, l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> verrà generato solo per messaggi informativi e per messaggi di avviso inviati dal server. Tuttavia, quando si verifica un errore, l'esecuzione del **ExecuteNonQuery** o **ExecuteReader** metodo che ha avviato l'operazione del server viene interrotta e viene generata un'eccezione.  
  
 Per continuare a elaborare le restanti istruzioni di un comando indipendentemente da eventuali messaggi di errore generati dal server, impostare la proprietà <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> del tipo <xref:System.Data.SqlClient.SqlConnection> su `true`. In questo modo, invece di generare un'eccezione e di interrompere l'elaborazione, la connessione genera l'evento di errore <xref:System.Data.SqlClient.SqlConnection.InfoMessage>. L'applicazione client può quindi gestire questo evento e rispondere alle condizioni di errore.  
  
> [!NOTE]
>  Un errore con un livello di gravità pari a 17 o superiore che provoca l'interruzione dell'elaborazione del comando da parte del server deve essere gestito come un'eccezione. In questo caso viene generata un'eccezione indipendentemente da come viene gestito l'errore nell'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.  
  
## <a name="working-with-the-statechange-event"></a>Utilizzo dell'evento StateChange  
 Il **StateChange** evento si verifica quando lo stato di un **connessione** le modifiche. Il **StateChange** riceve eventi <xref:System.Data.StateChangeEventArgs> che consentono di determinare la modifica dello stato del **connessione** utilizzando il **OriginalState** e **CurrentState** proprietà. Il **OriginalState** proprietà è un <xref:System.Data.ConnectionState> enumerazione che indica lo stato del **connessione** prima della modifica. **CurrentState** è un <xref:System.Data.ConnectionState> enumerazione che indica lo stato del **connessione** dopo che è stata modificata.  
  
 Nell'esempio di codice viene illustrato come utilizzare il **StateChange** evento per scrivere un messaggio nella console quando lo stato del **connessione** le modifiche.  
  
```vb  
' Assumes connection represents a SqlConnection object.  
  AddHandler connection.StateChange, _  
    New StateChangeEventHandler(AddressOf OnStateChange)  
  
Protected Shared Sub OnStateChange( _  
  sender As Object, args As StateChangeEventArgs)  
  
  Console.WriteLine( _  
  "The current Connection state has changed from {0} to {1}.", _  
  args.OriginalState, args.CurrentState)  
End Sub  
```  
  
```csharp  
// Assumes connection represents a SqlConnection object.  
  connection.StateChange  += new StateChangeEventHandler(OnStateChange);  
  
protected static void OnStateChange(object sender,   
  StateChangeEventArgs args)  
{  
  Console.WriteLine(  
    "The current Connection state has changed from {0} to {1}.",  
      args.OriginalState, args.CurrentState);  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Connessione a un'origine dati](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
