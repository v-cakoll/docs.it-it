---
title: '&lt;add&gt; di &lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 7e7361b24c0444b5f3d51a6f5bf079d5eb2dee18
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745552"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="1b280-102">&lt;add&gt; di &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="1b280-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="1b280-103">Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="1b280-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="1b280-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1b280-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1b280-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="1b280-105">\<routing></span></span>  
<span data-ttu-id="1b280-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="1b280-106">\<backupLists></span></span>  
<span data-ttu-id="1b280-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="1b280-107">\<backupList></span></span>  
<span data-ttu-id="1b280-108">\<add></span><span class="sxs-lookup"><span data-stu-id="1b280-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b280-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b280-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b280-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1b280-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1b280-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1b280-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b280-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1b280-112">Attributes</span></span>  
  
|<span data-ttu-id="1b280-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1b280-113">Attribute</span></span>|<span data-ttu-id="1b280-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b280-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b280-115">name</span><span class="sxs-lookup"><span data-stu-id="1b280-115">name</span></span>|<span data-ttu-id="1b280-116">Stringa che specifica il nome dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="1b280-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b280-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1b280-117">Child Elements</span></span>  
 <span data-ttu-id="1b280-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1b280-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b280-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1b280-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1b280-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1b280-120">Element</span></span>|<span data-ttu-id="1b280-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b280-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b280-122">\<routing ></span><span class="sxs-lookup"><span data-stu-id="1b280-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="1b280-123">Contiene un elenco di endpoint che si desidera che il servizio di Routing da utilizzare nel caso in cui l'endpoint primario non è raggiungibile.</span><span class="sxs-lookup"><span data-stu-id="1b280-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b280-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b280-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
