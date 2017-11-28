---
title: Elemento &lt;GenericParameter&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c682c75d4be78e9219a32e2a92520e9f9bfff823
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltgenericparametergt-element-net-native"></a><span data-ttu-id="dd1ed-102">Elemento &lt;GenericParameter&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="dd1ed-102">&lt;GenericParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="dd1ed-103">Applica i criteri al tipo di parametro di un tipo o di un metodo generico.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd1ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd1ed-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type" />  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd1ed-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dd1ed-105">Attributes and Elements</span></span>  
 <span data-ttu-id="dd1ed-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd1ed-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="dd1ed-107">Attributes</span></span>  
  
|<span data-ttu-id="dd1ed-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="dd1ed-108">Attribute</span></span>|<span data-ttu-id="dd1ed-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="dd1ed-109">Attribute type</span></span>|<span data-ttu-id="dd1ed-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd1ed-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="dd1ed-111">Generale</span><span class="sxs-lookup"><span data-stu-id="dd1ed-111">General</span></span>|<span data-ttu-id="dd1ed-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-112">Required attribute.</span></span> <span data-ttu-id="dd1ed-113">Il nome del parametro generico.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-113">The name of the generic parameter.</span></span> <span data-ttu-id="dd1ed-114">Ad esempio, per il delegato generico <xref:System.Func%603>, il valore dell'attributo `Name` è "TResult" per applicare i criteri di runtime al valore restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="dd1ed-115">Reflection</span><span class="sxs-lookup"><span data-stu-id="dd1ed-115">Reflection</span></span>|<span data-ttu-id="dd1ed-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-116">Optional attribute.</span></span> <span data-ttu-id="dd1ed-117">Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="dd1ed-118">Reflection</span><span class="sxs-lookup"><span data-stu-id="dd1ed-118">Reflection</span></span>|<span data-ttu-id="dd1ed-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-119">Optional attribute.</span></span> <span data-ttu-id="dd1ed-120">Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="dd1ed-121">Reflection</span><span class="sxs-lookup"><span data-stu-id="dd1ed-121">Reflection</span></span>|<span data-ttu-id="dd1ed-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-122">Optional attribute.</span></span> <span data-ttu-id="dd1ed-123">Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="dd1ed-124">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="dd1ed-124">Serialization</span></span>|<span data-ttu-id="dd1ed-125">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-125">Optional attribute.</span></span> <span data-ttu-id="dd1ed-126">Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="dd1ed-127">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="dd1ed-127">Serialization</span></span>|<span data-ttu-id="dd1ed-128">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-128">Optional attribute.</span></span> <span data-ttu-id="dd1ed-129">Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="dd1ed-130">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="dd1ed-130">Serialization</span></span>|<span data-ttu-id="dd1ed-131">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-131">Optional attribute.</span></span> <span data-ttu-id="dd1ed-132">Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="dd1ed-133">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="dd1ed-133">Serialization</span></span>|<span data-ttu-id="dd1ed-134">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-134">Optional attribute.</span></span> <span data-ttu-id="dd1ed-135">Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="dd1ed-136">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="dd1ed-136">Interop</span></span>|<span data-ttu-id="dd1ed-137">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-137">Optional attribute.</span></span> <span data-ttu-id="dd1ed-138">Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="dd1ed-139">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="dd1ed-139">Interop</span></span>|<span data-ttu-id="dd1ed-140">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-140">Optional attribute.</span></span> <span data-ttu-id="dd1ed-141">Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="dd1ed-142">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="dd1ed-142">Interop</span></span>|<span data-ttu-id="dd1ed-143">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-143">Optional attribute.</span></span> <span data-ttu-id="dd1ed-144">Controlla i criteri per il marshalling dei tipi di valore al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="dd1ed-145">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="dd1ed-145">Name attribute</span></span>  
  
|<span data-ttu-id="dd1ed-146">Valore</span><span class="sxs-lookup"><span data-stu-id="dd1ed-146">Value</span></span>|<span data-ttu-id="dd1ed-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd1ed-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dd1ed-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="dd1ed-148">*generic_parameter_name*</span></span>|<span data-ttu-id="dd1ed-149">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-149">Required attribute.</span></span> <span data-ttu-id="dd1ed-150">Il nome del parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-150">The name of the generic type parameter.</span></span> <span data-ttu-id="dd1ed-151">Ad esempio, per il delegato generico <xref:System.Func%603>, un valore "TResult" per *generic_parameter_name* consente di applicare i criteri di runtime al valore restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="dd1ed-152">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="dd1ed-152">All other attributes</span></span>  
  
|<span data-ttu-id="dd1ed-153">Valore</span><span class="sxs-lookup"><span data-stu-id="dd1ed-153">Value</span></span>|<span data-ttu-id="dd1ed-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd1ed-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dd1ed-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="dd1ed-155">*policy_setting*</span></span>|<span data-ttu-id="dd1ed-156">L'impostazione da applicare a questo tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="dd1ed-157">I valori consentiti sono `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="dd1ed-158">Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="dd1ed-158">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd1ed-159">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dd1ed-159">Child Elements</span></span>  
 <span data-ttu-id="dd1ed-160">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd1ed-161">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dd1ed-161">Parent Elements</span></span>  
  
|<span data-ttu-id="dd1ed-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd1ed-162">Element</span></span>|<span data-ttu-id="dd1ed-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd1ed-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd1ed-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="dd1ed-164">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="dd1ed-165">Applica i criteri di reflection di runtime a un costruttore o a un metodo.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="dd1ed-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="dd1ed-166">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="dd1ed-167">Applica i criteri di reflection di runtime a un determinato tipo, ad esempio una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd1ed-168">Note</span><span class="sxs-lookup"><span data-stu-id="dd1ed-168">Remarks</span></span>  
 <span data-ttu-id="dd1ed-169">L'elemento `<GenericParameter>` è figlio dell'elemento [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) o [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) ed è usato per applicare i criteri a un determinato parametro di tipo generico, specificato mediante il nome nella firma del tipo o del metodo generico.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-169">The `<GenericParameter>` element is a child of either the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) or [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="dd1ed-170">L'elemento `<GenericParameter>` è molto utile se usato con i serializzatori.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="dd1ed-171">L'esempio seguente usa l'elemento `<GenericParameter>` per applicare i criteri al tipo `T` nelle chiamate agli overload del metodo [JsonConvert.DeserializeObject\<T>(String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) del serializzatore JSON NewtonSoft.</span><span class="sxs-lookup"><span data-stu-id="dd1ed-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd1ed-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd1ed-172">See Also</span></span>  
 [<span data-ttu-id="dd1ed-173">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="dd1ed-173">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="dd1ed-174">\<Tipo > elemento</span><span class="sxs-lookup"><span data-stu-id="dd1ed-174">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 [<span data-ttu-id="dd1ed-175">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="dd1ed-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 <span data-ttu-id="dd1ed-176">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime)</span><span class="sxs-lookup"><span data-stu-id="dd1ed-176">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md)</span></span>  
 [<span data-ttu-id="dd1ed-177">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="dd1ed-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
