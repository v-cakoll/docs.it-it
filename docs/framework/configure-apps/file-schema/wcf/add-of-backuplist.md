---
title: <add> di <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: c590dbd671807b32e08ad5d871d376a0dc51e611
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926880"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="ca2bf-102">\<Aggiungi > di \<> di backup</span><span class="sxs-lookup"><span data-stu-id="ca2bf-102">\<add> of \<backupList></span></span>
<span data-ttu-id="ca2bf-103">Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="ca2bf-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="ca2bf-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ca2bf-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ca2bf-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="ca2bf-105">\<routing></span></span>  
<span data-ttu-id="ca2bf-106">\<> backupLists</span><span class="sxs-lookup"><span data-stu-id="ca2bf-106">\<backupLists></span></span>  
<span data-ttu-id="ca2bf-107">\<> di backup</span><span class="sxs-lookup"><span data-stu-id="ca2bf-107">\<backupList></span></span>  
<span data-ttu-id="ca2bf-108">\<add></span><span class="sxs-lookup"><span data-stu-id="ca2bf-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca2bf-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca2bf-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca2bf-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ca2bf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ca2bf-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ca2bf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca2bf-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="ca2bf-112">Attributes</span></span>  
  
|<span data-ttu-id="ca2bf-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="ca2bf-113">Attribute</span></span>|<span data-ttu-id="ca2bf-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca2bf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca2bf-115">name</span><span class="sxs-lookup"><span data-stu-id="ca2bf-115">name</span></span>|<span data-ttu-id="ca2bf-116">Stringa che specifica il nome dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="ca2bf-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca2bf-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ca2bf-117">Child Elements</span></span>  
 <span data-ttu-id="ca2bf-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ca2bf-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca2bf-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ca2bf-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ca2bf-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca2bf-120">Element</span></span>|<span data-ttu-id="ca2bf-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="ca2bf-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca2bf-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="ca2bf-122">\<routing></span></span>](routing.md)|<span data-ttu-id="ca2bf-123">Contiene un elenco di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="ca2bf-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca2bf-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca2bf-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
