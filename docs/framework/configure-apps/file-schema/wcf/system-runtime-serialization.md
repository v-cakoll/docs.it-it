---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152970"
---
# \<system.runtime.serialization>
<span data-ttu-id="397b1-102">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="397b1-102">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.serialization>**  
  
## <a name="syntax"></a><span data-ttu-id="397b1-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="397b1-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="397b1-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="397b1-104">Attributes and Elements</span></span>  
 <span data-ttu-id="397b1-105">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="397b1-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="397b1-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="397b1-106">Attributes</span></span>  
 <span data-ttu-id="397b1-107">No.</span><span class="sxs-lookup"><span data-stu-id="397b1-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="397b1-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="397b1-108">Child Elements</span></span>  
  
|<span data-ttu-id="397b1-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="397b1-109">Element</span></span>|<span data-ttu-id="397b1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="397b1-110">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="397b1-111">Consente l'aggiunta di tipi noti da usare durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="397b1-111">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="397b1-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="397b1-112">Parent Elements</span></span>  
  
|<span data-ttu-id="397b1-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="397b1-113">Element</span></span>|<span data-ttu-id="397b1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="397b1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="397b1-115">\<configuration>Elemento</span><span class="sxs-lookup"><span data-stu-id="397b1-115">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="397b1-116">Elemento di livello superiore della configurazione.</span><span class="sxs-lookup"><span data-stu-id="397b1-116">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="397b1-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="397b1-117">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="397b1-118">Using Data Contracts</span><span class="sxs-lookup"><span data-stu-id="397b1-118">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="397b1-119">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="397b1-119">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
