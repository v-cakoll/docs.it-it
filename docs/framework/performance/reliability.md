---
title: Affidabilità
ms.date: 03/30/2017
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
ms.openlocfilehash: 2d6601c4cbad32f768ff16301307083f35d986a0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715959"
---
# <a name="reliability"></a><span data-ttu-id="04566-102">Affidabilità</span><span class="sxs-lookup"><span data-stu-id="04566-102">Reliability</span></span>
<span data-ttu-id="04566-103">È importante che il codice in esecuzione in ambienti server, ad esempio SQL Server, fornisca protezione contro le eccezioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="04566-103">It is important that code executing in server environments such as SQL Server protect against asynchronous exceptions.</span></span> <span data-ttu-id="04566-104">L'affidabilità, come descritto in questo argomento, non è specifica di SQL Server, ma della scrittura di codice affidabile per qualsiasi host in esecuzione in un ambiente .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="04566-104">Reliability, as discussed here, is not specific to SQL Server but to writing reliable code for any host executing in a .NET Framework version 2.0 environment.</span></span> <span data-ttu-id="04566-105">SQL Server è tuttavia il primo servizio che fa un uso completo delle nuove funzionalità di affidabilità della versione 2.0, quindi viene usato come esempio.</span><span class="sxs-lookup"><span data-stu-id="04566-105">However, SQL Server is the first service making extensive use of the new reliability features of version 2.0, so it is used as an example.</span></span>  
  
 <span data-ttu-id="04566-106">Il codice in esecuzione in SQL Server deve rispettare linee guida per l'affidabilità più rigorose rispetto ad altri ambienti server.</span><span class="sxs-lookup"><span data-stu-id="04566-106">Code running in SQL Server must deal with more stringent reliability guidelines than other server environments.</span></span> <span data-ttu-id="04566-107">Ciò è dovuto al funzionamento stabile di SQL Server fino al limite estremo di utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="04566-107">This is due to SQL Server’s steady operation at the edge of resource consumption.</span></span>  <span data-ttu-id="04566-108">Le eccezioni <xref:System.OutOfMemoryException> e <xref:System.Threading.ThreadAbortException> non sono rare nell'ambiente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04566-108"><xref:System.OutOfMemoryException> and <xref:System.Threading.ThreadAbortException> exceptions are not uncommon in the SQL Server environment.</span></span> <span data-ttu-id="04566-109">Queste linee guida in generale sono incentrate meno sull'affidabilità e più su come consentire al codice gestito completamente attendibile di generare un errore non grave in caso di riciclo a livello di <xref:System.AppDomain>, che rappresenta il modo principale in cui il server mantiene la coerenza e la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="04566-109">These guidelines in general are focused less on reliability and more on allowing fully trusted managed code to fail gracefully in the face of <xref:System.AppDomain>-level recycling, which is the primary way the server maintains consistency and availability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04566-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="04566-110">In This Section</span></span>  
 [<span data-ttu-id="04566-111">Programmazione per SQL Server e attributi di protezione host</span><span class="sxs-lookup"><span data-stu-id="04566-111">SQL Server Programming and Host Protection Attributes</span></span>](sql-server-programming-and-host-protection-attributes.md)  
 <span data-ttu-id="04566-112">Descrive come viene usato l'attributo <xref:System.Security.Permissions.HostProtectionAttribute> da SQL Server per limitare l'esecuzione del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="04566-112">Describes how the <xref:System.Security.Permissions.HostProtectionAttribute> attribute is used by SQL Server to restrict the execution of managed code.</span></span>  
  
 [<span data-ttu-id="04566-113">Procedure consigliate per l'ottimizzazione dell'affidabilità</span><span class="sxs-lookup"><span data-stu-id="04566-113">Reliability Best Practices</span></span>](reliability-best-practices.md)  
 <span data-ttu-id="04566-114">Fornisce linee guida per la scrittura di codice che soddisfa i requisiti di affidabilità.</span><span class="sxs-lookup"><span data-stu-id="04566-114">Provides guidelines for writing code that meets reliability requirements.</span></span>  
  
 [<span data-ttu-id="04566-115">Aree a esecuzione vincolata</span><span class="sxs-lookup"><span data-stu-id="04566-115">Constrained Execution Regions</span></span>](constrained-execution-regions.md)  
 <span data-ttu-id="04566-116">Descrive la funzione e il comportamento delle aree a esecuzione vincolata.</span><span class="sxs-lookup"><span data-stu-id="04566-116">Describes the function and behavior of constrained execution regions (CERs).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="04566-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="04566-117">Reference</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>
