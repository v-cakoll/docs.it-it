---
title: Concessione di autorizzazioni a livello di riga in SQL Server
ms.date: 03/30/2017
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
ms.openlocfilehash: df5fcb4a6c73e12bec2ab17501fdfb02cf672324
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782360"
---
# <a name="granting-row-level-permissions-in-sql-server"></a><span data-ttu-id="20693-102">Concessione di autorizzazioni a livello di riga in SQL Server</span><span class="sxs-lookup"><span data-stu-id="20693-102">Granting Row-Level Permissions in SQL Server</span></span>

<span data-ttu-id="20693-103">In alcuni scenari è necessario controllare l'accesso a un livello caratterizzato da una maggior granularità rispetto a quanto consentito dalla semplice concessione, revoca o negazione delle autorizzazioni sui dati.</span><span class="sxs-lookup"><span data-stu-id="20693-103">In some scenarios, there is a requirement to control access to data at a more granular level than what simply granting, revoking, or denying permissions provides.</span></span> <span data-ttu-id="20693-104">Ad esempio, in un'applicazione di database usata in un ospedale potrebbe essere necessario consentire ai medici di visualizzare solo le informazioni correlate ai propri pazienti.</span><span class="sxs-lookup"><span data-stu-id="20693-104">For example, a hospital database application may require individual Doctors to be restricted to accessing information related to only their patients.</span></span> <span data-ttu-id="20693-105">Scenari simili sono presenti in molti ambienti, tra cui quelli delle applicazioni destinate al settore finanziario, legale, statale e militare.</span><span class="sxs-lookup"><span data-stu-id="20693-105">Similar requirements exist in many environments, including finance, law, government, and military applications.</span></span> <span data-ttu-id="20693-106">Per contribuire a gestire questi scenari, SQL Server 2016 fornisce una funzionalità di [sicurezza a livello di riga](/sql/relational-databases/security/row-level-security) che semplifica e centralizza la logica di accesso a livello di riga in un criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="20693-106">To help address these scenarios, SQL Server 2016 provides a [Row-Level Security](/sql/relational-databases/security/row-level-security) feature that simplifies and centralizes row-level access logic in a security policy.</span></span> <span data-ttu-id="20693-107">Per le versioni precedenti di SQL Server, una funzionalità simile può essere ottenuta usando le visualizzazioni per applicare filtri a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="20693-107">For earlier versions of SQL Server, similar functionality can be achieved by using views to enact row-level filtering.</span></span>

## <a name="implementing-row-level-filtering"></a><span data-ttu-id="20693-108">Implementazione di applicazione di filtri a livello di riga</span><span class="sxs-lookup"><span data-stu-id="20693-108">Implementing Row-level Filtering</span></span>

<span data-ttu-id="20693-109">L'applicazione di filtri a livello di riga viene usata per applicazioni che archiviano informazioni in un'unica tabella, come nell'esempio dell'ospedale.</span><span class="sxs-lookup"><span data-stu-id="20693-109">Row-level filtering is used for applications storing information in a single table like in the hospital example above.</span></span> <span data-ttu-id="20693-110">Per applicare i filtri a livello di riga, ogni riga include una colonna che definisce un parametro discriminante, ad esempio un nome utente, un'etichetta o un altro identificatore.</span><span class="sxs-lookup"><span data-stu-id="20693-110">To implement row-level filtering each row has a column that defines a differentiating parameter, such as a user name, label or other identifier.</span></span> <span data-ttu-id="20693-111">È possibile creare un criterio di sicurezza o una visualizzazione nella tabella, che consente di filtrare le righe a cui l'utente può accedere.</span><span class="sxs-lookup"><span data-stu-id="20693-111">You create either a security policy or a view on the table, which filters the rows that the user can access.</span></span> <span data-ttu-id="20693-112">È possibile quindi creare stored procedure con parametri, che controllano i tipi di query, che l'utente può eseguire.</span><span class="sxs-lookup"><span data-stu-id="20693-112">You then create parameterized stored procedures, which control the types of queries the user can execute.</span></span>

<span data-ttu-id="20693-113">L'esempio seguente descrive come configurare l'applicazione di filtri a livello di riga basati su un nome utente o un nome di accesso:</span><span class="sxs-lookup"><span data-stu-id="20693-113">The following example describes how to configure row-level filtering based on a user or login name:</span></span>

- <span data-ttu-id="20693-114">Creare la tabella, aggiungendo una colonna per l'archiviazione del nome.</span><span class="sxs-lookup"><span data-stu-id="20693-114">Create the table, adding a column to store the name.</span></span>

