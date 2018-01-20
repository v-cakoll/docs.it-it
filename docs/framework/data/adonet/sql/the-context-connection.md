---
title: Connessione di contesto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 40aa71a16c7a0616cfcf318901858da7587fa20b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="the-context-connection"></a><span data-ttu-id="c0b19-102">Connessione di contesto</span><span class="sxs-lookup"><span data-stu-id="c0b19-102">The Context Connection</span></span>
<span data-ttu-id="c0b19-103">Il problema dell'accesso ai dati interni è uno scenario abbastanza comune.</span><span class="sxs-lookup"><span data-stu-id="c0b19-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="c0b19-104">In altri termini, si desidera accedere allo stesso server sul quale è in esecuzione la propria stored procedure o funzione CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="c0b19-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="c0b19-105">Una possibilità consiste nel creare una connessione usando il tipo <xref:System.Data.SqlClient.SqlConnection>, specificare una stringa di connessione che faccia riferimento al server locale, quindi aprire la connessione.</span><span class="sxs-lookup"><span data-stu-id="c0b19-105">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="c0b19-106">A tale scopo è necessario fornire per l'accesso le credenziali appropriate.</span><span class="sxs-lookup"><span data-stu-id="c0b19-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="c0b19-107">La connessione si trova infatti in una sessione di database diversa da quella della stored procedure o della funzione, può disporre di opzioni `SET` diverse, si trova in una transazione separata, non rileva le tabelle temporanee e così via.</span><span class="sxs-lookup"><span data-stu-id="c0b19-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="c0b19-108">Se la stored procedure gestita o il codice di funzione gestito è in esecuzione nel processo SQL Server, significa che un utente ha effettuato l'accesso a quel server e ha eseguito un'istruzione SQL per richiamare tale stored procedure o funzione.</span><span class="sxs-lookup"><span data-stu-id="c0b19-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="c0b19-109">Con tutta probabilità si desidera che la stored procedure o funzione venga eseguita nel contesto di tale connessione, insieme alla relativa transazione, alle relative opzioni `SET` e così via.</span><span class="sxs-lookup"><span data-stu-id="c0b19-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="c0b19-110">Questa viene definita connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="c0b19-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="c0b19-111">La connessione di contesto consente di eseguire istruzioni Transact-SQL nello stesso contesto in cui il codice era stato richiamato in primo luogo.</span><span class="sxs-lookup"><span data-stu-id="c0b19-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="c0b19-112">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="c0b19-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="c0b19-113">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="c0b19-113">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="c0b19-114">Connessione di contesto</span><span class="sxs-lookup"><span data-stu-id="c0b19-114">The Context Connection</span></span>](http://go.microsoft.com/fwlink/?LinkId=115395)  
  
## <a name="see-also"></a><span data-ttu-id="c0b19-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0b19-115">See Also</span></span>  
 [<span data-ttu-id="c0b19-116">Creazione di oggetti di SQL Server 2005 nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="c0b19-116">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="c0b19-117">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c0b19-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
