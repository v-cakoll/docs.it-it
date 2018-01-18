---
title: DbConnection, DbCommand e DbException
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
ms.assetid: 58aab611-7e6f-4749-b983-28ab7ae87dbe
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7a79587762ec9b69bcc580af63fc1db19e491dec
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="dbconnection-dbcommand-and-dbexception"></a><span data-ttu-id="cb9c0-102">DbConnection, DbCommand e DbException</span><span class="sxs-lookup"><span data-stu-id="cb9c0-102">DbConnection, DbCommand and DbException</span></span>
<span data-ttu-id="cb9c0-103">Dopo aver creato un oggetto <xref:System.Data.Common.DbProviderFactory> e un oggetto <xref:System.Data.Common.DbConnection>, è possibile usare comandi e lettori di dati per recuperare i dati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-103">Once you have created a <xref:System.Data.Common.DbProviderFactory> and a <xref:System.Data.Common.DbConnection>, you can then work with commands and data readers to retrieve data from the data source.</span></span>  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="cb9c0-104">Esempio di recupero di dati</span><span class="sxs-lookup"><span data-stu-id="cb9c0-104">Retrieving Data Example</span></span>  
 <span data-ttu-id="cb9c0-105">In questo esempio viene usato un oggetto `DbConnection` come argomento.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-105">This example takes a `DbConnection` object as an argument.</span></span> <span data-ttu-id="cb9c0-106">Viene creato un oggetto <xref:System.Data.Common.DbCommand> per selezionare dati dalla tabella Categories impostando <xref:System.Data.Common.DbCommand.CommandText%2A> su un'istruzione SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-106">A <xref:System.Data.Common.DbCommand> is created to select data from the Categories table by setting the <xref:System.Data.Common.DbCommand.CommandText%2A> to a SQL SELECT statement.</span></span> <span data-ttu-id="cb9c0-107">Nel codice si presuppone che la tabella Categories esista nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-107">The code assumes that the Categories table exists at the data source.</span></span> <span data-ttu-id="cb9c0-108">La connessione viene aperta e i dati vengono recuperati tramite <xref:System.Data.Common.DbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-108">The connection is opened and the data is retrieved using a <xref:System.Data.Common.DbDataReader>.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/VB/source.vb#1)]  
  
## <a name="executing-a-command-example"></a><span data-ttu-id="cb9c0-109">Esempio di esecuzione di un comando</span><span class="sxs-lookup"><span data-stu-id="cb9c0-109">Executing a Command Example</span></span>  
 <span data-ttu-id="cb9c0-110">In questo esempio viene usato un oggetto `DbConnection` come argomento.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-110">This example takes a `DbConnection` object as an argument.</span></span> <span data-ttu-id="cb9c0-111">Se `DbConnection` è valido, la connessione viene aperta e viene creato ed eseguito un oggetto <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-111">If the `DbConnection` is valid, the connection is opened and a <xref:System.Data.Common.DbCommand> is created and executed.</span></span> <span data-ttu-id="cb9c0-112"><xref:System.Data.Common.DbCommand.CommandText%2A> viene impostato su un'istruzione SQL INSERT che esegue un inserimento nella tabella Categories del database Northwind.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-112">The <xref:System.Data.Common.DbCommand.CommandText%2A> is set to a SQL INSERT statement that performs an insert to the Categories table in the Northwind database.</span></span> <span data-ttu-id="cb9c0-113">Nel codice si presuppone che il database Northwind esista nell'origine dati e che la sintassi SQL usata nell'istruzione INSERT sia valida per il provider specificato.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-113">The code assumes that the Northwind database exists at the data source, and that the SQL syntax used in the INSERT statement is valid for the specified provider.</span></span> <span data-ttu-id="cb9c0-114">Gli errori che si verificano nell'origine dati vengono gestiti dal blocco di codice <xref:System.Data.Common.DbException>, mentre tutte le altre eccezioni vengono gestite nel blocco <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-114">Errors occurring at the data source are handled by the <xref:System.Data.Common.DbException> code block, and all other exceptions are handled in the <xref:System.Exception> block.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/VB/source.vb#1)]  
  
## <a name="handling-data-errors-with-dbexception"></a><span data-ttu-id="cb9c0-115">Gestione di errori dei dati con DbException</span><span class="sxs-lookup"><span data-stu-id="cb9c0-115">Handling Data Errors with DbException</span></span>  
 <span data-ttu-id="cb9c0-116">La classe <xref:System.Data.Common.DbException> è la classe di base per tutte le eccezioni generate per conto di un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-116">The <xref:System.Data.Common.DbException> class is the base class for all exceptions thrown on behalf of a data source.</span></span> <span data-ttu-id="cb9c0-117">È possibile usarla nel codice di gestione delle eccezioni per gestire le eccezioni generate da provider diversi senza dover fare riferimento a una classe di eccezioni specifica.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-117">You can use it in your exception handling code to handle exceptions thrown by different providers without having to reference a specific exception class.</span></span> <span data-ttu-id="cb9c0-118">Nel frammento di codice seguente viene illustrato come usare <xref:System.Data.Common.DbException> per visualizzare le informazioni sugli errori restituiti dall'origine dati tramite le proprietà <xref:System.Exception.GetType%2A>, <xref:System.Exception.Source%2A>, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A> e <xref:System.Exception.Message%2A>.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-118">The following code fragment demonstrates how to use <xref:System.Data.Common.DbException> to display error information returned by the data source using <xref:System.Exception.GetType%2A>, <xref:System.Exception.Source%2A>, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A>, and <xref:System.Exception.Message%2A> properties.</span></span> <span data-ttu-id="cb9c0-119">Nell'output verranno visualizzati il tipo di errore, l'origine indicante il nome del provider, un codice di errore e il messaggio associato all'errore.</span><span class="sxs-lookup"><span data-stu-id="cb9c0-119">The output will display the type of error, the source indicating the provider name, an error code, and the message associated with the error.</span></span>  
  
```vb  
Try  
    ' Do work here.  
Catch ex As DbException  
    ' Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType())  
    Console.WriteLine("Source: {0}", ex.Source)  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode)  
    Console.WriteLine("Message: {0}", ex.Message)  
Finally  
    ' Perform cleanup here.  
End Try  
```  
  
```csharp  
try  
{  
    // Do work here.  
}  
catch (DbException ex)  
{  
    // Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType());  
    Console.WriteLine("Source: {0}", ex.Source);  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode);  
    Console.WriteLine("Message: {0}", ex.Message);  
}  
finally  
{  
    // Perform cleanup here.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb9c0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb9c0-120">See Also</span></span>  
 [<span data-ttu-id="cb9c0-121">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="cb9c0-121">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [<span data-ttu-id="cb9c0-122">Recupero di una classe DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="cb9c0-122">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [<span data-ttu-id="cb9c0-123">Modifica di dati con un oggetto DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="cb9c0-123">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [<span data-ttu-id="cb9c0-124">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="cb9c0-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
