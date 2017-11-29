---
title: Elementi direttiva di runtime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3143c6b78749f3339e7e7195b551b5a5c31fad12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="09cab-102">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="09cab-102">Runtime Directive Elements</span></span>
<span data-ttu-id="09cab-103">Il formato del file delle direttive di runtime (rd.xml) supporta i seguenti elementi direttiva di runtime.</span><span class="sxs-lookup"><span data-stu-id="09cab-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="09cab-104">Per una rappresentazione gerarchica, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="09cab-104">See [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="09cab-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="09cab-105">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)  
 <span data-ttu-id="09cab-106">Applica criteri di reflection di runtime a tutti i tipi usati dall'app e funge da contenitore per i tipi a livello di applicazione e i membri del tipo i cui metadati sono disponibili per la reflection in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="09cab-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="09cab-107">Questo è un elemento figlio dell'elemento [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="09cab-107">This is a child of the [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="09cab-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="09cab-108">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)  
 <span data-ttu-id="09cab-109">Applica criteri di runtime a tutti i tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="09cab-109">Applies runnntime policy to all the types in an assembly.</span></span> <span data-ttu-id="09cab-110">Questo è un elemento figlio degli elementi [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) e [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="09cab-110">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09cab-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="09cab-111">\<AttributeImplies></span></span>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)  
 <span data-ttu-id="09cab-112">Se la direttiva [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) contenitore è un attributo, applica i criteri di runtime agli elementi di codice a cui è applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="09cab-112">If its containing [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="09cab-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="09cab-113">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)  
 <span data-ttu-id="09cab-114">Elemento radice in ogni file di direttive di runtime per [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09cab-114">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="09cab-115">I relativi elementi figlio sono [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) e [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="09cab-115">Its child elements are [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="09cab-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="09cab-116">\<Event></span></span>](../../../docs/framework/net-native/event-element-net-native.md)  
 <span data-ttu-id="09cab-117">Applica criteri di runtime a un evento.</span><span class="sxs-lookup"><span data-stu-id="09cab-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="09cab-118">Questo è un elemento figlio degli elementi [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) e [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="09cab-118">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09cab-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="09cab-119">\<Field></span></span>](../../../docs/framework/net-native/field-element-net-native.md)  
 <span data-ttu-id="09cab-120">Applica criteri di runtime a un campo.</span><span class="sxs-lookup"><span data-stu-id="09cab-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="09cab-121">Questo è un elemento figlio degli elementi [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) e [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="09cab-121">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09cab-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="09cab-122">\<GenericParameter></span></span>](../../../docs/framework/net-native/genericparameter-element-net-native.md)  
 <span data-ttu-id="09cab-123">Applica i criteri di runtime al tipo di parametro di un tipo o di un metodo generico.</span><span class="sxs-lookup"><span data-stu-id="09cab-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="09cab-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="09cab-124">\<ImpliesType></span></span>](../../../docs/framework/net-native/impliestype-element-net-native.md)  
 <span data-ttu-id="09cab-125">Applica criteri di runtime a un tipo, se tale criterio è stato applicato al metodo o al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="09cab-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="09cab-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="09cab-126">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)  
 <span data-ttu-id="09cab-127">Applica criteri di runtime a tutti i tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="09cab-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="09cab-128">Questo è un elemento figlio degli elementi [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) e [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="09cab-128">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09cab-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="09cab-129">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 <span data-ttu-id="09cab-130">Applica criteri di runtime a un metodo.</span><span class="sxs-lookup"><span data-stu-id="09cab-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="09cab-131">Questo è un elemento figlio degli elementi [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) e [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="09cab-131">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09cab-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="09cab-132">\<MethodInstantiation></span></span>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)  
 <span data-ttu-id="09cab-133">Applica criteri di runtime a un metodo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="09cab-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="09cab-134">Questo è un elemento figlio degli elementi [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) e [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="09cab-134">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09cab-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="09cab-135">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)  
 <span data-ttu-id="09cab-136">Applica criteri di runtime a tutti i tipi in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="09cab-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="09cab-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="09cab-137">\<Parameter></span></span>](../../../docs/framework/net-native/parameter-element-net-native.md)  
 <span data-ttu-id="09cab-138">Applica criteri di runtime al tipo di argomento passato a un metodo.</span><span class="sxs-lookup"><span data-stu-id="09cab-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="09cab-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="09cab-139">\<Property></span></span>](../../../docs/framework/net-native/property-element-net-native.md)  
 <span data-ttu-id="09cab-140">Applica criteri di runtime a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="09cab-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="09cab-141">Questo è un elemento figlio degli elementi [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) e [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="09cab-141">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09cab-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="09cab-142">\<Subtypes></span></span>](../../../docs/framework/net-native/subtypes-element-net-native.md)  
 <span data-ttu-id="09cab-143">Applica i criteri di runtime a tutte le classi ereditate per il tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="09cab-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="09cab-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="09cab-144">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 <span data-ttu-id="09cab-145">Applica criteri di runtime a un tipo.</span><span class="sxs-lookup"><span data-stu-id="09cab-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="09cab-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="09cab-146">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)  
 <span data-ttu-id="09cab-147">Applica criteri di runtime a un tipo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="09cab-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="09cab-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="09cab-148">\<TypeParameter></span></span>](../../../docs/framework/net-native/typeparameter-element-net-native.md)  
 <span data-ttu-id="09cab-149">Applica criteri di runtime al tipo rappresentato da un argomento <xref:System.Type> passato a un metodo.</span><span class="sxs-lookup"><span data-stu-id="09cab-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09cab-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09cab-150">See Also</span></span>  
 [<span data-ttu-id="09cab-151">Informazioni di riferimento sul file di configurazione rd.xml</span><span class="sxs-lookup"><span data-stu-id="09cab-151">rd.xml Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
