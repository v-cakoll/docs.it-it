---
title: Concessione di autorizzazioni a livello di riga in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a42c8d24a2817fb0a4118927722e7ac1887517a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="granting-row-level-permissions-in-sql-server"></a><span data-ttu-id="75da3-102">Concessione di autorizzazioni a livello di riga in SQL Server</span><span class="sxs-lookup"><span data-stu-id="75da3-102">Granting Row-Level Permissions in SQL Server</span></span>
<span data-ttu-id="75da3-103">In alcuni scenari è necessario controllare l'accesso a un livello caratterizzato da una maggior granularità rispetto a quanto consentito dalla semplice concessione, revoca o negazione delle autorizzazioni sui dati.</span><span class="sxs-lookup"><span data-stu-id="75da3-103">In some scenarios, there is a requirement to control access to data at a more granular level than what simply granting, revoking, or denying permissions provides.</span></span> <span data-ttu-id="75da3-104">Ad esempio, in un'applicazione di database usata in un ospedale potrebbe essere necessario consentire ai medici di visualizzare solo le informazioni correlate ai propri pazienti.</span><span class="sxs-lookup"><span data-stu-id="75da3-104">For example, a hospital database application may require individual Doctors to be restricted to accessing information related to only their patients.</span></span> <span data-ttu-id="75da3-105">Scenari simili sono presenti in molti ambienti, tra cui quelli delle applicazioni destinate al settore finanziario, legale, statale e militare.</span><span class="sxs-lookup"><span data-stu-id="75da3-105">Similar requirements exist in many environments, including finance, law, government, and military applications.</span></span> <span data-ttu-id="75da3-106">Per contribuire a gestire questi scenari, SQL Server 2016 fornisce una funzionalità di [sicurezza a livello di riga](https://msdn.microsoft.com/library/dn765131.aspx) che semplifica e centralizza la logica di accesso a livello di riga in un criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="75da3-106">To help address these scenarios, SQL Server 2016 provides a [Row-Level Security](https://msdn.microsoft.com/library/dn765131.aspx) feature that simplifies and centralizes row-level access logic in a security policy.</span></span> <span data-ttu-id="75da3-107">Per le versioni precedenti di SQL Server, una funzionalità simile può essere ottenuta usando le visualizzazioni per applicare filtri a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="75da3-107">For earlier versions of SQL Server, similar functionality can be achieved by using views to enact row-level filtering.</span></span>  
  
## <a name="implementing-row-level-filtering"></a><span data-ttu-id="75da3-108">Implementazione di applicazione di filtri a livello di riga</span><span class="sxs-lookup"><span data-stu-id="75da3-108">Implementing Row-level Filtering</span></span>  
 <span data-ttu-id="75da3-109">L'applicazione di filtri a livello di riga viene usata per applicazioni che archiviano informazioni in un'unica tabella, come nell'esempio dell'ospedale.</span><span class="sxs-lookup"><span data-stu-id="75da3-109">Row-level filtering is used for applications storing information in a single table like in the hospital example above.</span></span> <span data-ttu-id="75da3-110">Per applicare i filtri a livello di riga, ogni riga include una colonna che definisce un parametro discriminante, ad esempio un nome utente, un'etichetta o un altro identificatore.</span><span class="sxs-lookup"><span data-stu-id="75da3-110">To implement row-level filtering each row has a column that defines a differentiating parameter, such as a user name, label or other identifier.</span></span> <span data-ttu-id="75da3-111">È possibile creare un criterio di sicurezza o una visualizzazione nella tabella, che consente di filtrare le righe a cui l'utente può accedere.</span><span class="sxs-lookup"><span data-stu-id="75da3-111">You create either a security policy or a view on the table, which filters the rows that the user can access.</span></span> <span data-ttu-id="75da3-112">È possibile quindi creare stored procedure con parametri, che controllano i tipi di query, che l'utente può eseguire.</span><span class="sxs-lookup"><span data-stu-id="75da3-112">You then create parameterized stored procedures, which control the types of queries the user can execute.</span></span>  
  
 <span data-ttu-id="75da3-113">L'esempio seguente descrive come configurare l'applicazione di filtri a livello di riga basati su un nome utente o un nome di accesso:</span><span class="sxs-lookup"><span data-stu-id="75da3-113">The following example describes how to configure row-level filtering based on a user or login name:</span></span>  
  
-   <span data-ttu-id="75da3-114">Creare la tabella, aggiungendo una colonna per l'archiviazione del nome.</span><span class="sxs-lookup"><span data-stu-id="75da3-114">Create the table, adding a column to store the name.</span></span>  
  
-   <span data-ttu-id="75da3-115">Abilitare l'applicazione di filtri a livello di riga:</span><span class="sxs-lookup"><span data-stu-id="75da3-115">Enable row-level filtering:</span></span>  
  
    -   <span data-ttu-id="75da3-116">Se si utilizza SQL Server 2016 o versioni successive, o [Database SQL di Azure](https://docs.microsoft.com/azure/sql-database/), creare un criterio di sicurezza che consente di aggiungere un predicato nella tabella per limitare le righe restituite a quelle che corrispondono a uno utente del database corrente (tramite il CURRENT_USER() la funzione predefinita) o il nome di account di accesso corrente (tramite la funzione predefinita SUSER_SNAME ()):</span><span class="sxs-lookup"><span data-stu-id="75da3-116">If you are using SQL Server 2016 or higher, or [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/), create a security policy that adds a predicate on the table restricting the rows returned to those that match either the current database user (using the CURRENT_USER() built-in function) or the current login name (using the SUSER_SNAME() built-in function):</span></span>  
  
        ```tsql  
        CREATE SCHEMA Security  
        GO  
  
        CREATE FUNCTION Security.userAccessPredicate(@UserName sysname)  
            RETURNS TABLE  
            WITH SCHEMABINDING  
        AS  
            RETURN SELECT 1 AS accessResult  
            WHERE @UserName = SUSER_SNAME()  
        GO  
  
        CREATE SECURITY POLICY Security.userAccessPolicy  
            ADD FILTER PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable,  
            ADD BLOCK PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable  
        GO  
        ```  
  
    -   <span data-ttu-id="75da3-117">Se si usa una versione di SQL Server precedente alla 2016, è possibile ottenere funzionalità simili usando una visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="75da3-117">If you are using a version of SQL Server prior to 2016, you can achieve similar functionality using a view:</span></span>  
  
        ```tsql  
        CREATE VIEW vw_MyTable  
        AS  
            RETURN SELECT * FROM MyTable  
            WHERE UserName = SUSER_SNAME()  
        GO  
        ```  
  
-   <span data-ttu-id="75da3-118">Creare stored procedure per selezionare, inserire, aggiornare ed eliminare i dati.</span><span class="sxs-lookup"><span data-stu-id="75da3-118">Create stored procedures to select, insert, update, and delete data.</span></span> <span data-ttu-id="75da3-119">Se il filtro viene applicato dai criteri di sicurezza, le stored procedure devono eseguire queste operazioni direttamente nella tabella di base. In caso contrario, se il filtro viene applicato da una visualizzazione, le stored procedure devono invece operare sulla visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="75da3-119">If the filtering is enacted by a security policy, the stored procedures should perform these operations on the base table directly; otherwise, if the filtering is enacted by a view, the stored procedures should instead operate against the view.</span></span> <span data-ttu-id="75da3-120">Il criterio di sicurezza o la visualizzazione filtrerà automaticamente le righe restituite o modificate dalle query utente e la stored procedure fornirà un limite di sicurezza più rigoroso per impedire che gli utenti con accesso diretto alle query eseguano query che possono dedurre l'esistenza di dati filtrati.</span><span class="sxs-lookup"><span data-stu-id="75da3-120">The security policy or view will automatically filter the rows returned or modified by user queries, and the stored procedure will provide a harder security boundary to prevent users with direct query access from successfully running queries that can infer the existence of filtered data.</span></span>  
  
-   <span data-ttu-id="75da3-121">Per le stored procedure che inseriscono dati, acquisire il nome utente usando la stessa funzione specificata nel criterio di sicurezza o nella visualizzazione e inserire tale valore nella colonna UserName.</span><span class="sxs-lookup"><span data-stu-id="75da3-121">For stored procedures that insert data, capture the user name using the same function specified in the security policy or view, and insert that value into the UserName column.</span></span>  
  
-   <span data-ttu-id="75da3-122">Negare al ruolo `public` tutte le autorizzazioni sulle tabelle (e sulle visualizzazioni, se pertinente).</span><span class="sxs-lookup"><span data-stu-id="75da3-122">Deny all permissions on the tables (and views, if applicable) to the `public` role.</span></span> <span data-ttu-id="75da3-123">Gli utenti non potranno ereditare autorizzazioni da altri ruoli del database perché il predicato del filtro è basato su nomi utenti o di accesso e non su ruoli.</span><span class="sxs-lookup"><span data-stu-id="75da3-123">Users will not be able to inherit permissions from other database roles, because the filter predicate is based on user or login names, not on roles.</span></span>  
  
-   <span data-ttu-id="75da3-124">Concedere ai ruoli del database l'autorizzazione EXECUTE sulle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="75da3-124">Grant EXECUTE on the stored procedures to database roles.</span></span> <span data-ttu-id="75da3-125">Gli utenti potranno accedere ai dati solo tramite le stored procedure specificate.</span><span class="sxs-lookup"><span data-stu-id="75da3-125">Users can only access data through the stored procedures provided.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="75da3-126">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="75da3-126">External Resources</span></span>  
 <span data-ttu-id="75da3-127">Per altre informazioni, vedere la seguente risorsa.</span><span class="sxs-lookup"><span data-stu-id="75da3-127">For more information, see the following resource.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75da3-128">[Implementazione della sicurezza a livello di riga e di cella nei database classificati con SQL Server 2005](http://go.microsoft.com/fwlink/?LinkId=98227) nel sito SQL Server TechCenter.</span><span class="sxs-lookup"><span data-stu-id="75da3-128">[Implementing Row- and Cell-Level Security in Classified Databases Using SQL Server 2005](http://go.microsoft.com/fwlink/?LinkId=98227) on the SQL Server TechCenter site.</span></span>|<span data-ttu-id="75da3-129">Viene descritto come usare la sicurezza a livello di riga e di cella per soddisfare requisiti di sicurezza dei database classificati.</span><span class="sxs-lookup"><span data-stu-id="75da3-129">Describes how to use row- and cell-level security to meet classified database security requirements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75da3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75da3-130">See Also</span></span>  
 [<span data-ttu-id="75da3-131">Sicurezza a livello di riga</span><span class="sxs-lookup"><span data-stu-id="75da3-131">Row-Level Security</span></span>](https://msdn.microsoft.com/library/dn765131.aspx)  
 [<span data-ttu-id="75da3-132">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="75da3-132">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="75da3-133">Cenni preliminari sulla sicurezza in SQL Server</span><span class="sxs-lookup"><span data-stu-id="75da3-133">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="75da3-134">Scenari di sicurezza delle applicazioni in SQL Server</span><span class="sxs-lookup"><span data-stu-id="75da3-134">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="75da3-135">Gestione delle autorizzazioni con stored procedure in SQL Server</span><span class="sxs-lookup"><span data-stu-id="75da3-135">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="75da3-136">Scrittura dinamica sicura in SQL Server</span><span class="sxs-lookup"><span data-stu-id="75da3-136">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="75da3-137">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="75da3-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
