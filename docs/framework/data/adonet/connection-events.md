---
title: Eventi di connessione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: 719e529c7813679f1e927b66e7db0e110714e438
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758158"
---
# <a name="connection-events"></a><span data-ttu-id="e4d4c-102">Eventi di connessione</span><span class="sxs-lookup"><span data-stu-id="e4d4c-102">Connection Events</span></span>
<span data-ttu-id="e4d4c-103">Tutti i provider di dati .NET Framework dispongono di **connessione** oggetti con due eventi che è possibile utilizzare per recuperare i messaggi informativi da un'origine dati o per determinare se lo stato di un **connessione** è modificato.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-103">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="e4d4c-104">Nella tabella seguente vengono descritti gli eventi del **connessione** oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-104">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="e4d4c-105">event</span><span class="sxs-lookup"><span data-stu-id="e4d4c-105">Event</span></span>|<span data-ttu-id="e4d4c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4d4c-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4d4c-107">**InfoMessage**</span><span class="sxs-lookup"><span data-stu-id="e4d4c-107">**InfoMessage**</span></span>|<span data-ttu-id="e4d4c-108">Si verifica quando un messaggio informativo viene restituito da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-108">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="e4d4c-109">I messaggi informativi sono i messaggi di un'origine dati per cui non viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-109">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|<span data-ttu-id="e4d4c-110">**StateChange**</span><span class="sxs-lookup"><span data-stu-id="e4d4c-110">**StateChange**</span></span>|<span data-ttu-id="e4d4c-111">Si verifica quando lo stato del **connessione** le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-111">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="e4d4c-112">Utilizzo dell'evento InfoMessage</span><span class="sxs-lookup"><span data-stu-id="e4d4c-112">Working with the InfoMessage Event</span></span>  
 <span data-ttu-id="e4d4c-113">È possibile recuperare avvisi e messaggi informativi da un'origine dati SQL Server usando l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> dell'oggetto <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-113">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="e4d4c-114">Gli errori restituiti da un'origine dati con un livello di gravità compreso tra 11 e 16 generano un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-114">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="e4d4c-115">Tuttavia, l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> consente di ottenere dall'origine dati i messaggi che non sono associati a un errore.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-115">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="e4d4c-116">Nel caso di Microsoft SQL Server i messaggi di errore con una gravità uguale o minore di 10 sono considerati informativi e vengono acquisiti usando l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-116">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="e4d4c-117">Per altre informazioni, vedere l'argomento "Error Message Severity Levels" (Livelli di gravità dei messaggi di errore) nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-117">For more information, see the "Error Message Severity Levels" topic in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="e4d4c-118">Il <xref:System.Data.SqlClient.SqlConnection.InfoMessage> evento riceve un <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> oggetto che contiene, nella relativa **errori** , una raccolta di messaggi dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-118">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="e4d4c-119">È possibile eseguire una query di **errore** oggetti della raccolta per il testo di un numero e il messaggio di errore, nonché l'origine dell'errore.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-119">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="e4d4c-120">Il provider di dati .NET Framework per SQL Server include inoltre i dettagli sul database, sulla stored procedure e sul numero di riga da cui proviene il messaggio.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-120">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e4d4c-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="e4d4c-121">Example</span></span>  
 <span data-ttu-id="e4d4c-122">Nell'esempio di codice seguente viene illustrato come aggiungere un gestore eventi per l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-122">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
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
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="e4d4c-123">Gestione di errori come InfoMessage</span><span class="sxs-lookup"><span data-stu-id="e4d4c-123">Handling Errors as InfoMessages</span></span>  
 <span data-ttu-id="e4d4c-124">In genere, l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> verrà generato solo per messaggi informativi e per messaggi di avviso inviati dal server.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-124">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="e4d4c-125">Tuttavia, quando si verifica un errore, l'esecuzione del **ExecuteNonQuery** o **ExecuteReader** metodo che ha avviato l'operazione del server viene interrotta e viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-125">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="e4d4c-126">Per continuare a elaborare le restanti istruzioni di un comando indipendentemente da eventuali messaggi di errore generati dal server, impostare la proprietà <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> del tipo <xref:System.Data.SqlClient.SqlConnection> su `true`.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-126">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="e4d4c-127">In questo modo, invece di generare un'eccezione e di interrompere l'elaborazione, la connessione genera l'evento di errore <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-127">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="e4d4c-128">L'applicazione client può quindi gestire questo evento e rispondere alle condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-128">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4d4c-129">Un errore con un livello di gravità pari a 17 o superiore che provoca l'interruzione dell'elaborazione del comando da parte del server deve essere gestito come un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-129">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="e4d4c-130">In questo caso viene generata un'eccezione indipendentemente da come viene gestito l'errore nell'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-130">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="e4d4c-131">Utilizzo dell'evento StateChange</span><span class="sxs-lookup"><span data-stu-id="e4d4c-131">Working with the StateChange Event</span></span>  
 <span data-ttu-id="e4d4c-132">Il **StateChange** evento si verifica quando lo stato di un **connessione** le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-132">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="e4d4c-133">Il **StateChange** riceve eventi <xref:System.Data.StateChangeEventArgs> che consentono di determinare la modifica dello stato del **connessione** utilizzando il **OriginalState** e **CurrentState** proprietà.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-133">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="e4d4c-134">Il **OriginalState** proprietà è un <xref:System.Data.ConnectionState> enumerazione che indica lo stato del **connessione** prima della modifica.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-134">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="e4d4c-135">**CurrentState** è un <xref:System.Data.ConnectionState> enumerazione che indica lo stato del **connessione** dopo che è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-135">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="e4d4c-136">Nell'esempio di codice viene illustrato come utilizzare il **StateChange** evento per scrivere un messaggio nella console quando lo stato del **connessione** le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-136">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e4d4c-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4d4c-137">See Also</span></span>  
 [<span data-ttu-id="e4d4c-138">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="e4d4c-138">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="e4d4c-139">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="e4d4c-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
