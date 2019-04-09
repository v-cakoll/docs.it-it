---
title: <add> di <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 03bf1bbb8156e4722d987e171d9034747ac6bb61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089536"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="96544-102">\<aggiungere > di \<backupList ></span><span class="sxs-lookup"><span data-stu-id="96544-102">\<add> of \<backupList></span></span>
<span data-ttu-id="96544-103">Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="96544-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="96544-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="96544-104">\<system.serviceModel></span></span>  
<span data-ttu-id="96544-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="96544-105">\<routing></span></span>  
<span data-ttu-id="96544-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="96544-106">\<backupLists></span></span>  
<span data-ttu-id="96544-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="96544-107">\<backupList></span></span>  
<span data-ttu-id="96544-108">\<add></span><span class="sxs-lookup"><span data-stu-id="96544-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96544-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96544-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96544-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="96544-110">Attributes and Elements</span></span>  
 <span data-ttu-id="96544-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="96544-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96544-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="96544-112">Attributes</span></span>  
  
|<span data-ttu-id="96544-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="96544-113">Attribute</span></span>|<span data-ttu-id="96544-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96544-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="96544-115">name</span><span class="sxs-lookup"><span data-stu-id="96544-115">name</span></span>|<span data-ttu-id="96544-116">Stringa che specifica il nome dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="96544-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96544-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="96544-117">Child Elements</span></span>  
 <span data-ttu-id="96544-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="96544-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96544-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="96544-119">Parent Elements</span></span>  
  
|<span data-ttu-id="96544-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="96544-120">Element</span></span>|<span data-ttu-id="96544-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96544-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96544-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="96544-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="96544-123">Contiene un elenco di endpoint che si desidera il servizio di Routing da usare nel caso in cui non è possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="96544-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96544-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96544-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
