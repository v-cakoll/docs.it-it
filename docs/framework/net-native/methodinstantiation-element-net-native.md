---
title: <MethodInstantiation> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccc8cd22c3175a2b6456f71d9dc773ce85848949
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275055"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="87641-102">\<MethodInstantiation > elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="87641-102">\<MethodInstantiation> Element (.NET Native)</span></span>
<span data-ttu-id="87641-103">Applica i criteri di reflection di runtime a un metodo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="87641-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87641-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87641-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87641-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="87641-105">Attributes and Elements</span></span>  
 <span data-ttu-id="87641-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="87641-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87641-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="87641-107">Attributes</span></span>  
  
|<span data-ttu-id="87641-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="87641-108">Attribute</span></span>|<span data-ttu-id="87641-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="87641-109">Attribute type</span></span>|<span data-ttu-id="87641-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87641-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="87641-111">Generale</span><span class="sxs-lookup"><span data-stu-id="87641-111">General</span></span>|<span data-ttu-id="87641-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87641-112">Required attribute.</span></span> <span data-ttu-id="87641-113">Specifica il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="87641-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="87641-114">Generale</span><span class="sxs-lookup"><span data-stu-id="87641-114">General</span></span>|<span data-ttu-id="87641-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="87641-115">Optional attribute.</span></span> <span data-ttu-id="87641-116">Specifica i parametri denominati del metodo.</span><span class="sxs-lookup"><span data-stu-id="87641-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="87641-117">Più parametri denominati sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="87641-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="87641-118">L'attributo `Signature` viene usato per differenziare i metodi sottoposti a overload.</span><span class="sxs-lookup"><span data-stu-id="87641-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="87641-119">Generale</span><span class="sxs-lookup"><span data-stu-id="87641-119">General</span></span>|<span data-ttu-id="87641-120">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87641-120">Required attribute.</span></span> <span data-ttu-id="87641-121">Specifica gli argomenti di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="87641-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="87641-122">Se sono presenti più argomenti, saranno separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="87641-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="87641-123">Reflection</span><span class="sxs-lookup"><span data-stu-id="87641-123">Reflection</span></span>|<span data-ttu-id="87641-124">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="87641-124">Optional attribute.</span></span> <span data-ttu-id="87641-125">Controlla l'esecuzione di query per informazioni sul metodo o la sua enumerazione, ma non abilita alcuna chiamata dinamica in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="87641-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="87641-126">Reflection</span><span class="sxs-lookup"><span data-stu-id="87641-126">Reflection</span></span>|<span data-ttu-id="87641-127">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="87641-127">Optional attribute.</span></span> <span data-ttu-id="87641-128">Controlla l'accesso del runtime a un costruttore o al metodo per attivare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="87641-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="87641-129">Questo criterio assicura che un membro possa essere richiamato in modo dinamico in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="87641-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="87641-130">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="87641-130">Name attribute</span></span>  
  
|<span data-ttu-id="87641-131">Valore</span><span class="sxs-lookup"><span data-stu-id="87641-131">Value</span></span>|<span data-ttu-id="87641-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87641-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="87641-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="87641-133">*method_name*</span></span>|<span data-ttu-id="87641-134">Nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="87641-134">The method name.</span></span> <span data-ttu-id="87641-135">Il tipo di metodo viene definito dall'elemento padre [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="87641-135">The type of the method is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="87641-136">Attributo Signature</span><span class="sxs-lookup"><span data-stu-id="87641-136">Signature attribute</span></span>  
  
|<span data-ttu-id="87641-137">Valore</span><span class="sxs-lookup"><span data-stu-id="87641-137">Value</span></span>|<span data-ttu-id="87641-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87641-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="87641-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="87641-139">*method_signature*</span></span>|<span data-ttu-id="87641-140">Specifica i parametri del metodo denominati.</span><span class="sxs-lookup"><span data-stu-id="87641-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="87641-141">Se esistono più parametri, sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="87641-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="87641-142">Attributo di argomenti</span><span class="sxs-lookup"><span data-stu-id="87641-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="87641-143">Valore</span><span class="sxs-lookup"><span data-stu-id="87641-143">Value</span></span>|<span data-ttu-id="87641-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87641-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="87641-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="87641-145">*method_arguments*</span></span>|<span data-ttu-id="87641-146">Specifica gli argomenti tipo generico.</span><span class="sxs-lookup"><span data-stu-id="87641-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="87641-147">Se sono presenti più argomenti, saranno separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="87641-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="87641-148">Ogni argomento deve essere costituito dal nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="87641-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="87641-149">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="87641-149">All other attributes</span></span>  
  
|<span data-ttu-id="87641-150">Valore</span><span class="sxs-lookup"><span data-stu-id="87641-150">Value</span></span>|<span data-ttu-id="87641-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87641-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="87641-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="87641-152">*policy_setting*</span></span>|<span data-ttu-id="87641-153">L'impostazione da applicare a questo tipo di criteri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="87641-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="87641-154">I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`.</span><span class="sxs-lookup"><span data-stu-id="87641-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="87641-155">Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="87641-155">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87641-156">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="87641-156">Child Elements</span></span>  
 <span data-ttu-id="87641-157">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="87641-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87641-158">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="87641-158">Parent Elements</span></span>  
  
|<span data-ttu-id="87641-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="87641-159">Element</span></span>|<span data-ttu-id="87641-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87641-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87641-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="87641-161">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="87641-162">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="87641-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="87641-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="87641-163">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="87641-164">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="87641-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87641-165">Note</span><span class="sxs-lookup"><span data-stu-id="87641-165">Remarks</span></span>  
 <span data-ttu-id="87641-166">L'elemento `<MethodInstantiation>` prevale sui criteri di reflection di runtime del corrispondente metodo generico aperto.</span><span class="sxs-lookup"><span data-stu-id="87641-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87641-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87641-167">See also</span></span>
- [<span data-ttu-id="87641-168">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="87641-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="87641-169">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="87641-169">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="87641-170">Impostazioni dei criteri delle direttive di runtime</span><span class="sxs-lookup"><span data-stu-id="87641-170">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [<span data-ttu-id="87641-171">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="87641-171">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
