---
title: Elemento &lt;MethodInstantiation&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 37e3ff3e792b8067b6d9409d799cf6e30350606a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltmethodinstantiationgt-element-net-native"></a><span data-ttu-id="02307-102">Elemento &lt;MethodInstantiation&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="02307-102">&lt;MethodInstantiation&gt; Element (.NET Native)</span></span>
<span data-ttu-id="02307-103">Applica i criteri di reflection di runtime a un metodo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="02307-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02307-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02307-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02307-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="02307-105">Attributes and Elements</span></span>  
 <span data-ttu-id="02307-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="02307-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02307-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="02307-107">Attributes</span></span>  
  
|<span data-ttu-id="02307-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="02307-108">Attribute</span></span>|<span data-ttu-id="02307-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="02307-109">Attribute type</span></span>|<span data-ttu-id="02307-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02307-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="02307-111">Generale</span><span class="sxs-lookup"><span data-stu-id="02307-111">General</span></span>|<span data-ttu-id="02307-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="02307-112">Required attribute.</span></span> <span data-ttu-id="02307-113">Specifica il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="02307-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="02307-114">Generale</span><span class="sxs-lookup"><span data-stu-id="02307-114">General</span></span>|<span data-ttu-id="02307-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="02307-115">Optional attribute.</span></span> <span data-ttu-id="02307-116">Specifica i parametri denominati del metodo.</span><span class="sxs-lookup"><span data-stu-id="02307-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="02307-117">Più parametri denominati sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="02307-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="02307-118">L'attributo `Signature` viene usato per differenziare i metodi sottoposti a overload.</span><span class="sxs-lookup"><span data-stu-id="02307-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="02307-119">Generale</span><span class="sxs-lookup"><span data-stu-id="02307-119">General</span></span>|<span data-ttu-id="02307-120">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="02307-120">Required attribute.</span></span> <span data-ttu-id="02307-121">Specifica gli argomenti di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="02307-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="02307-122">Se sono presenti più argomenti, saranno separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="02307-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="02307-123">Reflection</span><span class="sxs-lookup"><span data-stu-id="02307-123">Reflection</span></span>|<span data-ttu-id="02307-124">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="02307-124">Optional attribute.</span></span> <span data-ttu-id="02307-125">Controlla l'esecuzione di query per informazioni sul metodo o la sua enumerazione, ma non abilita alcuna chiamata dinamica in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="02307-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="02307-126">Reflection</span><span class="sxs-lookup"><span data-stu-id="02307-126">Reflection</span></span>|<span data-ttu-id="02307-127">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="02307-127">Optional attribute.</span></span> <span data-ttu-id="02307-128">Controlla l'accesso del runtime a un costruttore o al metodo per attivare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="02307-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="02307-129">Questo criterio assicura che un membro possa essere richiamato in modo dinamico in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="02307-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="02307-130">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="02307-130">Name attribute</span></span>  
  
|<span data-ttu-id="02307-131">Valore</span><span class="sxs-lookup"><span data-stu-id="02307-131">Value</span></span>|<span data-ttu-id="02307-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02307-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02307-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="02307-133">*method_name*</span></span>|<span data-ttu-id="02307-134">Nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="02307-134">The method name.</span></span> <span data-ttu-id="02307-135">Il tipo di metodo viene definito dall'elemento padre [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="02307-135">The type of the method is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="02307-136">Attributo Signature</span><span class="sxs-lookup"><span data-stu-id="02307-136">Signature attribute</span></span>  
  
|<span data-ttu-id="02307-137">Valore</span><span class="sxs-lookup"><span data-stu-id="02307-137">Value</span></span>|<span data-ttu-id="02307-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02307-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02307-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="02307-139">*method_signature*</span></span>|<span data-ttu-id="02307-140">Specifica i parametri del metodo denominati.</span><span class="sxs-lookup"><span data-stu-id="02307-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="02307-141">Se esistono più parametri, sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="02307-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="02307-142">Attributo di argomenti</span><span class="sxs-lookup"><span data-stu-id="02307-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="02307-143">Valore</span><span class="sxs-lookup"><span data-stu-id="02307-143">Value</span></span>|<span data-ttu-id="02307-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02307-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02307-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="02307-145">*method_arguments*</span></span>|<span data-ttu-id="02307-146">Specifica gli argomenti tipo generico.</span><span class="sxs-lookup"><span data-stu-id="02307-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="02307-147">Se sono presenti più argomenti, saranno separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="02307-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="02307-148">Ogni argomento deve essere costituito dal nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="02307-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="02307-149">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="02307-149">All other attributes</span></span>  
  
|<span data-ttu-id="02307-150">Valore</span><span class="sxs-lookup"><span data-stu-id="02307-150">Value</span></span>|<span data-ttu-id="02307-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02307-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02307-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="02307-152">*policy_setting*</span></span>|<span data-ttu-id="02307-153">L'impostazione da applicare a questo tipo di criteri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="02307-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="02307-154">I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`.</span><span class="sxs-lookup"><span data-stu-id="02307-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="02307-155">Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="02307-155">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02307-156">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="02307-156">Child Elements</span></span>  
 <span data-ttu-id="02307-157">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="02307-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02307-158">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="02307-158">Parent Elements</span></span>  
  
|<span data-ttu-id="02307-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="02307-159">Element</span></span>|<span data-ttu-id="02307-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02307-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02307-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="02307-161">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="02307-162">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="02307-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="02307-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="02307-163">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="02307-164">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="02307-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02307-165">Note</span><span class="sxs-lookup"><span data-stu-id="02307-165">Remarks</span></span>  
 <span data-ttu-id="02307-166">L'elemento `<MethodInstantiation>` prevale sui criteri di reflection di runtime del corrispondente metodo generico aperto.</span><span class="sxs-lookup"><span data-stu-id="02307-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02307-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02307-167">See Also</span></span>  
 [<span data-ttu-id="02307-168">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="02307-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="02307-169">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="02307-169">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 <span data-ttu-id="02307-170">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime)</span><span class="sxs-lookup"><span data-stu-id="02307-170">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md)</span></span>  
 [<span data-ttu-id="02307-171">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="02307-171">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
