---
title: '&lt;add&gt; di &lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 2cc7cce62082317bb86218d68bd2881b74649771
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670186"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="04c66-102">&lt;add&gt; di &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="04c66-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="04c66-103">Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="04c66-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="04c66-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="04c66-104">\<system.serviceModel></span></span>  
<span data-ttu-id="04c66-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="04c66-105">\<routing></span></span>  
<span data-ttu-id="04c66-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="04c66-106">\<backupLists></span></span>  
<span data-ttu-id="04c66-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="04c66-107">\<backupList></span></span>  
<span data-ttu-id="04c66-108">\<add></span><span class="sxs-lookup"><span data-stu-id="04c66-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c66-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04c66-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04c66-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="04c66-110">Attributes and Elements</span></span>  
 <span data-ttu-id="04c66-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="04c66-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04c66-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="04c66-112">Attributes</span></span>  
  
|<span data-ttu-id="04c66-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="04c66-113">Attribute</span></span>|<span data-ttu-id="04c66-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04c66-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04c66-115">name</span><span class="sxs-lookup"><span data-stu-id="04c66-115">name</span></span>|<span data-ttu-id="04c66-116">Stringa che specifica il nome dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="04c66-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04c66-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="04c66-117">Child Elements</span></span>  
 <span data-ttu-id="04c66-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="04c66-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04c66-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="04c66-119">Parent Elements</span></span>  
  
|<span data-ttu-id="04c66-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="04c66-120">Element</span></span>|<span data-ttu-id="04c66-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04c66-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04c66-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="04c66-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="04c66-123">Contiene un elenco di endpoint che si desidera il servizio di Routing da usare nel caso in cui non è possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="04c66-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04c66-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04c66-124">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