- <span data-ttu-id="20693-115">Abilitare l'applicazione di filtri a livello di riga:</span><span class="sxs-lookup"><span data-stu-id="20693-115">Enable row-level filtering:</span></span>

  - <span data-ttu-id="20693-116">Se si usa SQL Server 2016 o versioni successive oppure il [database SQL di Azure](https://docs.microsoft.com/azure/sql-database/), creare un criterio di sicurezza che aggiunga un predicato nella tabella per limitare le righe restituite a quelle che corrispondono all'utente del database corrente (usando la funzione predefinita CURRENT_USER()) o il nome di accesso corrente (usando la funzione predefinita SUSER_SNAME()):</span><span class="sxs-lookup"><span data-stu-id="20693-116">If you are using SQL Server 2016 or higher, or [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/), create a security policy that adds a predicate on the table restricting the rows returned to those that match either the current database user (using the CURRENT_USER() built-in function) or the current login name (using the SUSER_SNAME() built-in function):</span></span>

      ```sql
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

  - <span data-ttu-id="20693-117">Se si usa una versione di SQL Server precedente alla 2016, è possibile ottenere funzionalità simili usando una visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="20693-117">If you are using a version of SQL Server prior to 2016, you can achieve similar functionality using a view:</span></span>

      ```sql
      CREATE VIEW vw_MyTable
      AS
          RETURN SELECT * FROM MyTable
          WHERE UserName = SUSER_SNAME()
      GO
      ```

- <span data-ttu-id="20693-118">Creare stored procedure per selezionare, inserire, aggiornare ed eliminare i dati.</span><span class="sxs-lookup"><span data-stu-id="20693-118">Create stored procedures to select, insert, update, and delete data.</span></span> <span data-ttu-id="20693-119">Se il filtro viene applicato dai criteri di sicurezza, le stored procedure devono eseguire queste operazioni direttamente nella tabella di base. In caso contrario, se il filtro viene applicato da una visualizzazione, le stored procedure devono invece operare sulla visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="20693-119">If the filtering is enacted by a security policy, the stored procedures should perform these operations on the base table directly; otherwise, if the filtering is enacted by a view, the stored procedures should instead operate against the view.</span></span> <span data-ttu-id="20693-120">Il criterio di sicurezza o la visualizzazione filtrerà automaticamente le righe restituite o modificate dalle query utente e la stored procedure fornirà un limite di sicurezza più rigoroso per impedire che gli utenti con accesso diretto alle query eseguano query che possono dedurre l'esistenza di dati filtrati.</span><span class="sxs-lookup"><span data-stu-id="20693-120">The security policy or view will automatically filter the rows returned or modified by user queries, and the stored procedure will provide a harder security boundary to prevent users with direct query access from successfully running queries that can infer the existence of filtered data.</span></span>

- <span data-ttu-id="20693-121">Per le stored procedure che inseriscono dati, acquisire il nome utente usando la stessa funzione specificata nel criterio di sicurezza o nella visualizzazione e inserire tale valore nella colonna UserName.</span><span class="sxs-lookup"><span data-stu-id="20693-121">For stored procedures that insert data, capture the user name using the same function specified in the security policy or view, and insert that value into the UserName column.</span></span>

- <span data-ttu-id="20693-122">Negare al ruolo `public` tutte le autorizzazioni sulle tabelle (e sulle visualizzazioni, se pertinente).</span><span class="sxs-lookup"><span data-stu-id="20693-122">Deny all permissions on the tables (and views, if applicable) to the `public` role.</span></span> <span data-ttu-id="20693-123">Gli utenti non potranno ereditare autorizzazioni da altri ruoli del database perché il predicato del filtro è basato su nomi utenti o di accesso e non su ruoli.</span><span class="sxs-lookup"><span data-stu-id="20693-123">Users will not be able to inherit permissions from other database roles, because the filter predicate is based on user or login names, not on roles.</span></span>

- <span data-ttu-id="20693-124">Concedere ai ruoli del database l'autorizzazione EXECUTE sulle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="20693-124">Grant EXECUTE on the stored procedures to database roles.</span></span> <span data-ttu-id="20693-125">Gli utenti potranno accedere ai dati solo tramite le stored procedure specificate.</span><span class="sxs-lookup"><span data-stu-id="20693-125">Users can only access data through the stored procedures provided.</span></span>

## <a name="see-also"></a><span data-ttu-id="20693-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20693-126">See also</span></span>

- [<span data-ttu-id="20693-127">Sicurezza a livello di riga</span><span class="sxs-lookup"><span data-stu-id="20693-127">Row-Level Security</span></span>](/sql/relational-databases/security/row-level-security)
- [<span data-ttu-id="20693-128">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="20693-128">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="20693-129">Cenni preliminari sulla sicurezza in SQL Server</span><span class="sxs-lookup"><span data-stu-id="20693-129">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)
- [<span data-ttu-id="20693-130">Scenari di sicurezza delle applicazioni in SQL Server</span><span class="sxs-lookup"><span data-stu-id="20693-130">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="20693-131">Gestione delle autorizzazioni con stored procedure in SQL Server</span><span class="sxs-lookup"><span data-stu-id="20693-131">Managing Permissions with Stored Procedures in SQL Server</span></span>](managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="20693-132">Scrittura dinamica sicura in SQL Server</span><span class="sxs-lookup"><span data-stu-id="20693-132">Writing Secure Dynamic SQL in SQL Server</span></span>](writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="20693-133">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="20693-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
