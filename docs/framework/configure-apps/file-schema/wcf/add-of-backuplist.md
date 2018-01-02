---
title: '&lt;add&gt; di &lt;backupList&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 786620b0daf1cd22a95f9d0c94b7fc3d17c1a2c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="c1d7c-102">&lt;add&gt; di &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="c1d7c-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="c1d7c-103">Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="c1d7c-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="c1d7c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c1d7c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c1d7c-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="c1d7c-105">\<routing></span></span>  
<span data-ttu-id="c1d7c-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="c1d7c-106">\<backupLists></span></span>  
<span data-ttu-id="c1d7c-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="c1d7c-107">\<backupList></span></span>  
<span data-ttu-id="c1d7c-108">\<add></span><span class="sxs-lookup"><span data-stu-id="c1d7c-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1d7c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1d7c-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1d7c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c1d7c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c1d7c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c1d7c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1d7c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c1d7c-112">Attributes</span></span>  
  
|<span data-ttu-id="c1d7c-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c1d7c-113">Attribute</span></span>|<span data-ttu-id="c1d7c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1d7c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1d7c-115">name</span><span class="sxs-lookup"><span data-stu-id="c1d7c-115">name</span></span>|<span data-ttu-id="c1d7c-116">Stringa che specifica il nome dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="c1d7c-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1d7c-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c1d7c-117">Child Elements</span></span>  
 <span data-ttu-id="c1d7c-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c1d7c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1d7c-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c1d7c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c1d7c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1d7c-120">Element</span></span>|<span data-ttu-id="c1d7c-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1d7c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1d7c-122">\<routing ></span><span class="sxs-lookup"><span data-stu-id="c1d7c-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="c1d7c-123">Contiene un elenco di endpoint che si desidera che il servizio di Routing da utilizzare nel caso in cui l'endpoint primario non è raggiungibile.</span><span class="sxs-lookup"><span data-stu-id="c1d7c-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1d7c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1d7c-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
