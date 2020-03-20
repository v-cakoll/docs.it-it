---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152970"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="55885-102">\<> system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="55885-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="55885-103">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="55885-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

<span data-ttu-id="55885-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="55885-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="55885-105">&nbsp;&nbsp;**\<>system.runtime.serialization**</span><span class="sxs-lookup"><span data-stu-id="55885-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55885-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55885-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55885-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="55885-107">Attributes and Elements</span></span>  
 <span data-ttu-id="55885-108">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="55885-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55885-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="55885-109">Attributes</span></span>  
 <span data-ttu-id="55885-110">No.</span><span class="sxs-lookup"><span data-stu-id="55885-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="55885-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="55885-111">Child Elements</span></span>  
  
|<span data-ttu-id="55885-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="55885-112">Element</span></span>|<span data-ttu-id="55885-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55885-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55885-114">\<>DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="55885-114">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="55885-115">Consente l'aggiunta di tipi noti da usare durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="55885-115">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="55885-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="55885-116">Parent Elements</span></span>  
  
|<span data-ttu-id="55885-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="55885-117">Element</span></span>|<span data-ttu-id="55885-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55885-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55885-119">\<Elemento> configurazione</span><span class="sxs-lookup"><span data-stu-id="55885-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="55885-120">Elemento di livello superiore della configurazione.</span><span class="sxs-lookup"><span data-stu-id="55885-120">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55885-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55885-121">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="55885-122">Using Data Contracts</span><span class="sxs-lookup"><span data-stu-id="55885-122">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="55885-123">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="55885-123">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
