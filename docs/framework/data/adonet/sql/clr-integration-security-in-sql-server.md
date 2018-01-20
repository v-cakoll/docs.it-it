---
title: Sicurezza dell'integrazione CLR in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 37437d827fc0ff6583178f33f4cceaa86f5175dd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="998fe-102">Sicurezza dell'integrazione CLR in SQL Server</span><span class="sxs-lookup"><span data-stu-id="998fe-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="998fe-103">Microsoft SQL Server fornisce l'integrazione del componente CLR di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="998fe-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="998fe-104">L'integrazione CLR consente di possibile scrivere stored procedure, trigger, tipi definiti dall'utente, funzioni definite dall'utente, aggregati definiti dall'utente e funzioni con valori di tabella di flusso usando qualsiasi linguaggio di .NET Framework, inclusi Microsoft Visual Basic .NET e Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="998fe-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="998fe-105">CLR supporta un modello di sicurezza per il codice gestito denominato CAS (Code Access Security).</span><span class="sxs-lookup"><span data-stu-id="998fe-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="998fe-106">In questo modello, le autorizzazioni vengono concesse agli assembly in base all'evidenza fornita dal codice nei metadati.</span><span class="sxs-lookup"><span data-stu-id="998fe-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="998fe-107">In SQL Server il modello di sicurezza basato su utente di SQL Server si integra con il modello di sicurezza basato su accesso al codice di CLR.</span><span class="sxs-lookup"><span data-stu-id="998fe-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="998fe-108">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="998fe-108">External Resources</span></span>  
 <span data-ttu-id="998fe-109">Per altre informazioni sull'integrazione di CLR con SQL Server, vedere le risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="998fe-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="998fe-110">Risorsa</span><span class="sxs-lookup"><span data-stu-id="998fe-110">Resource</span></span>|<span data-ttu-id="998fe-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="998fe-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="998fe-112">Sicurezza dall'accesso di codice</span><span class="sxs-lookup"><span data-stu-id="998fe-112">Code Access Security</span></span>](http://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03)|<span data-ttu-id="998fe-113">Contiene argomenti in cui viene descritta la sicurezza dall'accesso di codice in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="998fe-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="998fe-114">Sicurezza dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="998fe-114">CLR Integration Security</span></span>](http://go.microsoft.com/fwlink/?LinkId=59998)|<span data-ttu-id="998fe-115">Viene descritto il modello di sicurezza per il codice gestito in esecuzione in SQL Server</span><span class="sxs-lookup"><span data-stu-id="998fe-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="998fe-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="998fe-116">See Also</span></span>  
 [<span data-ttu-id="998fe-117">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="998fe-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="998fe-118">Scenari di sicurezza delle applicazioni in SQL Server</span><span class="sxs-lookup"><span data-stu-id="998fe-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="998fe-119">Integrazione di Common Language Runtime di SQL Server</span><span class="sxs-lookup"><span data-stu-id="998fe-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [<span data-ttu-id="998fe-120">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="998fe-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
