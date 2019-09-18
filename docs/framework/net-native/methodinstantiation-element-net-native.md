---
title: <MethodInstantiation>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2c0354853e4725ba3e673fb9142c4a7a85d2121
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049614"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="c4904-102">\<Elemento > MethodInstantiation (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="c4904-102">\<MethodInstantiation> Element (.NET Native)</span></span>
<span data-ttu-id="c4904-103">Applica i criteri di reflection di runtime a un metodo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="c4904-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4904-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4904-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4904-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c4904-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c4904-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c4904-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4904-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="c4904-107">Attributes</span></span>  
  
|<span data-ttu-id="c4904-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="c4904-108">Attribute</span></span>|<span data-ttu-id="c4904-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="c4904-109">Attribute type</span></span>|<span data-ttu-id="c4904-110">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c4904-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="c4904-111">Generale</span><span class="sxs-lookup"><span data-stu-id="c4904-111">General</span></span>|<span data-ttu-id="c4904-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c4904-112">Required attribute.</span></span> <span data-ttu-id="c4904-113">Specifica il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="c4904-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="c4904-114">Generale</span><span class="sxs-lookup"><span data-stu-id="c4904-114">General</span></span>|<span data-ttu-id="c4904-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c4904-115">Optional attribute.</span></span> <span data-ttu-id="c4904-116">Specifica i parametri denominati del metodo.</span><span class="sxs-lookup"><span data-stu-id="c4904-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="c4904-117">Più parametri denominati sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="c4904-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="c4904-118">L'attributo `Signature` viene usato per differenziare i metodi sottoposti a overload.</span><span class="sxs-lookup"><span data-stu-id="c4904-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="c4904-119">Generale</span><span class="sxs-lookup"><span data-stu-id="c4904-119">General</span></span>|<span data-ttu-id="c4904-120">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c4904-120">Required attribute.</span></span> <span data-ttu-id="c4904-121">Specifica gli argomenti tipo generico.</span><span class="sxs-lookup"><span data-stu-id="c4904-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="c4904-122">Se sono presenti più argomenti, saranno separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="c4904-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="c4904-123">Reflection</span><span class="sxs-lookup"><span data-stu-id="c4904-123">Reflection</span></span>|<span data-ttu-id="c4904-124">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c4904-124">Optional attribute.</span></span> <span data-ttu-id="c4904-125">Controlla l'esecuzione di query per informazioni sul metodo o la sua enumerazione, ma non abilita alcuna chiamata dinamica in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c4904-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="c4904-126">Reflection</span><span class="sxs-lookup"><span data-stu-id="c4904-126">Reflection</span></span>|<span data-ttu-id="c4904-127">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c4904-127">Optional attribute.</span></span> <span data-ttu-id="c4904-128">Controlla l'accesso del runtime a un costruttore o al metodo per attivare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="c4904-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="c4904-129">Questo criterio assicura che un membro possa essere richiamato in modo dinamico in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c4904-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="c4904-130">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="c4904-130">Name attribute</span></span>  
  
|<span data-ttu-id="c4904-131">Value</span><span class="sxs-lookup"><span data-stu-id="c4904-131">Value</span></span>|<span data-ttu-id="c4904-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4904-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c4904-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="c4904-133">*method_name*</span></span>|<span data-ttu-id="c4904-134">Nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="c4904-134">The method name.</span></span> <span data-ttu-id="c4904-135">Il tipo di metodo viene definito dall'elemento padre [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="c4904-135">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="c4904-136">Attributo Signature</span><span class="sxs-lookup"><span data-stu-id="c4904-136">Signature attribute</span></span>  
  
|<span data-ttu-id="c4904-137">Value</span><span class="sxs-lookup"><span data-stu-id="c4904-137">Value</span></span>|<span data-ttu-id="c4904-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4904-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c4904-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="c4904-139">*method_signature*</span></span>|<span data-ttu-id="c4904-140">Specifica i parametri del metodo denominati.</span><span class="sxs-lookup"><span data-stu-id="c4904-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="c4904-141">Se esistono più parametri, sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="c4904-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="c4904-142">Attributo di argomenti</span><span class="sxs-lookup"><span data-stu-id="c4904-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="c4904-143">Value</span><span class="sxs-lookup"><span data-stu-id="c4904-143">Value</span></span>|<span data-ttu-id="c4904-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4904-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c4904-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="c4904-145">*method_arguments*</span></span>|<span data-ttu-id="c4904-146">Specifica gli argomenti tipo generico.</span><span class="sxs-lookup"><span data-stu-id="c4904-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="c4904-147">Se sono presenti più argomenti, saranno separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="c4904-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="c4904-148">Ogni argomento deve essere costituito dal nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="c4904-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="c4904-149">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="c4904-149">All other attributes</span></span>  
  
|<span data-ttu-id="c4904-150">Value</span><span class="sxs-lookup"><span data-stu-id="c4904-150">Value</span></span>|<span data-ttu-id="c4904-151">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c4904-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c4904-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="c4904-152">*policy_setting*</span></span>|<span data-ttu-id="c4904-153">L'impostazione da applicare a questo tipo di criteri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="c4904-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="c4904-154">I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`.</span><span class="sxs-lookup"><span data-stu-id="c4904-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="c4904-155">Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="c4904-155">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4904-156">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c4904-156">Child Elements</span></span>  
 <span data-ttu-id="c4904-157">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c4904-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4904-158">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c4904-158">Parent Elements</span></span>  
  
|<span data-ttu-id="c4904-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4904-159">Element</span></span>|<span data-ttu-id="c4904-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4904-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4904-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="c4904-161">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="c4904-162">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="c4904-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="c4904-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="c4904-163">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="c4904-164">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="c4904-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4904-165">Note</span><span class="sxs-lookup"><span data-stu-id="c4904-165">Remarks</span></span>  
 <span data-ttu-id="c4904-166">L'elemento `<MethodInstantiation>` prevale sui criteri di reflection di runtime del corrispondente metodo generico aperto.</span><span class="sxs-lookup"><span data-stu-id="c4904-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4904-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4904-167">See also</span></span>

- [<span data-ttu-id="c4904-168">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="c4904-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="c4904-169">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="c4904-169">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="c4904-170">Impostazioni dei criteri delle direttive di runtime</span><span class="sxs-lookup"><span data-stu-id="c4904-170">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="c4904-171">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="c4904-171">\<Method> Element</span></span>](method-element-net-native.md)
