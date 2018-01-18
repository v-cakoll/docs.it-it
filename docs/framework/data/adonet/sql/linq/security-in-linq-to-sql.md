---
title: Sicurezza in LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0ee361c27bd14f0266b2b86f315f9c091e049c12
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="security-in-linq-to-sql"></a><span data-ttu-id="952bf-102">Sicurezza in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="952bf-102">Security in LINQ to SQL</span></span>
<span data-ttu-id="952bf-103">Quando si esegue la connessione a un database, vi sono sempre problemi relativi alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="952bf-103">Security risks are always present when you connect to a database.</span></span> <span data-ttu-id="952bf-104">Sebbene in LINQ to SQL siano disponibili alcune nuove modalità di utilizzo dei dati in SQL Server, non vengono forniti meccanismi di sicurezza aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="952bf-104">Although LINQ to SQL may include some new ways to work with data in SQL Server, it does not provide any additional security mechanisms.</span></span>  
  
## <a name="access-control-and-authentication"></a><span data-ttu-id="952bf-105">Controllo dell'accesso e autenticazione</span><span class="sxs-lookup"><span data-stu-id="952bf-105">Access Control and Authentication</span></span>  
 <span data-ttu-id="952bf-106">LINQ to SQL non dispone di meccanismi di autenticazione o di un modello utente.</span><span class="sxs-lookup"><span data-stu-id="952bf-106">LINQ to SQL does not have its own user model or authentication mechanisms.</span></span> <span data-ttu-id="952bf-107">Usare le funzionalità di sicurezza di SQL Server per controllare l'accesso al database, le tabelle di database, le visualizzazioni e le stored procedure mappate al modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="952bf-107">Use SQL Server Security to control access to the database, database tables, views, and stored procedures that are mapped to your object model.</span></span> <span data-ttu-id="952bf-108">Concedere l'accesso minimo richiesto agli utenti e richiedere password complesse per l'autenticazione utente.</span><span class="sxs-lookup"><span data-stu-id="952bf-108">Grant the minimally required access to users and require strong passwords for user authentication.</span></span>  
  
## <a name="mapping-and-schema-information"></a><span data-ttu-id="952bf-109">Informazioni sul mapping e sullo schema</span><span class="sxs-lookup"><span data-stu-id="952bf-109">Mapping and Schema Information</span></span>  
 <span data-ttu-id="952bf-110">Le informazioni sul mapping dei tipi SQL-CLR e sullo schema di database nel modello a oggetti o nel file di mapping esterno sono disponibili per tutti gli utenti che dispongono di accesso a tali file nel file system.</span><span class="sxs-lookup"><span data-stu-id="952bf-110">SQL-CLR type mapping and database schema information in your object model or external mapping file is available for all with access to those files in the file system.</span></span> <span data-ttu-id="952bf-111">Si presupponga che le informazioni sullo schema siano disponibili per tutti gli utenti che possono accedere al modello a oggetti o al file di mapping esterno. Per impedire un accesso più esteso alle informazioni sullo schema, usare i meccanismi di sicurezza dei file per proteggere i file di origine e i file di mapping.</span><span class="sxs-lookup"><span data-stu-id="952bf-111">Assume that schema information will be available to all who can access the object model or external mapping file.To prevent more widespread access to schema information, use file security mechanisms to secure source files and mapping files.</span></span>  
  
## <a name="connection-strings"></a><span data-ttu-id="952bf-112">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="952bf-112">Connection Strings</span></span>  
 <span data-ttu-id="952bf-113">L'utilizzo di password nelle stringhe di connessione deve essere evitato, quando possibile.</span><span class="sxs-lookup"><span data-stu-id="952bf-113">Using passwords in connection strings should be avoided whenever possible.</span></span> <span data-ttu-id="952bf-114">Una stringa di connessione non solo rappresenta un rischio per la sicurezza di per sé, ma può anche essere aggiunta come testo non crittografato al modello a oggetti o al file di mapping esterno quando si usa Progettazione relazionale oggetti o lo strumento da riga di comando SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="952bf-114">Not only is a connection string a security risk in its own right, but the connection string may also be added in clear text to the object model or external mapping file when using the Object Relational Designer or SQLMetal command-line tool.</span></span> <span data-ttu-id="952bf-115">Chiunque disponga di accesso al modello a oggetti o al file di mapping esterno tramite il file system può vedere la password di connessione, se è inclusa nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="952bf-115">Anyone with access to the object model or external mapping file via the file system could see the connection password (if it is included in the connection string).</span></span>  
  
 <span data-ttu-id="952bf-116">Per minimizzare tali rischi, usare la sicurezza integrata per effettuare una connessione trusted con [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="952bf-116">To minimize such risks, use integrated security to make a trusted connection with [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="952bf-117">Usando questo approccio, non è necessario archiviare una password nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="952bf-117">By using this approach, you do not have to store a password in the connection string.</span></span> <span data-ttu-id="952bf-118">Per ulteriori informazioni, vedere [sicurezza di SQL Server](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span><span class="sxs-lookup"><span data-stu-id="952bf-118">For more information, see [SQL Server Security](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span></span>  
  
 <span data-ttu-id="952bf-119">In assenza della sicurezza integrata, nella stringa di connessione è necessaria una password non crittografata.</span><span class="sxs-lookup"><span data-stu-id="952bf-119">In the absence of integrated security, a clear-text password will be needed in the connection string.</span></span> <span data-ttu-id="952bf-120">I modi migliori per proteggere la stringa di connessione, in ordine di rischio crescente, sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="952bf-120">The best way to help secure your connection string, in increasing order of risk, is as follows:</span></span>  
  
-   <span data-ttu-id="952bf-121">Usare la sicurezza integrata.</span><span class="sxs-lookup"><span data-stu-id="952bf-121">Use integrated security.</span></span>  
  
-   <span data-ttu-id="952bf-122">Proteggere le stringhe di connessione tramite password e ridurre al minimo i passaggi delle stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="952bf-122">Secure connection strings with passwords and minimize passing around connection strings.</span></span>  
  
-   <span data-ttu-id="952bf-123">Usare una classe <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> anziché una stringa di connessione, in quanto la classe limita la durata dell'esposizione.</span><span class="sxs-lookup"><span data-stu-id="952bf-123">Use a <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> class instead of a connection string since it limits the duration of exposure.</span></span> <span data-ttu-id="952bf-124">È possibile creare un'istanza della classe <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> LINQ to SQL usando un oggetto <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="952bf-124">The LINQ to SQL <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> class can be instantiated using a <xref:System.Data.SqlClient.SqlConnection>.</span></span>  
  
-   <span data-ttu-id="952bf-125">Ridurre al minimo la durata e i punti di contatto per tutte le stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="952bf-125">Minimize lifetimes and touch points for all connection strings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="952bf-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="952bf-126">See Also</span></span>  
 [<span data-ttu-id="952bf-127">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="952bf-127">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="952bf-128">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="952bf-128">Frequently Asked Questions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)
