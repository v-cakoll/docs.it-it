---
title: "&lt;add&gt; dell'elemento &lt;declaredTypes&gt;"
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 90eaf11ce8b9e3675a23ed3875680b03f149b56b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754119"
---
# <a name="ltaddgt-of-ltdeclaredtypesgt-element"></a><span data-ttu-id="5e6da-102">&lt;add&gt; dell'elemento &lt;declaredTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="5e6da-102">&lt;add&gt; of &lt;declaredTypes&gt; Element</span></span>
<span data-ttu-id="5e6da-103">Aggiunge un tipo usato dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="5e6da-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="5e6da-104">Ogni tipo dichiarato contiene i tipi noti che verranno restituiti come campo o come proprietà del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="5e6da-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="5e6da-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="5e6da-105">system.runtime.serialization</span></span>  
<span data-ttu-id="5e6da-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="5e6da-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="5e6da-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="5e6da-107">\<declaredTypes></span></span>  
<span data-ttu-id="5e6da-108">\<aggiungere > di \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="5e6da-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e6da-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e6da-109">Syntax</span></span>  
  
```xml  
<add type="String">  
   <knownType type="String">  
       <parameter index="Integer"  
                  type="String" />  
   </knownType>  
</add>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e6da-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5e6da-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5e6da-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5e6da-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e6da-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="5e6da-112">Attributes</span></span>  
  
|<span data-ttu-id="5e6da-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="5e6da-113">Attribute</span></span>|<span data-ttu-id="5e6da-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e6da-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e6da-115">tipo</span><span class="sxs-lookup"><span data-stu-id="5e6da-115">type</span></span>|<span data-ttu-id="5e6da-116">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e6da-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="5e6da-117">Specifica il nome del tipo (compreso lo spazio dei nomi), il nome dell'assembly, il numero di versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="5e6da-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e6da-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5e6da-118">Child Elements</span></span>  
  
|<span data-ttu-id="5e6da-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e6da-119">Element</span></span>|<span data-ttu-id="5e6da-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e6da-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e6da-121">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="5e6da-121">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="5e6da-122">Specifica il tipo conosciuto del tipo dichiarato da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="5e6da-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="5e6da-123">Se il tipo dichiarato è un tipo generico occorre aggiungere anche un elemento di parametro all'elemento `<knownType>` per specificare quale parametro generico viene usato per restituire il tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="5e6da-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5e6da-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5e6da-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5e6da-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e6da-125">Element</span></span>|<span data-ttu-id="5e6da-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e6da-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e6da-127">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="5e6da-127">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="5e6da-128">Contiene i tipi che richiedono tipi noti durante la deserializzazione eseguita dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5e6da-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e6da-129">Note</span><span class="sxs-lookup"><span data-stu-id="5e6da-129">Remarks</span></span>  
 <span data-ttu-id="5e6da-130">Per ulteriori informazioni sui tipi noti, vedere [tipi conosciuti di contratto dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5e6da-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="5e6da-131">Vedere il [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="5e6da-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e6da-132">Se si aggiunge il tipo <xref:System.Object> come tipo `<declaredType>`, viene generata un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="5e6da-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="5e6da-133">Ciò è dovuto al fatto che il tipo <xref:System.Object> non può essere usato come tipo dichiarato in configurazione.</span><span class="sxs-lookup"><span data-stu-id="5e6da-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e6da-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e6da-134">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5e6da-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e6da-135">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="5e6da-136">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="5e6da-136">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="5e6da-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="5e6da-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="5e6da-138">\<aggiungere > di \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="5e6da-138">\<add> of \<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
