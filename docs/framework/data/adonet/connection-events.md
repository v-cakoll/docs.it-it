---
title: Eventi di connessione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: a7ad0d4d950da71db0aebca872949fa82669c5c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151701"
---
# <a name="connection-events"></a><span data-ttu-id="03eec-102">Eventi di connessione</span><span class="sxs-lookup"><span data-stu-id="03eec-102">Connection Events</span></span>
<span data-ttu-id="03eec-103">Tutti i provider di dati .NET Framework .NET Framework dispongono di oggetti **Connection** con due eventi che è possibile utilizzare per recuperare messaggi informativi da un'origine dati o per determinare se lo stato di un **oggetto Connection** è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="03eec-103">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="03eec-104">Nella tabella seguente vengono descritti gli eventi dell'oggetto **Connection.**</span><span class="sxs-lookup"><span data-stu-id="03eec-104">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="03eec-105">Event</span><span class="sxs-lookup"><span data-stu-id="03eec-105">Event</span></span>|<span data-ttu-id="03eec-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03eec-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="03eec-107">**Infomessage**</span><span class="sxs-lookup"><span data-stu-id="03eec-107">**InfoMessage**</span></span>|<span data-ttu-id="03eec-108">Si verifica quando un messaggio informativo viene restituito da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="03eec-108">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="03eec-109">I messaggi informativi sono i messaggi di un'origine dati per cui non viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="03eec-109">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|<span data-ttu-id="03eec-110">**StateChange**</span><span class="sxs-lookup"><span data-stu-id="03eec-110">**StateChange**</span></span>|<span data-ttu-id="03eec-111">Si verifica quando cambia lo stato della **connessione.**</span><span class="sxs-lookup"><span data-stu-id="03eec-111">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="03eec-112">Utilizzo dell'evento InfoMessage</span><span class="sxs-lookup"><span data-stu-id="03eec-112">Working with the InfoMessage Event</span></span>  
 <span data-ttu-id="03eec-113">È possibile recuperare avvisi e messaggi informativi da un'origine dati SQL Server usando l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> dell'oggetto <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="03eec-113">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="03eec-114">Gli errori restituiti da un'origine dati con un livello di gravità compreso tra 11 e 16 generano un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="03eec-114">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="03eec-115">Tuttavia, l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> consente di ottenere dall'origine dati i messaggi che non sono associati a un errore.</span><span class="sxs-lookup"><span data-stu-id="03eec-115">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="03eec-116">Nel caso di Microsoft SQL Server i messaggi di errore con una gravità uguale o minore di 10 sono considerati informativi e vengono acquisiti usando l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="03eec-116">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="03eec-117">Per altre informazioni, vedere l'articolo Gravità degli errori del motore di [database.](/sql/relational-databases/errors-events/database-engine-error-severities)</span><span class="sxs-lookup"><span data-stu-id="03eec-117">For more information, see the [Database Engine Error Severities](/sql/relational-databases/errors-events/database-engine-error-severities) article.</span></span>
  
 <span data-ttu-id="03eec-118">L'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> riceve <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> un oggetto contenente, nella relativa proprietà **Errors,** una raccolta dei messaggi dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="03eec-118">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="03eec-119">È possibile eseguire una query di **Error** oggetti in questa raccolta per il numero di errore e il testo del messaggio, nonché l'origine dell'errore.</span><span class="sxs-lookup"><span data-stu-id="03eec-119">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="03eec-120">Il provider di dati .NET Framework per SQL Server include inoltre i dettagli sul database, sulla stored procedure e sul numero di riga da cui proviene il messaggio.</span><span class="sxs-lookup"><span data-stu-id="03eec-120">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="03eec-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="03eec-121">Example</span></span>  
 <span data-ttu-id="03eec-122">Nell'esempio di codice seguente viene illustrato come aggiungere un gestore eventi per l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="03eec-122">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
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
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="03eec-123">Gestione di errori come InfoMessage</span><span class="sxs-lookup"><span data-stu-id="03eec-123">Handling Errors as InfoMessages</span></span>  
 <span data-ttu-id="03eec-124">In genere, l'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> verrà generato solo per messaggi informativi e per messaggi di avviso inviati dal server.</span><span class="sxs-lookup"><span data-stu-id="03eec-124">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="03eec-125">Tuttavia, quando si verifica un errore effettivo, l'esecuzione del **metodo ExecuteNonQuery** o **ExecuteReader** che ha avviato l'operazione del server viene interrotta e viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="03eec-125">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="03eec-126">Per continuare a elaborare le restanti istruzioni di un comando indipendentemente da eventuali messaggi di errore generati dal server, impostare la proprietà <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> del tipo <xref:System.Data.SqlClient.SqlConnection> su `true`.</span><span class="sxs-lookup"><span data-stu-id="03eec-126">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="03eec-127">In questo modo, invece di generare un'eccezione e di interrompere l'elaborazione, la connessione genera l'evento di errore <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="03eec-127">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="03eec-128">L'applicazione client può quindi gestire questo evento e rispondere alle condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="03eec-128">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03eec-129">Un errore con un livello di gravità pari a 17 o superiore che provoca l'interruzione dell'elaborazione del comando da parte del server deve essere gestito come un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="03eec-129">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="03eec-130">In questo caso viene generata un'eccezione indipendentemente da come viene gestito l'errore nell'evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="03eec-130">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="03eec-131">Utilizzo dell'evento StateChange</span><span class="sxs-lookup"><span data-stu-id="03eec-131">Working with the StateChange Event</span></span>  
 <span data-ttu-id="03eec-132">**L'evento StateChange** si verifica quando cambia lo stato di un **oggetto Connection.**</span><span class="sxs-lookup"><span data-stu-id="03eec-132">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="03eec-133">L'evento **StateChange** <xref:System.Data.StateChangeEventArgs> riceve che consente di determinare la modifica dello stato della **connessione** utilizzando il **OriginalState** e **CurrentState** proprietà.</span><span class="sxs-lookup"><span data-stu-id="03eec-133">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="03eec-134">Il **OriginalState** proprietà <xref:System.Data.ConnectionState> è un'enumerazione che indica lo stato del **Connection** prima della modifica.</span><span class="sxs-lookup"><span data-stu-id="03eec-134">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="03eec-135">**CurrentState** è <xref:System.Data.ConnectionState> un'enumerazione che indica lo stato della **connessione** dopo la modifica.</span><span class="sxs-lookup"><span data-stu-id="03eec-135">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="03eec-136">Nell'esempio di codice riportato di seguito viene illustrato come utilizzare l'evento **StateChange** per scrivere un messaggio nella console quando cambia lo stato della **connessione.**</span><span class="sxs-lookup"><span data-stu-id="03eec-136">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="03eec-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03eec-137">See also</span></span>

- [<span data-ttu-id="03eec-138">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="03eec-138">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="03eec-139">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="03eec-139">ADO.NET Overview</span></span>](ado-net-overview.md)
