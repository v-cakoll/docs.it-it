---
title: Introduzione all'integrazione CLR in SQL Server
description: L'integrazione di CLR con SQL Server supporta stored procedure, trigger, funzioni definite dall'utente, tipi definiti dall'utente e funzioni di aggregazione definite dall'utente nel codice gestito.
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: fa2ef68792d09cf94b3e0680a14bd79f9b593999
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286430"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="9a991-103">Introduzione all'integrazione CLR in SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a991-103">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="9a991-104">Common Language Runtime (CLR) rappresenta il fulcro di Microsoft .NET Framework e fornisce l'ambiente di esecuzione per tutto il codice .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a991-104">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="9a991-105">Il codice eseguito in CLR viene chiamato codice gestito.</span><span class="sxs-lookup"><span data-stu-id="9a991-105">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="9a991-106">CLR fornisce varie funzioni e servizi necessari per l'esecuzione del programma, incluse le funzioni di compilazione JIT (Just-In-Time), di allocazione e gestione della memoria, di imposizione dell'indipendenza dai tipi, di gestione delle eccezioni, di gestione dei thread e di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9a991-106">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="9a991-107">Grazie all'integrazione di CLR in Microsoft SQL Server, è possibile creare stored procedure, trigger, funzioni definite dall'utente, tipi definiti dall'utente e aggregazioni definite dall'utente nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="9a991-107">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="9a991-108">Poiché il codice gestito viene compilato nel codice nativo prima dell'esecuzione, è possibile ottenere notevoli miglioramenti delle prestazioni in alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="9a991-108">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="9a991-109">Il codice gestito usa la sicurezza dall'accesso di codice (CAS, Code Access Security), i collegamenti del codice e i domini dell'applicazione per impedire alle assembly di eseguire determinate operazioni.</span><span class="sxs-lookup"><span data-stu-id="9a991-109">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="9a991-110">In SQL Server viene usato CAS per proteggere il codice gestito e per impedire il danneggiamento del sistema operativo o del server di database.</span><span class="sxs-lookup"><span data-stu-id="9a991-110">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="9a991-111">In questa sezione vengono fornite solo le informazioni di base per iniziare a programmare con l'integrazione CLR di SQL Server. Tali informazioni non sono da considerarsi esaustive.</span><span class="sxs-lookup"><span data-stu-id="9a991-111">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="9a991-112">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="9a991-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="9a991-113">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9a991-113">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="9a991-114">Panoramica dell'integrazione con CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="9a991-114">Common Language Runtime (CLR) Integration Overview</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="9a991-115">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="9a991-115">Enabling CLR Integration</span></span>  
 <span data-ttu-id="9a991-116">In Microsoft SQL Server la funzionalità di integrazione CLR (Common Language Runtime) è disattivata per impostazione predefinita e deve essere abilitata in modo da usare oggetti implementati mediante l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="9a991-116">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="9a991-117">Per abilitare l'integrazione CLR mediante Transact-SQL, usare l'opzione `clr enabled` della stored procedure `sp_configure`, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9a991-117">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="9a991-118">È possibile disabilitare l'integrazione CLR impostando l'opzione `clr enabled` su 0.</span><span class="sxs-lookup"><span data-stu-id="9a991-118">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="9a991-119">Quando si disabilita l'integrazione CLR, SQL Server non esegue più le routine CLR e scarica tutti i domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a991-119">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="9a991-120">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="9a991-120">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="9a991-121">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9a991-121">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="9a991-122">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="9a991-122">Enabling CLR Integration</span></span>](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="9a991-123">Distribuzione di un assembly CLR</span><span class="sxs-lookup"><span data-stu-id="9a991-123">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="9a991-124">Dopo aver testato e verificato i metodi CLR sul server di prova, sarà possibile distribuirli a server di produzione utilizzando uno script di distribuzione</span><span class="sxs-lookup"><span data-stu-id="9a991-124">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="9a991-125">Lo script di distribuzione può essere generato manualmente o tramite SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="9a991-125">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="9a991-126">Per informazioni più dettagliate, vedere la versione di SQL Server documentazione per la versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="9a991-126">For more detailed information, see the version of SQL Server documentation for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="9a991-127">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9a991-127">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="9a991-128">Distribuzione di oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="9a991-128">Deploying CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="9a991-129">Sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="9a991-129">CLR Integration Security</span></span>  
 <span data-ttu-id="9a991-130">Il modello di sicurezza dell'integrazione di Microsoft SQL Server con CLR (Common Language Runtime) di Microsoft .NET Framework consente di gestire e di proteggere l'accesso tra diversi tipi di oggetti CLR e non CLR in esecuzione in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9a991-130">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="9a991-131">Questi oggetti possono essere chiamati da un'istruzione Transact-SQL o da un altro oggetto CLR in esecuzione sul server.</span><span class="sxs-lookup"><span data-stu-id="9a991-131">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="9a991-132">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="9a991-132">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="9a991-133">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9a991-133">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="9a991-134">Sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="9a991-134">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="9a991-135">Debug di un assembly CLR</span><span class="sxs-lookup"><span data-stu-id="9a991-135">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="9a991-136">Microsoft SQL Server fornisce il supporto per il debug di oggetti Transact-SQL e CLR (Common Language Runtime) nel database.</span><span class="sxs-lookup"><span data-stu-id="9a991-136">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="9a991-137">Il debug può essere eseguito in entrambi i linguaggi, ovvero gli utenti possono passare agevolmente da oggetti Transact-SQL a oggetti CLR e viceversa.</span><span class="sxs-lookup"><span data-stu-id="9a991-137">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="9a991-138">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="9a991-138">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="9a991-139">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9a991-139">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="9a991-140">Debug di oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="9a991-140">Debugging CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a><span data-ttu-id="9a991-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a991-141">See also</span></span>

- [<span data-ttu-id="9a991-142">Sicurezza dell'accesso di codice e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9a991-142">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="9a991-143">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9a991-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
