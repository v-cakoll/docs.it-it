---
title: '&lt;Serialization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5a47417ded6e0917fadf2134eed5997d9d3b3d74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemruntimeserializationgt"></a><span data-ttu-id="f02e4-102">&lt;Serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="f02e4-102">&lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="f02e4-103">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f02e4-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="f02e4-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="f02e4-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f02e4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f02e4-105">Syntax</span></span>  
  
```xml  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer">  
      <declaredTypes>  
        <add type="String ">  
          <knownType type="String">  
             <parameter index="Integer"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f02e4-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f02e4-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f02e4-107">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f02e4-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f02e4-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="f02e4-108">Attributes</span></span>  
 <span data-ttu-id="f02e4-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f02e4-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f02e4-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f02e4-110">Child Elements</span></span>  
  
|<span data-ttu-id="f02e4-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="f02e4-111">Element</span></span>|<span data-ttu-id="f02e4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f02e4-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f02e4-113">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="f02e4-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="f02e4-114">Consente l'aggiunta di tipi noti da usare durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="f02e4-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f02e4-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f02e4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f02e4-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f02e4-116">Element</span></span>|<span data-ttu-id="f02e4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f02e4-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f02e4-118">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="f02e4-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="f02e4-119">Elemento di livello superiore della configurazione.</span><span class="sxs-lookup"><span data-stu-id="f02e4-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f02e4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f02e4-120">See Also</span></span>  
 <xref:System.Runtime.Serialization>  
 [<span data-ttu-id="f02e4-121">Uso di contratti dati</span><span class="sxs-lookup"><span data-stu-id="f02e4-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="f02e4-122">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="f02e4-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
