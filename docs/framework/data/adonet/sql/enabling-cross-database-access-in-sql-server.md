---
title: Abilitazione dell'accesso tra database in SQL Server
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
caps.latest.revision: 10
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 0f27f5bd63acbf532d3dca2a8c6fea0b1a59d659
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="enabling-cross-database-access-in-sql-server"></a><span data-ttu-id="6f0f6-102">Abilitazione dell'accesso tra database in SQL Server</span><span class="sxs-lookup"><span data-stu-id="6f0f6-102">Enabling Cross-Database Access in SQL Server</span></span>
<span data-ttu-id="6f0f6-103">Il concatenamento della proprietà tra database si verifica quando una procedura di un database dipende dagli oggetti di un altro.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-103">Cross-database ownership chaining occurs when a procedure in one database depends on objects in another database.</span></span> <span data-ttu-id="6f0f6-104">Una catena di proprietà tra database funziona allo stesso modo del concatenamento della proprietà con un singolo database, ad eccezione del fatto che una catena di proprietà non interrotta richiede che tutti i proprietari degli oggetti siano mappati allo stesso account di accesso.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-104">A cross-database ownership chain works in the same way as ownership chaining within a single database, except that an unbroken ownership chain requires that all the object owners are mapped to the same login account.</span></span> <span data-ttu-id="6f0f6-105">Se l'oggetto di origine nel database di origine e gli oggetti di destinazione nei database di destinazione appartengono allo stesso account di accesso, le autorizzazioni sugli oggetti di destinazione non verranno controllate in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-105">If the source object in the source database and the target objects in the target databases are owned by the same login account, SQL Server does not check permissions on the target objects.</span></span>  
  
## <a name="off-by-default"></a><span data-ttu-id="6f0f6-106">Disattivazione per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="6f0f6-106">Off By Default</span></span>  
 <span data-ttu-id="6f0f6-107">Il concatenamento della proprietà tra database è disattivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-107">Ownership chaining across databases is turned off by default.</span></span> <span data-ttu-id="6f0f6-108">Microsoft consiglia di disabilitare questa funzionalità perché espone la sicurezza ai seguenti rischi:</span><span class="sxs-lookup"><span data-stu-id="6f0f6-108">Microsoft recommends that you disable cross-database ownership chaining because it exposes you to the following security risks:</span></span>  
  
-   <span data-ttu-id="6f0f6-109">I proprietari dei database e i membri dei ruoli di database `db_ddladmin` o `db_owners` possono creare oggetti appartenenti ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-109">Database owners and members of the `db_ddladmin` or the `db_owners` database roles can create objects that are owned by other users.</span></span> <span data-ttu-id="6f0f6-110">Questi oggetti possono avere come destinazione gli oggetti di altri database,</span><span class="sxs-lookup"><span data-stu-id="6f0f6-110">These objects can potentially target objects in other databases.</span></span> <span data-ttu-id="6f0f6-111">il che significa che se si abilita il concatenamento della proprietà tra database, è necessario considerare completamente attendibili questi utenti per i dati di tutti i database.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-111">This means that if you enable cross-database ownership chaining, you must fully trust these users with data in all databases.</span></span>  
  
-   <span data-ttu-id="6f0f6-112">Gli utenti con l'autorizzazione CREATE DATABASE possono creare nuovi database e collegare database esistenti.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-112">Users with CREATE DATABASE permission can create new databases and attach existing databases.</span></span> <span data-ttu-id="6f0f6-113">Se il concatenamento della proprietà tra database è abilitato, questi utenti possono accedere ad oggetti di altri database per cui potrebbero non disporre di privilegi dai database appena creati o collegati.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-113">If cross-database ownership chaining is enabled, these users can access objects in other databases that they might not have privileges in from the newly created or attached databases that they create.</span></span>  
  
