---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c34eba2614a354f1753d8da077f8653f2c260a97
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165893"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="edfe0-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="edfe0-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="edfe0-103">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="edfe0-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="edfe0-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="edfe0-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edfe0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edfe0-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edfe0-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="edfe0-106">Attributes and Elements</span></span>  
 <span data-ttu-id="edfe0-107">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="edfe0-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edfe0-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="edfe0-108">Attributes</span></span>  
 <span data-ttu-id="edfe0-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="edfe0-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="edfe0-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="edfe0-110">Child Elements</span></span>  
  
|<span data-ttu-id="edfe0-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="edfe0-111">Element</span></span>|<span data-ttu-id="edfe0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edfe0-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edfe0-113">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="edfe0-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="edfe0-114">Consente l'aggiunta di tipi noti da usare durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="edfe0-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="edfe0-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="edfe0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="edfe0-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="edfe0-116">Element</span></span>|<span data-ttu-id="edfe0-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edfe0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edfe0-118">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="edfe0-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="edfe0-119">Elemento di livello superiore della configurazione.</span><span class="sxs-lookup"><span data-stu-id="edfe0-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="edfe0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edfe0-120">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="edfe0-121">Uso di contratti di dati</span><span class="sxs-lookup"><span data-stu-id="edfe0-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="edfe0-122">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="edfe0-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
