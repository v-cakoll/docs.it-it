---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: b67f51e634d1294830690dad8c8cffb1fc9a6cd2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399456"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="c5231-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="c5231-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="c5231-103">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c5231-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

<span data-ttu-id="c5231-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c5231-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c5231-105">&nbsp;&nbsp; **\<System. Runtime. Serialization >**</span><span class="sxs-lookup"><span data-stu-id="c5231-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5231-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5231-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5231-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c5231-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c5231-108">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c5231-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5231-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="c5231-109">Attributes</span></span>  
 <span data-ttu-id="c5231-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c5231-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c5231-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c5231-111">Child Elements</span></span>  
  
|<span data-ttu-id="c5231-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c5231-112">Element</span></span>|<span data-ttu-id="c5231-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c5231-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5231-114">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="c5231-114">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="c5231-115">Consente l'aggiunta di tipi noti da usare durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="c5231-115">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c5231-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c5231-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c5231-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c5231-117">Element</span></span>|<span data-ttu-id="c5231-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5231-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5231-119">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="c5231-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="c5231-120">Elemento di livello superiore della configurazione.</span><span class="sxs-lookup"><span data-stu-id="c5231-120">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5231-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5231-121">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="c5231-122">Uso di contratti di dati</span><span class="sxs-lookup"><span data-stu-id="c5231-122">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="c5231-123">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="c5231-123">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
 