## <a name="enabling-cross-database-ownership-chaining"></a><span data-ttu-id="6f0f6-114">Abilitazione del concatenamento della proprietà tra database</span><span class="sxs-lookup"><span data-stu-id="6f0f6-114">Enabling Cross-database Ownership Chaining</span></span>  
 <span data-ttu-id="6f0f6-115">Il concatenamento della proprietà tra database deve essere abilitato solo negli ambienti in cui gli utenti con privilegi elevati possono essere considerati completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-115">Cross-database ownership chaining should only be enabled in environments where you can fully trust highly-privileged users.</span></span> <span data-ttu-id="6f0f6-116">Questa funzionalità può essere configurata durante l'installazione per tutti i database o in modo selettivo per specifici database usando i comandi [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `sp_configure` e `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-116">It can be configured during setup for all databases, or selectively for specific databases using the [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] commands `sp_configure` and `ALTER DATABASE`.</span></span>  
  
 <span data-ttu-id="6f0f6-117">Per configurare in modo selettivo questa funzionalità, usare `sp_configure` per disattivarla per il server.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-117">To selectively configure cross-database ownership chaining, use `sp_configure` to turn it off for the server.</span></span> <span data-ttu-id="6f0f6-118">Usare quindi il comando ALTER DATABASE con SET DB_CHAINING ON per configurare il concatenamento della proprietà tra database solo per i database per cui è necessario.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-118">Then use the ALTER DATABASE command with SET DB_CHAINING ON to configure cross-database ownership chaining for only the databases that require it.</span></span>  
  
 <span data-ttu-id="6f0f6-119">Nell'esempio seguente si attiva il concatenamento della proprietà tra database per tutti i database:</span><span class="sxs-lookup"><span data-stu-id="6f0f6-119">The following sample turns on cross-database ownership chaining for all databases:</span></span>  
  
```  
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 <span data-ttu-id="6f0f6-120">Nell'esempio seguente si attiva il concatenamento della proprietà tra database per database specifici:</span><span class="sxs-lookup"><span data-stu-id="6f0f6-120">The following sample turns on cross-database ownership chaining for specific databases:</span></span>  
  
```  
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a><span data-ttu-id="6f0f6-121">SQL dinamico</span><span class="sxs-lookup"><span data-stu-id="6f0f6-121">Dynamic SQL</span></span>  
 <span data-ttu-id="6f0f6-122">Il concatenamento della proprietà tra database non funziona nei casi in cui vengono eseguite istruzioni SQL create in modo dinamico, a meno che nei due database non esistano gli stessi utenti.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-122">Cross-database ownership chaining does not work in cases where dynamically created SQL statements are executed unless the same user exists in both databases.</span></span> <span data-ttu-id="6f0f6-123">È possibile risolvere il problema in SQL Server creando una stored procedure che accede ai dati in un altro database e firmare la procedura con un certificato esistente in entrambi i database.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-123">You can work around this in SQL Server by creating a stored procedure that accesses data in another database and signing the procedure with a certificate that exists in both databases.</span></span> <span data-ttu-id="6f0f6-124">In questo modo si fornisce agli utenti l'accesso alle risorse del database usate dalla procedura senza concedere loro l'accesso o le autorizzazioni per il database.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-124">This gives users access to the database resources used by the procedure without granting them database access or permissions.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="6f0f6-125">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="6f0f6-125">External Resources</span></span>  
 <span data-ttu-id="6f0f6-126">Per altre informazioni, vedere le risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-126">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="6f0f6-127">Risorsa</span><span class="sxs-lookup"><span data-stu-id="6f0f6-127">Resource</span></span>|<span data-ttu-id="6f0f6-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f0f6-128">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6f0f6-129">[Estensione della rappresentazione di Database tramite EXECUTE AS](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) e [Cross DB Ownership Chaining-opzione](http://msdn.microsoft.com/library/ms188694.aspx)documentazione Online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-129">[Extending Database Impersonation by Using EXECUTE AS](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) and [Cross DB Ownership Chaining Option](http://msdn.microsoft.com/library/ms188694.aspx)SQL Server Books Online.</span></span>|<span data-ttu-id="6f0f6-130">Negli argomenti viene descritto come configurare tra database concatenamento della proprietà per un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f0f6-130">Topics describe how to configure cross-database ownership chaining for an instance of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f0f6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f0f6-131">See Also</span></span>  
 [<span data-ttu-id="6f0f6-132">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6f0f6-132">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="6f0f6-133">Cenni preliminari sulla sicurezza in SQL Server</span><span class="sxs-lookup"><span data-stu-id="6f0f6-133">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="6f0f6-134">Gestione delle autorizzazioni con stored procedure in SQL Server</span><span class="sxs-lookup"><span data-stu-id="6f0f6-134">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="6f0f6-135">Scrittura dinamica sicura in SQL Server</span><span class="sxs-lookup"><span data-stu-id="6f0f6-135">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="6f0f6-136">Firma di stored procedure in SQL Server</span><span class="sxs-lookup"><span data-stu-id="6f0f6-136">Signing Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="6f0f6-137">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="6f0f6-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
