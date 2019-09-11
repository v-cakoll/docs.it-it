---
title: <add> di <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850547"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="5d890-102">\<Aggiungi > di \<> di backup</span><span class="sxs-lookup"><span data-stu-id="5d890-102">\<add> of \<backupList></span></span>
<span data-ttu-id="5d890-103">Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="5d890-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
<span data-ttu-id="5d890-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d890-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d890-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5d890-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5d890-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di routing**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="5d890-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="5d890-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> backupLists**](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="5d890-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="5d890-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di backup**](backuplist.md)</span><span class="sxs-lookup"><span data-stu-id="5d890-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)</span></span>\
<span data-ttu-id="5d890-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="5d890-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d890-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d890-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d890-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5d890-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5d890-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5d890-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d890-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="5d890-113">Attributes</span></span>  
  
|<span data-ttu-id="5d890-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="5d890-114">Attribute</span></span>|<span data-ttu-id="5d890-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d890-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d890-116">name</span><span class="sxs-lookup"><span data-stu-id="5d890-116">name</span></span>|<span data-ttu-id="5d890-117">Stringa che specifica il nome dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="5d890-117">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d890-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5d890-118">Child Elements</span></span>  
 <span data-ttu-id="5d890-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5d890-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d890-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5d890-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5d890-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d890-121">Element</span></span>|<span data-ttu-id="5d890-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="5d890-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d890-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="5d890-123">\<routing></span></span>](routing.md)|<span data-ttu-id="5d890-124">Contiene un elenco di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="5d890-124">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d890-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d890-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
