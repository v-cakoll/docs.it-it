---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855078"
---
# <a name="persistabletype"></a><span data-ttu-id="e70f4-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="e70f4-101">\<persistableType></span></span>
<span data-ttu-id="e70f4-102">Specifica tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="e70f4-102">Specifies all the persistable types.</span></span>  
  
<span data-ttu-id="e70f4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e70f4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e70f4-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e70f4-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e70f4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comcontratti >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="e70f4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="e70f4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> comContract**](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="e70f4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="e70f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> persistableTypes**](persistabletypes.md)</span><span class="sxs-lookup"><span data-stu-id="e70f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)</span></span>\
<span data-ttu-id="e70f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> persistableType**</span><span class="sxs-lookup"><span data-stu-id="e70f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e70f4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e70f4-109">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="e70f4-110">Type</span><span class="sxs-lookup"><span data-stu-id="e70f4-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e70f4-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e70f4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e70f4-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e70f4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e70f4-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="e70f4-113">Attributes</span></span>  
  
|<span data-ttu-id="e70f4-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="e70f4-114">Attribute</span></span>|<span data-ttu-id="e70f4-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e70f4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e70f4-116">id</span><span class="sxs-lookup"><span data-stu-id="e70f4-116">id</span></span>|<span data-ttu-id="e70f4-117">Un attributo obbligatorio che contiene una stringa che specifica un identificatore univoco per un tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="e70f4-117">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="e70f4-118">name</span><span class="sxs-lookup"><span data-stu-id="e70f4-118">name</span></span>|<span data-ttu-id="e70f4-119">Attributo facoltativo contenente una stringa che specifica il nome del tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="e70f4-119">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e70f4-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e70f4-120">Child Elements</span></span>  
 <span data-ttu-id="e70f4-121">Nessuna</span><span class="sxs-lookup"><span data-stu-id="e70f4-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e70f4-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e70f4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e70f4-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e70f4-123">Element</span></span>|<span data-ttu-id="e70f4-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e70f4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e70f4-125">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="e70f4-125">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="e70f4-126">Raccolta di elementi `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="e70f4-126">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e70f4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e70f4-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="e70f4-128">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e70f4-128">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="e70f4-129">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="e70f4-129">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="e70f4-130">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="e70f4-130">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
