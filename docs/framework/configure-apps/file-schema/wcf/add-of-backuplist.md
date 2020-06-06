---
title: <add> di <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850547"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="02076-102">\<add> di \<backupList></span><span class="sxs-lookup"><span data-stu-id="02076-102">\<add> of \<backupList></span></span>
<span data-ttu-id="02076-103">Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="02076-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="02076-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02076-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02076-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="02076-105">Attributes and Elements</span></span>  
 <span data-ttu-id="02076-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="02076-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02076-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="02076-107">Attributes</span></span>  
  
|<span data-ttu-id="02076-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="02076-108">Attribute</span></span>|<span data-ttu-id="02076-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02076-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02076-110">name</span><span class="sxs-lookup"><span data-stu-id="02076-110">name</span></span>|<span data-ttu-id="02076-111">Stringa che specifica il nome dell'endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="02076-111">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02076-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="02076-112">Child Elements</span></span>  
 <span data-ttu-id="02076-113">No.</span><span class="sxs-lookup"><span data-stu-id="02076-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02076-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="02076-114">Parent Elements</span></span>  
  
|<span data-ttu-id="02076-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="02076-115">Element</span></span>|<span data-ttu-id="02076-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02076-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="02076-117">Contiene un elenco di endpoint che dovranno essere usati nel servizio di routing quando non è possibile raggiungere l'endpoint primario. </span><span class="sxs-lookup"><span data-stu-id="02076-117">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02076-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02076-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
