---
title: '&lt;add&gt; dell''elemento &lt;declaredTypes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71f9c2b45f631eb2d9021254d2866f0092ebb079
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltdeclaredtypesgt-element"></a><span data-ttu-id="c45f2-102">&lt;add&gt; dell'elemento &lt;declaredTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="c45f2-102">&lt;add&gt; of &lt;declaredTypes&gt; Element</span></span>
<span data-ttu-id="c45f2-103">Aggiunge un tipo usato dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="c45f2-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="c45f2-104">Ogni tipo dichiarato contiene i tipi noti che verranno restituiti come campo o come proprietà del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="c45f2-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="c45f2-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="c45f2-105">system.runtime.serialization</span></span>  
<span data-ttu-id="c45f2-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c45f2-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="c45f2-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="c45f2-107">\<declaredTypes></span></span>  
<span data-ttu-id="c45f2-108">\<aggiungere > di \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="c45f2-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c45f2-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c45f2-109">Syntax</span></span>  
  
```xml  
<add type="String">  
   <knownType type="String">  
       <parameter index="Integer"  
                  type="String" />  
   </knownType>  
</add>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c45f2-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c45f2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c45f2-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c45f2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c45f2-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c45f2-112">Attributes</span></span>  
  
|<span data-ttu-id="c45f2-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c45f2-113">Attribute</span></span>|<span data-ttu-id="c45f2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c45f2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c45f2-115">tipo</span><span class="sxs-lookup"><span data-stu-id="c45f2-115">type</span></span>|<span data-ttu-id="c45f2-116">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c45f2-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="c45f2-117">Specifica il nome del tipo (compreso lo spazio dei nomi), il nome dell'assembly, il numero di versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="c45f2-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c45f2-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c45f2-118">Child Elements</span></span>  
  
|<span data-ttu-id="c45f2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c45f2-119">Element</span></span>|<span data-ttu-id="c45f2-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c45f2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c45f2-121">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="c45f2-121">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="c45f2-122">Specifica il tipo conosciuto del tipo dichiarato da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c45f2-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="c45f2-123">Se il tipo dichiarato è un tipo generico occorre aggiungere anche un elemento di parametro all'elemento `<knownType>` per specificare quale parametro generico viene usato per restituire il tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="c45f2-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c45f2-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c45f2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c45f2-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="c45f2-125">Element</span></span>|<span data-ttu-id="c45f2-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c45f2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c45f2-127">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="c45f2-127">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="c45f2-128">Contiene i tipi che richiedono tipi noti durante la deserializzazione eseguita dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c45f2-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c45f2-129">Note</span><span class="sxs-lookup"><span data-stu-id="c45f2-129">Remarks</span></span>  
 <span data-ttu-id="c45f2-130">Per ulteriori informazioni sui tipi noti, vedere [tipi conosciuti di contratto dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c45f2-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="c45f2-131">Vedere il [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="c45f2-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c45f2-132">Se si aggiunge il tipo <xref:System.Object> come tipo `<declaredType>`, viene generata un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="c45f2-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="c45f2-133">Ciò è dovuto al fatto che il tipo <xref:System.Object> non può essere usato come tipo dichiarato in configurazione.</span><span class="sxs-lookup"><span data-stu-id="c45f2-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c45f2-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="c45f2-134">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,   
           MyAssembly, Version=2.0.0.0, Culture=neutral,  
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">  
           <knownType type="MyCompany.Library.Circle,   
                      MyAssembly, Version=2.0.0.0, Culture=neutral,  
                      PublicKeyToken=XXXXXX,  
                      processorArchitecture=MSIL"/>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c45f2-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c45f2-135">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="c45f2-136">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="c45f2-136">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="c45f2-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c45f2-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="c45f2-138">\<aggiungere > di \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="c45f2-138">\<add> of \<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
