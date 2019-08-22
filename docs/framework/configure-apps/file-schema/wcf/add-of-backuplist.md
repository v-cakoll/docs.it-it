---
title: <add> di <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 53af01a519c244376b262db1f6515a438dcc554f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663376"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="abdfb-102">\<Aggiungi > di \<> di backup</span><span class="sxs-lookup"><span data-stu-id="abdfb-102">\<add> of \<backupList></span></span>
<span data-ttu-id="abdfb-103">Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="abdfb-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="abdfb-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="abdfb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="abdfb-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="abdfb-105">\<routing></span></span>  
<span data-ttu-id="abdfb-106">\<> backupLists</span><span class="sxs-lookup"><span data-stu-id="abdfb-106">\<backupLists></span></span>  
<span data-ttu-id="abdfb-107">\<> di backup</span><span class="sxs-lookup"><span data-stu-id="abdfb-107">\<backupList></span></span>  
<span data-ttu-id="abdfb-108">\<add></span><span class="sxs-lookup"><span data-stu-id="abdfb-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abdfb-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="abdfb-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abdfb-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="abdfb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="abdfb-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="abdfb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abdfb-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="abdfb-112">Attributes</span></span>  
  
|<span data-ttu-id="abdfb-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="abdfb-113">Attribute</span></span>|<span data-ttu-id="abdfb-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abdfb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="abdfb-115">name</span><span class="sxs-lookup"><span data-stu-id="abdfb-115">name</span></span>|<span data-ttu-id="abdfb-116">Stringa che specifica il nome dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="abdfb-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="abdfb-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="abdfb-117">Child Elements</span></span>  
 <span data-ttu-id="abdfb-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="abdfb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="abdfb-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="abdfb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="abdfb-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="abdfb-120">Element</span></span>|<span data-ttu-id="abdfb-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abdfb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="abdfb-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="abdfb-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="abdfb-123">Contiene un elenco di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="abdfb-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="abdfb-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abdfb-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
