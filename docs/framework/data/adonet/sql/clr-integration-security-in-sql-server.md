---
title: Sicurezza dell'integrazione CLR in SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: 946401211d515df9ba5b9e38d7cfd10730973b64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165815"
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="d472c-102">Sicurezza dell'integrazione CLR in SQL Server</span><span class="sxs-lookup"><span data-stu-id="d472c-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="d472c-103">Microsoft SQL Server fornisce l'integrazione del componente CLR di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d472c-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="d472c-104">L'integrazione CLR consente di possibile scrivere stored procedure, trigger, tipi definiti dall'utente, funzioni definite dall'utente, aggregati definiti dall'utente e funzioni con valori di tabella di flusso usando qualsiasi linguaggio di .NET Framework, inclusi Microsoft Visual Basic .NET e Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d472c-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="d472c-105">CLR supporta un modello di sicurezza per il codice gestito denominato CAS (Code Access Security).</span><span class="sxs-lookup"><span data-stu-id="d472c-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="d472c-106">In questo modello, le autorizzazioni vengono concesse agli assembly in base all'evidenza fornita dal codice nei metadati.</span><span class="sxs-lookup"><span data-stu-id="d472c-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="d472c-107">In SQL Server il modello di sicurezza basato su utente di SQL Server si integra con il modello di sicurezza basato su accesso al codice di CLR.</span><span class="sxs-lookup"><span data-stu-id="d472c-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="d472c-108">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="d472c-108">External Resources</span></span>  
 <span data-ttu-id="d472c-109">Per altre informazioni sull'integrazione di CLR con SQL Server, vedere le risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="d472c-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="d472c-110">Risorsa</span><span class="sxs-lookup"><span data-stu-id="d472c-110">Resource</span></span>|<span data-ttu-id="d472c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d472c-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="d472c-112">Sicurezza per l'accesso al codice</span><span class="sxs-lookup"><span data-stu-id="d472c-112">Code Access Security</span></span>](../../../../../docs/framework/misc/code-access-security.md)|<span data-ttu-id="d472c-113">Contiene argomenti in cui viene descritta la sicurezza dall'accesso di codice in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d472c-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="d472c-114">Sicurezza dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="d472c-114">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)|<span data-ttu-id="d472c-115">Viene descritto il modello di sicurezza per il codice gestito in esecuzione in SQL Server</span><span class="sxs-lookup"><span data-stu-id="d472c-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d472c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d472c-116">See also</span></span>

- [<span data-ttu-id="d472c-117">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d472c-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="d472c-118">Scenari di sicurezza delle applicazioni in SQL Server</span><span class="sxs-lookup"><span data-stu-id="d472c-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="d472c-119">Integrazione di Common Language Runtime di SQL Server</span><span class="sxs-lookup"><span data-stu-id="d472c-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)
- [<span data-ttu-id="d472c-120">Cenni preliminari su ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d472c-120">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)
