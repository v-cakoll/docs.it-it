---
title: Elementi direttiva di runtime
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128175"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="a7f31-102">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="a7f31-102">Runtime Directive Elements</span></span>
<span data-ttu-id="a7f31-103">Il formato del file delle direttive di runtime (rd.xml) supporta i seguenti elementi direttiva di runtime.</span><span class="sxs-lookup"><span data-stu-id="a7f31-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="a7f31-104">Per una rappresentazione gerarchica, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a7f31-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="a7f31-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="a7f31-105">\<Application></span></span>](application-element-net-native.md)  
 <span data-ttu-id="a7f31-106">Applica criteri di reflection di runtime a tutti i tipi usati dall'app e funge da contenitore per i tipi a livello di applicazione e i membri del tipo i cui metadati sono disponibili per la reflection in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a7f31-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="a7f31-107">Questo è un elemento figlio dell'elemento [\<Directives>](directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a7f31-107">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="a7f31-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="a7f31-108">\<Assembly></span></span>](assembly-element-net-native.md)  
 <span data-ttu-id="a7f31-109">Applica criteri di runtime a tutti i tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="a7f31-109">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="a7f31-110">Questo è un elemento figlio degli elementi [\<Application>](application-element-net-native.md) e [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a7f31-110">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a7f31-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="a7f31-111">\<AttributeImplies></span></span>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="a7f31-112">Se la direttiva [\<Type>](type-element-net-native.md) contenitore è un attributo, applica i criteri di runtime agli elementi di codice a cui è applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="a7f31-112">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="a7f31-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="a7f31-113">\<Directives></span></span>](directives-element-net-native.md)  
 <span data-ttu-id="a7f31-114">Elemento radice in ogni file di direttive di runtime per .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a7f31-114">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="a7f31-115">I relativi elementi figlio sono [\<Application>](application-element-net-native.md) e [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a7f31-115">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="a7f31-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="a7f31-116">\<Event></span></span>](event-element-net-native.md)  
 <span data-ttu-id="a7f31-117">Applica criteri di runtime a un evento.</span><span class="sxs-lookup"><span data-stu-id="a7f31-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="a7f31-118">Questo è un elemento figlio degli elementi [\<Type>](type-element-net-native.md) e [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a7f31-118">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a7f31-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="a7f31-119">\<Field></span></span>](field-element-net-native.md)  
 <span data-ttu-id="a7f31-120">Applica criteri di runtime a un campo.</span><span class="sxs-lookup"><span data-stu-id="a7f31-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="a7f31-121">Questo è un elemento figlio degli elementi [\<Type>](type-element-net-native.md) e [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a7f31-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a7f31-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="a7f31-122">\<GenericParameter></span></span>](genericparameter-element-net-native.md)  
 <span data-ttu-id="a7f31-123">Applica i criteri di runtime al tipo di parametro di un tipo o di un metodo generico.</span><span class="sxs-lookup"><span data-stu-id="a7f31-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="a7f31-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="a7f31-124">\<ImpliesType></span></span>](impliestype-element-net-native.md)  
 <span data-ttu-id="a7f31-125">Applica criteri di runtime a un tipo, se tale criterio è stato applicato al metodo o al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="a7f31-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="a7f31-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="a7f31-126">\<Library></span></span>](library-element-net-native.md)  
 <span data-ttu-id="a7f31-127">Applica criteri di runtime a tutti i tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="a7f31-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="a7f31-128">Questo è un elemento figlio degli elementi [\<Application>](application-element-net-native.md) e [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a7f31-128">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a7f31-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="a7f31-129">\<Method></span></span>](method-element-net-native.md)  
 <span data-ttu-id="a7f31-130">Applica criteri di runtime a un metodo.</span><span class="sxs-lookup"><span data-stu-id="a7f31-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="a7f31-131">Questo è un elemento figlio degli elementi [\<Type>](type-element-net-native.md) e [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a7f31-131">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a7f31-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="a7f31-132">\<MethodInstantiation></span></span>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="a7f31-133">Applica criteri di runtime a un metodo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="a7f31-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="a7f31-134">Questo è un elemento figlio degli elementi [\<Type>](type-element-net-native.md) e [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a7f31-134">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a7f31-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="a7f31-135">\<Namespace></span></span>](namespace-element-net-native.md)  
 <span data-ttu-id="a7f31-136">Applica criteri di runtime a tutti i tipi in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a7f31-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="a7f31-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="a7f31-137">\<Parameter></span></span>](parameter-element-net-native.md)  
 <span data-ttu-id="a7f31-138">Applica criteri di runtime al tipo di argomento passato a un metodo.</span><span class="sxs-lookup"><span data-stu-id="a7f31-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="a7f31-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="a7f31-139">\<Property></span></span>](property-element-net-native.md)  
 <span data-ttu-id="a7f31-140">Applica criteri di runtime a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="a7f31-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="a7f31-141">Questo è un elemento figlio degli elementi [\<Type>](type-element-net-native.md) e [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a7f31-141">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a7f31-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="a7f31-142">\<Subtypes></span></span>](subtypes-element-net-native.md)  
 <span data-ttu-id="a7f31-143">Applica i criteri di runtime a tutte le classi ereditate per il tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="a7f31-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="a7f31-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="a7f31-144">\<Type></span></span>](type-element-net-native.md)  
 <span data-ttu-id="a7f31-145">Applica criteri di runtime a un tipo.</span><span class="sxs-lookup"><span data-stu-id="a7f31-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="a7f31-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="a7f31-146">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="a7f31-147">Applica criteri di runtime a un tipo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="a7f31-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="a7f31-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="a7f31-148">\<TypeParameter></span></span>](typeparameter-element-net-native.md)  
 <span data-ttu-id="a7f31-149">Applica criteri di runtime al tipo rappresentato da un argomento <xref:System.Type> passato a un metodo.</span><span class="sxs-lookup"><span data-stu-id="a7f31-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f31-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7f31-150">See also</span></span>

- [<span data-ttu-id="a7f31-151">Informazioni di riferimento sul file di configurazione rd.xml</span><span class="sxs-lookup"><span data-stu-id="a7f31-151">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
