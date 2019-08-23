---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: fcfd338e289b5151688724f0e84b6878707d32be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933829"
---
# <a name="persistabletype"></a><span data-ttu-id="aaaa7-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="aaaa7-101">\<persistableType></span></span>
<span data-ttu-id="aaaa7-102">Specifica tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="aaaa7-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="aaaa7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="aaaa7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="aaaa7-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="aaaa7-104">\<comContracts></span></span>  
<span data-ttu-id="aaaa7-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="aaaa7-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaaa7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aaaa7-106">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="aaaa7-107">Type</span><span class="sxs-lookup"><span data-stu-id="aaaa7-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aaaa7-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="aaaa7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="aaaa7-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="aaaa7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aaaa7-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="aaaa7-110">Attributes</span></span>  
  
|<span data-ttu-id="aaaa7-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="aaaa7-111">Attribute</span></span>|<span data-ttu-id="aaaa7-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="aaaa7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aaaa7-113">id</span><span class="sxs-lookup"><span data-stu-id="aaaa7-113">id</span></span>|<span data-ttu-id="aaaa7-114">Un attributo obbligatorio che contiene una stringa che specifica un identificatore univoco per un tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="aaaa7-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="aaaa7-115">name</span><span class="sxs-lookup"><span data-stu-id="aaaa7-115">name</span></span>|<span data-ttu-id="aaaa7-116">Attributo facoltativo contenente una stringa che specifica il nome del tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="aaaa7-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aaaa7-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="aaaa7-117">Child Elements</span></span>  
 <span data-ttu-id="aaaa7-118">Nessuna</span><span class="sxs-lookup"><span data-stu-id="aaaa7-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aaaa7-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="aaaa7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="aaaa7-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="aaaa7-120">Element</span></span>|<span data-ttu-id="aaaa7-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aaaa7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaaa7-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="aaaa7-122">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="aaaa7-123">Raccolta di elementi `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="aaaa7-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aaaa7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaaa7-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="aaaa7-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="aaaa7-125">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="aaaa7-126">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="aaaa7-126">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="aaaa7-127">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="aaaa7-127">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
