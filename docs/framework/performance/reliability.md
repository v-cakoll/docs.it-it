---
title: Affidabilità
description: Informazioni sull'affidabilità in .NET. Protezione dalle eccezioni asincrone negli host che eseguono in .NET, ad esempio SQL Server.
ms.date: 03/30/2017
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
ms.openlocfilehash: ce9ffbb7f58c2f5dc016c56c0e2ce13b45c30f26
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474254"
---
# <a name="reliability"></a><span data-ttu-id="2eb26-104">Affidabilità</span><span class="sxs-lookup"><span data-stu-id="2eb26-104">Reliability</span></span>
<span data-ttu-id="2eb26-105">È importante che il codice in esecuzione in ambienti server, ad esempio SQL Server, fornisca protezione contro le eccezioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="2eb26-105">It is important that code executing in server environments such as SQL Server protect against asynchronous exceptions.</span></span> <span data-ttu-id="2eb26-106">L'affidabilità, come descritto in questo argomento, non è specifica di SQL Server, ma della scrittura di codice affidabile per qualsiasi host in esecuzione in un ambiente .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="2eb26-106">Reliability, as discussed here, is not specific to SQL Server but to writing reliable code for any host executing in a .NET Framework version 2.0 environment.</span></span> <span data-ttu-id="2eb26-107">SQL Server è tuttavia il primo servizio che fa un uso completo delle nuove funzionalità di affidabilità della versione 2.0, quindi viene usato come esempio.</span><span class="sxs-lookup"><span data-stu-id="2eb26-107">However, SQL Server is the first service making extensive use of the new reliability features of version 2.0, so it is used as an example.</span></span>  
  
 <span data-ttu-id="2eb26-108">Il codice in esecuzione in SQL Server deve rispettare linee guida per l'affidabilità più rigorose rispetto ad altri ambienti server.</span><span class="sxs-lookup"><span data-stu-id="2eb26-108">Code running in SQL Server must deal with more stringent reliability guidelines than other server environments.</span></span> <span data-ttu-id="2eb26-109">Ciò è dovuto al funzionamento stabile di SQL Server fino al limite estremo di utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2eb26-109">This is due to SQL Server’s steady operation at the edge of resource consumption.</span></span>  <span data-ttu-id="2eb26-110">Le eccezioni <xref:System.OutOfMemoryException> e <xref:System.Threading.ThreadAbortException> non sono rare nell'ambiente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2eb26-110"><xref:System.OutOfMemoryException> and <xref:System.Threading.ThreadAbortException> exceptions are not uncommon in the SQL Server environment.</span></span> <span data-ttu-id="2eb26-111">Queste linee guida in generale sono incentrate meno sull'affidabilità e più su come consentire al codice gestito completamente attendibile di generare un errore non grave in caso di riciclo a livello di <xref:System.AppDomain>, che rappresenta il modo principale in cui il server mantiene la coerenza e la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2eb26-111">These guidelines in general are focused less on reliability and more on allowing fully trusted managed code to fail gracefully in the face of <xref:System.AppDomain>-level recycling, which is the primary way the server maintains consistency and availability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2eb26-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2eb26-112">In This Section</span></span>  
 [<span data-ttu-id="2eb26-113">programmazione per SQL Server e attributi di protezione host</span><span class="sxs-lookup"><span data-stu-id="2eb26-113">SQL Server Programming and Host Protection Attributes</span></span>](sql-server-programming-and-host-protection-attributes.md)  
 <span data-ttu-id="2eb26-114">Descrive come viene usato l'attributo <xref:System.Security.Permissions.HostProtectionAttribute> da SQL Server per limitare l'esecuzione del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="2eb26-114">Describes how the <xref:System.Security.Permissions.HostProtectionAttribute> attribute is used by SQL Server to restrict the execution of managed code.</span></span>  
  
 [<span data-ttu-id="2eb26-115">Procedure consigliate per l'ottimizzazione dell'affidabilità</span><span class="sxs-lookup"><span data-stu-id="2eb26-115">Reliability Best Practices</span></span>](reliability-best-practices.md)  
 <span data-ttu-id="2eb26-116">Fornisce linee guida per la scrittura di codice che soddisfa i requisiti di affidabilità.</span><span class="sxs-lookup"><span data-stu-id="2eb26-116">Provides guidelines for writing code that meets reliability requirements.</span></span>  
  
 [<span data-ttu-id="2eb26-117">aree di esecuzione vincolate</span><span class="sxs-lookup"><span data-stu-id="2eb26-117">Constrained Execution Regions</span></span>](constrained-execution-regions.md)  
 <span data-ttu-id="2eb26-118">Descrive la funzione e il comportamento delle aree a esecuzione vincolata.</span><span class="sxs-lookup"><span data-stu-id="2eb26-118">Describes the function and behavior of constrained execution regions (CERs).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2eb26-119">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="2eb26-119">Reference</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>
