---
title: Introduzione all'integrazione CLR in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ab9dad1031979169aee99a7bb6bc5fe409954e9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="4ab35-102">Introduzione all'integrazione CLR in SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ab35-102">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="4ab35-103">Common Language Runtime (CLR) rappresenta l'elemento essenziale di Microsoft .NET Framework e fornisce l'ambiente di esecuzione per tutto il codice .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ab35-103">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="4ab35-104">Il codice eseguito all'interno di CLR viene definito codice gestito.</span><span class="sxs-lookup"><span data-stu-id="4ab35-104">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="4ab35-105">CLR fornisce diverse funzioni e vari servizi richiesti per l'esecuzione del programma, che includono la compilazione JIT (Just-In-Time), l'allocazione e la gestione della memoria, l'applicazione dell'indipendenza dai tipi, la gestione delle eccezioni e dei thread e la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4ab35-105">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="4ab35-106">Con CLR incluso in Microsoft SQL Server (integrazione di CLR), è possibile creare nuove stored procedure, trigger, funzioni definite dall'utente e aggregati definiti dall'utente nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="4ab35-106">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="4ab35-107">Poiché il codice gestito viene processato con il codice nativo prima dell'esecuzione, in determinati scenari è possibile ottenere significativi aumenti di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4ab35-107">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="4ab35-108">Il codice gestito usa la sicurezza dall'accesso di codice (CAS, Code Access Security), i collegamenti del codice e i domini dell'applicazione per impedire alle assembly di eseguire determinate operazioni.</span><span class="sxs-lookup"><span data-stu-id="4ab35-108">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="4ab35-109">In SQL Server viene usato CAS per proteggere il codice gestito e per impedire il danneggiamento del sistema operativo o del server di database.</span><span class="sxs-lookup"><span data-stu-id="4ab35-109">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="4ab35-110">In questa sezione vengono fornite solo le informazioni di base per iniziare a programmare con l'integrazione CLR di SQL Server. Tali informazioni non sono da considerarsi esaustive.</span><span class="sxs-lookup"><span data-stu-id="4ab35-110">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="4ab35-111">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="4ab35-111">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="4ab35-112">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4ab35-112">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="4ab35-113">Panoramica dell'integrazione con Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="4ab35-113">Common Language Runtime (CLR) Integration Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=115242)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="4ab35-114">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="4ab35-114">Enabling CLR Integration</span></span>  
 <span data-ttu-id="4ab35-115">In Microsoft SQL Server la funzione di integrazione CLR (Common Language Runtime) è disattivata per impostazione predefinita e deve essere abilitata in modo da usare oggetti implementati mediante l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="4ab35-115">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="4ab35-116">Per abilitare l'integrazione CLR mediante Transact-SQL, usare l'opzione `clr enabled` della stored procedure `sp_configure`, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4ab35-116">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="4ab35-117">È possibile disabilitare l'integrazione CLR impostando l'opzione `clr enabled` su 0.</span><span class="sxs-lookup"><span data-stu-id="4ab35-117">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="4ab35-118">Quando si disabilita l'integrazione CLR, SQL Server non esegue più le routine CLR e scarica tutti i domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ab35-118">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="4ab35-119">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="4ab35-119">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="4ab35-120">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4ab35-120">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="4ab35-121">Attivazione dell'integrazione CLR</span><span class="sxs-lookup"><span data-stu-id="4ab35-121">Enabling CLR Integration</span></span>](http://go.microsoft.com/fwlink/?LinkId=115230)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="4ab35-122">Distribuzione di un assembly CLR</span><span class="sxs-lookup"><span data-stu-id="4ab35-122">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="4ab35-123">Dopo che i metodi CLR sono stati testati e verificati nel server di prova, possono essere distribuiti nei server di produzione usando uno script di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4ab35-123">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="4ab35-124">Lo script di distribuzione può essere generato manualmente o tramite SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="4ab35-124">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="4ab35-125">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="4ab35-125">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="4ab35-126">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4ab35-126">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="4ab35-127">Distribuzione di oggetti di Database CLR</span><span class="sxs-lookup"><span data-stu-id="4ab35-127">Deploying CLR Database Objects</span></span>](http://go.microsoft.com/fwlink/?LinkId=115232)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="4ab35-128">Sicurezza dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="4ab35-128">CLR Integration Security</span></span>  
 <span data-ttu-id="4ab35-129">Il modello di sicurezza dell'integrazione di Microsoft SQL Server con CLR (Common Language Runtime) di Microsoft .NET Framework consente di gestire e di proteggere l'accesso tra diversi tipi di oggetti CLR e non CLR in esecuzione in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4ab35-129">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="4ab35-130">Questi oggetti possono essere chiamati da un'istruzione Transact-SQL o da un altro oggetto CLR in esecuzione sul server.</span><span class="sxs-lookup"><span data-stu-id="4ab35-130">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="4ab35-131">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="4ab35-131">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="4ab35-132">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4ab35-132">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="4ab35-133">Sicurezza dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="4ab35-133">CLR Integration Security</span></span>](http://go.microsoft.com/fwlink/?LinkId=115234)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="4ab35-134">Debug di un assembly CLR</span><span class="sxs-lookup"><span data-stu-id="4ab35-134">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="4ab35-135">Microsoft SQL Server fornisce il supporto per il debug di oggetti Transact-SQL e CLR (Common Language Runtime) nel database.</span><span class="sxs-lookup"><span data-stu-id="4ab35-135">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="4ab35-136">Il debug può essere eseguito in entrambi i linguaggi, ovvero gli utenti possono passare agevolmente da oggetti Transact-SQL a oggetti CLR e viceversa.</span><span class="sxs-lookup"><span data-stu-id="4ab35-136">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="4ab35-137">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="4ab35-137">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="4ab35-138">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4ab35-138">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="4ab35-139">Debug di oggetti di Database CLR</span><span class="sxs-lookup"><span data-stu-id="4ab35-139">Debugging CLR Database Objects</span></span>](http://go.microsoft.com/fwlink/?LinkId=115236)  
  
## <a name="see-also"></a><span data-ttu-id="4ab35-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ab35-140">See Also</span></span>  
 [<span data-ttu-id="4ab35-141">Creazione di oggetti di SQL Server 2005 nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="4ab35-141">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="4ab35-142">Sicurezza dall'accesso di codice e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4ab35-142">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [<span data-ttu-id="4ab35-143">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="4ab35-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
