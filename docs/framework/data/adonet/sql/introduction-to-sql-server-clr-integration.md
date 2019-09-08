---
title: Introduzione all'integrazione CLR in SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: fb812a8e524148c507d26ea32e0b4263a4998153
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782269"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="1a42f-102">Introduzione all'integrazione CLR in SQL Server</span><span class="sxs-lookup"><span data-stu-id="1a42f-102">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="1a42f-103">Common Language Runtime (CLR) rappresenta l'elemento essenziale di Microsoft .NET Framework e fornisce l'ambiente di esecuzione per tutto il codice .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a42f-103">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="1a42f-104">Il codice eseguito all'interno di CLR viene definito codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1a42f-104">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="1a42f-105">CLR fornisce diverse funzioni e vari servizi richiesti per l'esecuzione del programma, che includono la compilazione JIT (Just-In-Time), l'allocazione e la gestione della memoria, l'applicazione dell'indipendenza dai tipi, la gestione delle eccezioni e dei thread e la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1a42f-105">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="1a42f-106">Con CLR incluso in Microsoft SQL Server (integrazione di CLR), è possibile creare nuove stored procedure, trigger, funzioni definite dall'utente e aggregati definiti dall'utente nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1a42f-106">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="1a42f-107">Poiché il codice gestito viene processato con il codice nativo prima dell'esecuzione, in determinati scenari è possibile ottenere significativi aumenti di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1a42f-107">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="1a42f-108">Il codice gestito usa la sicurezza dall'accesso di codice (CAS, Code Access Security), i collegamenti del codice e i domini dell'applicazione per impedire alle assembly di eseguire determinate operazioni.</span><span class="sxs-lookup"><span data-stu-id="1a42f-108">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="1a42f-109">In SQL Server viene usato CAS per proteggere il codice gestito e per impedire il danneggiamento del sistema operativo o del server di database.</span><span class="sxs-lookup"><span data-stu-id="1a42f-109">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="1a42f-110">In questa sezione vengono fornite solo le informazioni di base per iniziare a programmare con l'integrazione CLR di SQL Server. Tali informazioni non sono da considerarsi esaustive.</span><span class="sxs-lookup"><span data-stu-id="1a42f-110">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="1a42f-111">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="1a42f-111">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="1a42f-112">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1a42f-112">**SQL Server Books Online**</span></span>  
  
- [<span data-ttu-id="1a42f-113">Panoramica dell'integrazione con CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="1a42f-113">Common Language Runtime (CLR) Integration Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=115242)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="1a42f-114">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="1a42f-114">Enabling CLR Integration</span></span>  
 <span data-ttu-id="1a42f-115">In Microsoft SQL Server la funzionalità di integrazione CLR (Common Language Runtime) è disattivata per impostazione predefinita e deve essere abilitata in modo da usare oggetti implementati mediante l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="1a42f-115">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="1a42f-116">Per abilitare l'integrazione CLR mediante Transact-SQL, usare l'opzione `clr enabled` della stored procedure `sp_configure`, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1a42f-116">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="1a42f-117">È possibile disabilitare l'integrazione CLR impostando l'opzione `clr enabled` su 0.</span><span class="sxs-lookup"><span data-stu-id="1a42f-117">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="1a42f-118">Quando si disabilita l'integrazione CLR, SQL Server non esegue più le routine CLR e scarica tutti i domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1a42f-118">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="1a42f-119">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="1a42f-119">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="1a42f-120">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1a42f-120">**SQL Server Books Online**</span></span>  
  
- [<span data-ttu-id="1a42f-121">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="1a42f-121">Enabling CLR Integration</span></span>](https://go.microsoft.com/fwlink/?LinkId=115230)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="1a42f-122">Distribuzione di un assembly CLR</span><span class="sxs-lookup"><span data-stu-id="1a42f-122">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="1a42f-123">Dopo che i metodi CLR sono stati testati e verificati nel server di prova, possono essere distribuiti nei server di produzione usando uno script di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1a42f-123">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="1a42f-124">Lo script di distribuzione può essere generato manualmente o tramite SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="1a42f-124">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="1a42f-125">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="1a42f-125">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="1a42f-126">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1a42f-126">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="1a42f-127">Distribuzione di oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="1a42f-127">Deploying CLR Database Objects</span></span>](https://go.microsoft.com/fwlink/?LinkId=115232)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="1a42f-128">Sicurezza dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="1a42f-128">CLR Integration Security</span></span>  
 <span data-ttu-id="1a42f-129">Il modello di sicurezza dell'integrazione di Microsoft SQL Server con CLR (Common Language Runtime) di Microsoft .NET Framework consente di gestire e di proteggere l'accesso tra diversi tipi di oggetti CLR e non CLR in esecuzione in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1a42f-129">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="1a42f-130">Questi oggetti possono essere chiamati da un'istruzione Transact-SQL o da un altro oggetto CLR in esecuzione sul server.</span><span class="sxs-lookup"><span data-stu-id="1a42f-130">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="1a42f-131">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="1a42f-131">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="1a42f-132">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1a42f-132">**SQL Server Books Online**</span></span>  
  
- [<span data-ttu-id="1a42f-133">Sicurezza dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="1a42f-133">CLR Integration Security</span></span>](https://go.microsoft.com/fwlink/?LinkId=115234)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="1a42f-134">Debug di un assembly CLR</span><span class="sxs-lookup"><span data-stu-id="1a42f-134">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="1a42f-135">Microsoft SQL Server fornisce il supporto per il debug di oggetti Transact-SQL e CLR (Common Language Runtime) nel database.</span><span class="sxs-lookup"><span data-stu-id="1a42f-135">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="1a42f-136">Il debug può essere eseguito in entrambi i linguaggi, ovvero gli utenti possono passare agevolmente da oggetti Transact-SQL a oggetti CLR e viceversa.</span><span class="sxs-lookup"><span data-stu-id="1a42f-136">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="1a42f-137">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="1a42f-137">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="1a42f-138">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1a42f-138">**SQL Server Books Online**</span></span>  
  
- [<span data-ttu-id="1a42f-139">Debug di oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="1a42f-139">Debugging CLR Database Objects</span></span>](https://go.microsoft.com/fwlink/?LinkId=115236)  
  
## <a name="see-also"></a><span data-ttu-id="1a42f-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a42f-140">See also</span></span>

- [<span data-ttu-id="1a42f-141">Sicurezza dell'accesso di codice e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1a42f-141">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="1a42f-142">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1a42f-142">ADO.NET Overview</span></span>](../ado-net-overview.md)
