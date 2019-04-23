---
title: <TypeParameter> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b03c87c70fa1bfcd331f468d369632f4164300bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110214"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="b6f26-102">\<TypeParameter > elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="b6f26-102">\<TypeParameter> Element (.NET Native)</span></span>
<span data-ttu-id="b6f26-103">Applica i criteri al tipo rappresentato da un argomento tipo passato a un metodo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6f26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6f26-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6f26-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6f26-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b6f26-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6f26-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6f26-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6f26-107">Attributes</span></span>  
  
|<span data-ttu-id="b6f26-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="b6f26-108">Attribute</span></span>|<span data-ttu-id="b6f26-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="b6f26-109">Attribute type</span></span>|<span data-ttu-id="b6f26-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6f26-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="b6f26-111">Generale</span><span class="sxs-lookup"><span data-stu-id="b6f26-111">General</span></span>|<span data-ttu-id="b6f26-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b6f26-112">Required attribute.</span></span> <span data-ttu-id="b6f26-113">Il nome del parametro di tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="b6f26-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="b6f26-114">Ad esempio, per la firma del metodo `Type.GetInterfaceMap(Type interfaceType)`, il valore dell'attributo `Name` è "interfaceType".</span><span class="sxs-lookup"><span data-stu-id="b6f26-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="b6f26-115">Reflection</span><span class="sxs-lookup"><span data-stu-id="b6f26-115">Reflection</span></span>|<span data-ttu-id="b6f26-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-116">Optional attribute.</span></span> <span data-ttu-id="b6f26-117">Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="b6f26-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="b6f26-118">Reflection</span><span class="sxs-lookup"><span data-stu-id="b6f26-118">Reflection</span></span>|<span data-ttu-id="b6f26-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-119">Optional attribute.</span></span> <span data-ttu-id="b6f26-120">Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b6f26-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="b6f26-121">Reflection</span><span class="sxs-lookup"><span data-stu-id="b6f26-121">Reflection</span></span>|<span data-ttu-id="b6f26-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-122">Optional attribute.</span></span> <span data-ttu-id="b6f26-123">Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="b6f26-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="b6f26-124">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="b6f26-124">Serialization</span></span>|<span data-ttu-id="b6f26-125">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-125">Optional attribute.</span></span> <span data-ttu-id="b6f26-126">Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="b6f26-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="b6f26-127">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="b6f26-127">Serialization</span></span>|<span data-ttu-id="b6f26-128">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-128">Optional attribute.</span></span> <span data-ttu-id="b6f26-129">Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6f26-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="b6f26-130">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="b6f26-130">Serialization</span></span>|<span data-ttu-id="b6f26-131">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-131">Optional attribute.</span></span> <span data-ttu-id="b6f26-132">Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6f26-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="b6f26-133">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="b6f26-133">Serialization</span></span>|<span data-ttu-id="b6f26-134">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-134">Optional attribute.</span></span> <span data-ttu-id="b6f26-135">Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6f26-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="b6f26-136">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="b6f26-136">Interop</span></span>|<span data-ttu-id="b6f26-137">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-137">Optional attribute.</span></span> <span data-ttu-id="b6f26-138">Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.</span><span class="sxs-lookup"><span data-stu-id="b6f26-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="b6f26-139">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="b6f26-139">Interop</span></span>|<span data-ttu-id="b6f26-140">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-140">Optional attribute.</span></span> <span data-ttu-id="b6f26-141">Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="b6f26-142">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="b6f26-142">Interop</span></span>|<span data-ttu-id="b6f26-143">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-143">Optional attribute.</span></span> <span data-ttu-id="b6f26-144">Controlla i criteri per il marshalling dei tipi di valore al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="b6f26-145">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="b6f26-145">Name attribute</span></span>  
  
|<span data-ttu-id="b6f26-146">Value</span><span class="sxs-lookup"><span data-stu-id="b6f26-146">Value</span></span>|<span data-ttu-id="b6f26-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6f26-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b6f26-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="b6f26-148">*parameter_name*</span></span>|<span data-ttu-id="b6f26-149">Il nome del parametro di tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="b6f26-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="b6f26-150">Ad esempio, per la firma del metodo `Type.GetInterfaceMap(Type interfaceType)`, il valore dell'attributo `Name` è "interfaceType".</span><span class="sxs-lookup"><span data-stu-id="b6f26-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="b6f26-151">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="b6f26-151">All other attributes</span></span>  
  
|<span data-ttu-id="b6f26-152">Value</span><span class="sxs-lookup"><span data-stu-id="b6f26-152">Value</span></span>|<span data-ttu-id="b6f26-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6f26-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b6f26-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="b6f26-154">*policy_setting*</span></span>|<span data-ttu-id="b6f26-155">L'impostazione da applicare a questo tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="b6f26-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="b6f26-156">I valori consentiti sono `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`.</span><span class="sxs-lookup"><span data-stu-id="b6f26-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="b6f26-157">Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="b6f26-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6f26-158">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6f26-158">Child Elements</span></span>  
 <span data-ttu-id="b6f26-159">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b6f26-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6f26-160">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6f26-160">Parent Elements</span></span>  
  
|<span data-ttu-id="b6f26-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6f26-161">Element</span></span>|<span data-ttu-id="b6f26-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6f26-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6f26-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="b6f26-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="b6f26-164">Applica i criteri di reflection di runtime a un costruttore o a un metodo.</span><span class="sxs-lookup"><span data-stu-id="b6f26-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6f26-165">Note</span><span class="sxs-lookup"><span data-stu-id="b6f26-165">Remarks</span></span>  
 <span data-ttu-id="b6f26-166">L'elemento `<TypeParameter>` è simile all'elemento [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md), ma può essere applicato solo a parametri di tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="b6f26-166">The `<TypeParameter>` element is similar to the [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="b6f26-167">Applica i criteri a qualsiasi tipo rappresentato al runtime dall'argomento Type specificato dall'attributo `Name`.</span><span class="sxs-lookup"><span data-stu-id="b6f26-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="b6f26-168">Ad esempio, il serializzatore JSON di NewtonSoft include un metodo statico `JsonConvert.DeserializeObject(String value, Type type)`.</span><span class="sxs-lookup"><span data-stu-id="b6f26-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="b6f26-169">Le seguenti direttive di reflection:</span><span class="sxs-lookup"><span data-stu-id="b6f26-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="b6f26-170">specificano che i metadati per il tipo di runtime rappresentati dall'argomento `type` devono essere resi disponibili per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="b6f26-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="b6f26-171">Se queste direttive di runtime vengono applicate a un progetto che include il seguente codice sorgente:</span><span class="sxs-lookup"><span data-stu-id="b6f26-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="b6f26-172">le direttive di reflection rendono disponibili i metadati per il tipo `StockQuote` per il serializzatore JSON di NewtonSoft al runtime.</span><span class="sxs-lookup"><span data-stu-id="b6f26-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6f26-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6f26-173">See also</span></span>

- [<span data-ttu-id="b6f26-174">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="b6f26-174">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
- [<span data-ttu-id="b6f26-175">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="b6f26-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="b6f26-176">Impostazioni dei criteri delle direttive di runtime</span><span class="sxs-lookup"><span data-stu-id="b6f26-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [<span data-ttu-id="b6f26-177">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="b6f26-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
