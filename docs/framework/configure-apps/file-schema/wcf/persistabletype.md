---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855078"
---
# \<persistableType>
<span data-ttu-id="7e756-101">Specifica tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="7e756-101">Specifies all the persistable types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**  
  
## <a name="syntax"></a><span data-ttu-id="7e756-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e756-102">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="7e756-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="7e756-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e756-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7e756-104">Attributes and Elements</span></span>  
 <span data-ttu-id="7e756-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7e756-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e756-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="7e756-106">Attributes</span></span>  
  
|<span data-ttu-id="7e756-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="7e756-107">Attribute</span></span>|<span data-ttu-id="7e756-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e756-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e756-109">id</span><span class="sxs-lookup"><span data-stu-id="7e756-109">id</span></span>|<span data-ttu-id="7e756-110">Un attributo obbligatorio che contiene una stringa che specifica un identificatore univoco per un tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="7e756-110">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="7e756-111">name</span><span class="sxs-lookup"><span data-stu-id="7e756-111">name</span></span>|<span data-ttu-id="7e756-112">Attributo facoltativo contenente una stringa che specifica il nome del tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="7e756-112">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e756-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7e756-113">Child Elements</span></span>  
 <span data-ttu-id="7e756-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="7e756-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e756-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7e756-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7e756-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e756-116">Element</span></span>|<span data-ttu-id="7e756-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e756-117">Description</span></span>|  
|-------------|-----------------|  
|[\<persistableTypes>](persistabletypes.md)|<span data-ttu-id="7e756-118">Raccolta di elementi `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="7e756-118">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e756-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7e756-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="7e756-120">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="7e756-120">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="7e756-121">Procedura: configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="7e756-121">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
