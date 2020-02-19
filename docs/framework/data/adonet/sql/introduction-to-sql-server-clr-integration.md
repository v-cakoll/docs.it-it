---
title: Introduzione all'integrazione CLR in SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: 41dd89af4f45c673cf6b7283fc39aaf91fd9963c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452409"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="872fd-102">Introduzione all'integrazione CLR in SQL Server</span><span class="sxs-lookup"><span data-stu-id="872fd-102">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="872fd-103">Common Language Runtime (CLR) rappresenta l'elemento essenziale di Microsoft .NET Framework e fornisce l'ambiente di esecuzione per tutto il codice .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="872fd-103">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="872fd-104">Il codice eseguito all'interno di CLR viene definito codice gestito.</span><span class="sxs-lookup"><span data-stu-id="872fd-104">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="872fd-105">CLR fornisce diverse funzioni e vari servizi richiesti per l'esecuzione del programma, che includono la compilazione JIT (Just-In-Time), l'allocazione e la gestione della memoria, l'applicazione dell'indipendenza dai tipi, la gestione delle eccezioni e dei thread e la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="872fd-105">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="872fd-106">Con CLR incluso in Microsoft SQL Server (integrazione di CLR), è possibile creare nuove stored procedure, trigger, funzioni definite dall'utente e aggregati definiti dall'utente nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="872fd-106">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="872fd-107">Poiché il codice gestito viene processato con il codice nativo prima dell'esecuzione, in determinati scenari è possibile ottenere significativi aumenti di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="872fd-107">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="872fd-108">Il codice gestito usa la sicurezza dall'accesso di codice (CAS, Code Access Security), i collegamenti del codice e i domini dell'applicazione per impedire alle assembly di eseguire determinate operazioni.</span><span class="sxs-lookup"><span data-stu-id="872fd-108">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="872fd-109">In SQL Server viene usato CAS per proteggere il codice gestito e per impedire il danneggiamento del sistema operativo o del server di database.</span><span class="sxs-lookup"><span data-stu-id="872fd-109">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="872fd-110">In questa sezione vengono fornite solo le informazioni di base per iniziare a programmare con l'integrazione CLR di SQL Server. Tali informazioni non sono da considerarsi esaustive.</span><span class="sxs-lookup"><span data-stu-id="872fd-110">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="872fd-111">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="872fd-111">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="872fd-112">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="872fd-112">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="872fd-113">Panoramica dell'integrazione con CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="872fd-113">Common Language Runtime (CLR) Integration Overview</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="872fd-114">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="872fd-114">Enabling CLR Integration</span></span>  
 <span data-ttu-id="872fd-115">In Microsoft SQL Server la funzionalità di integrazione CLR (Common Language Runtime) è disattivata per impostazione predefinita e deve essere abilitata in modo da usare oggetti implementati mediante l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="872fd-115">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="872fd-116">Per abilitare l'integrazione CLR mediante Transact-SQL, usare l'opzione `clr enabled` della stored procedure `sp_configure`, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="872fd-116">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="872fd-117">È possibile disabilitare l'integrazione CLR impostando l'opzione `clr enabled` su 0.</span><span class="sxs-lookup"><span data-stu-id="872fd-117">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="872fd-118">Quando si disabilita l'integrazione CLR, SQL Server non esegue più le routine CLR e scarica tutti i domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="872fd-118">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="872fd-119">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="872fd-119">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="872fd-120">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="872fd-120">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="872fd-121">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="872fd-121">Enabling CLR Integration</span></span>](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="872fd-122">Distribuzione di un assembly CLR</span><span class="sxs-lookup"><span data-stu-id="872fd-122">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="872fd-123">Dopo che i metodi CLR sono stati testati e verificati nel server di prova, possono essere distribuiti nei server di produzione usando uno script di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="872fd-123">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="872fd-124">Lo script di distribuzione può essere generato manualmente o tramite SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="872fd-124">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="872fd-125">Per informazioni più dettagliate, vedere la versione di SQL Server documentazione per la versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="872fd-125">For more detailed information, see the version of SQL Server documentation for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="872fd-126">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="872fd-126">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="872fd-127">Distribuzione di oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="872fd-127">Deploying CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="872fd-128">Sicurezza dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="872fd-128">CLR Integration Security</span></span>  
 <span data-ttu-id="872fd-129">Il modello di sicurezza dell'integrazione di Microsoft SQL Server con CLR (Common Language Runtime) di Microsoft .NET Framework consente di gestire e di proteggere l'accesso tra diversi tipi di oggetti CLR e non CLR in esecuzione in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="872fd-129">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="872fd-130">Questi oggetti possono essere chiamati da un'istruzione Transact-SQL o da un altro oggetto CLR in esecuzione sul server.</span><span class="sxs-lookup"><span data-stu-id="872fd-130">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="872fd-131">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="872fd-131">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="872fd-132">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="872fd-132">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="872fd-133">Sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="872fd-133">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="872fd-134">Debug di un assembly CLR</span><span class="sxs-lookup"><span data-stu-id="872fd-134">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="872fd-135">Microsoft SQL Server fornisce il supporto per il debug di oggetti Transact-SQL e CLR (Common Language Runtime) nel database.</span><span class="sxs-lookup"><span data-stu-id="872fd-135">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="872fd-136">Il debug può essere eseguito in entrambi i linguaggi, ovvero gli utenti possono passare agevolmente da oggetti Transact-SQL a oggetti CLR e viceversa.</span><span class="sxs-lookup"><span data-stu-id="872fd-136">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="872fd-137">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="872fd-137">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="872fd-138">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="872fd-138">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="872fd-139">Debug di oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="872fd-139">Debugging CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a><span data-ttu-id="872fd-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="872fd-140">See also</span></span>

- [<span data-ttu-id="872fd-141">Sicurezza dell'accesso di codice e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="872fd-141">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="872fd-142">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="872fd-142">ADO.NET Overview</span></span>](../ado-net-overview.md)
