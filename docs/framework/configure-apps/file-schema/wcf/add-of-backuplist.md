---
title: '&lt;add&gt; di &lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 4a8eb3df9be6b6b5bfe43aee330f3174ddca66ab
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151475"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="f726d-102">&lt;add&gt; di &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="f726d-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="f726d-103">Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="f726d-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="f726d-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f726d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f726d-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="f726d-105">\<routing></span></span>  
<span data-ttu-id="f726d-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="f726d-106">\<backupLists></span></span>  
<span data-ttu-id="f726d-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="f726d-107">\<backupList></span></span>  
<span data-ttu-id="f726d-108">\<add></span><span class="sxs-lookup"><span data-stu-id="f726d-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f726d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f726d-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f726d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f726d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f726d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f726d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f726d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f726d-112">Attributes</span></span>  
  
|<span data-ttu-id="f726d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="f726d-113">Attribute</span></span>|<span data-ttu-id="f726d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f726d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f726d-115">name</span><span class="sxs-lookup"><span data-stu-id="f726d-115">name</span></span>|<span data-ttu-id="f726d-116">Stringa che specifica il nome dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="f726d-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f726d-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f726d-117">Child Elements</span></span>  
 <span data-ttu-id="f726d-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f726d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f726d-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f726d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f726d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f726d-120">Element</span></span>|<span data-ttu-id="f726d-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f726d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f726d-122">\<routing ></span><span class="sxs-lookup"><span data-stu-id="f726d-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="f726d-123">Contiene un elenco di endpoint che si desidera il servizio di Routing da usare nel caso in cui non è possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="f726d-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f726d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f726d-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
