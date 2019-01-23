---
title: Elemento &lt;GenericParameter&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 002addf0f020365f87e239b7b8707f3a6031003f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519450"
---
# <a name="ltgenericparametergt-element-net-native"></a><span data-ttu-id="3dddc-102">Elemento &lt;GenericParameter&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="3dddc-102">&lt;GenericParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="3dddc-103">Applica i criteri al tipo di parametro di un tipo o di un metodo generico.</span><span class="sxs-lookup"><span data-stu-id="3dddc-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dddc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3dddc-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type"  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dddc-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3dddc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3dddc-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3dddc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dddc-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="3dddc-107">Attributes</span></span>  
  
|<span data-ttu-id="3dddc-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="3dddc-108">Attribute</span></span>|<span data-ttu-id="3dddc-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="3dddc-109">Attribute type</span></span>|<span data-ttu-id="3dddc-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dddc-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="3dddc-111">Generale</span><span class="sxs-lookup"><span data-stu-id="3dddc-111">General</span></span>|<span data-ttu-id="3dddc-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3dddc-112">Required attribute.</span></span> <span data-ttu-id="3dddc-113">Il nome del parametro generico.</span><span class="sxs-lookup"><span data-stu-id="3dddc-113">The name of the generic parameter.</span></span> <span data-ttu-id="3dddc-114">Ad esempio, per il delegato generico <xref:System.Func%603>, il valore dell'attributo `Name` è "TResult" per applicare i criteri di runtime al valore restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="3dddc-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="3dddc-115">Reflection</span><span class="sxs-lookup"><span data-stu-id="3dddc-115">Reflection</span></span>|<span data-ttu-id="3dddc-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-116">Optional attribute.</span></span> <span data-ttu-id="3dddc-117">Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="3dddc-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="3dddc-118">Reflection</span><span class="sxs-lookup"><span data-stu-id="3dddc-118">Reflection</span></span>|<span data-ttu-id="3dddc-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-119">Optional attribute.</span></span> <span data-ttu-id="3dddc-120">Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3dddc-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="3dddc-121">Reflection</span><span class="sxs-lookup"><span data-stu-id="3dddc-121">Reflection</span></span>|<span data-ttu-id="3dddc-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-122">Optional attribute.</span></span> <span data-ttu-id="3dddc-123">Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="3dddc-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="3dddc-124">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="3dddc-124">Serialization</span></span>|<span data-ttu-id="3dddc-125">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-125">Optional attribute.</span></span> <span data-ttu-id="3dddc-126">Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="3dddc-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="3dddc-127">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="3dddc-127">Serialization</span></span>|<span data-ttu-id="3dddc-128">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-128">Optional attribute.</span></span> <span data-ttu-id="3dddc-129">Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3dddc-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="3dddc-130">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="3dddc-130">Serialization</span></span>|<span data-ttu-id="3dddc-131">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-131">Optional attribute.</span></span> <span data-ttu-id="3dddc-132">Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3dddc-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="3dddc-133">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="3dddc-133">Serialization</span></span>|<span data-ttu-id="3dddc-134">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-134">Optional attribute.</span></span> <span data-ttu-id="3dddc-135">Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3dddc-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="3dddc-136">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="3dddc-136">Interop</span></span>|<span data-ttu-id="3dddc-137">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-137">Optional attribute.</span></span> <span data-ttu-id="3dddc-138">Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.</span><span class="sxs-lookup"><span data-stu-id="3dddc-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="3dddc-139">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="3dddc-139">Interop</span></span>|<span data-ttu-id="3dddc-140">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-140">Optional attribute.</span></span> <span data-ttu-id="3dddc-141">Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="3dddc-142">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="3dddc-142">Interop</span></span>|<span data-ttu-id="3dddc-143">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-143">Optional attribute.</span></span> <span data-ttu-id="3dddc-144">Controlla i criteri per il marshalling dei tipi di valore al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="3dddc-145">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="3dddc-145">Name attribute</span></span>  
  
|<span data-ttu-id="3dddc-146">Valore</span><span class="sxs-lookup"><span data-stu-id="3dddc-146">Value</span></span>|<span data-ttu-id="3dddc-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dddc-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3dddc-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="3dddc-148">*generic_parameter_name*</span></span>|<span data-ttu-id="3dddc-149">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3dddc-149">Required attribute.</span></span> <span data-ttu-id="3dddc-150">Il nome del parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="3dddc-150">The name of the generic type parameter.</span></span> <span data-ttu-id="3dddc-151">Ad esempio, per il delegato generico <xref:System.Func%603>, un valore "TResult" per *generic_parameter_name* consente di applicare i criteri di runtime al valore restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="3dddc-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="3dddc-152">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="3dddc-152">All other attributes</span></span>  
  
|<span data-ttu-id="3dddc-153">Valore</span><span class="sxs-lookup"><span data-stu-id="3dddc-153">Value</span></span>|<span data-ttu-id="3dddc-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dddc-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3dddc-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="3dddc-155">*policy_setting*</span></span>|<span data-ttu-id="3dddc-156">L'impostazione da applicare a questo tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="3dddc-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="3dddc-157">I valori consentiti sono `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`.</span><span class="sxs-lookup"><span data-stu-id="3dddc-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="3dddc-158">Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="3dddc-158">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3dddc-159">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3dddc-159">Child Elements</span></span>  
 <span data-ttu-id="3dddc-160">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3dddc-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3dddc-161">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3dddc-161">Parent Elements</span></span>  
  
|<span data-ttu-id="3dddc-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dddc-162">Element</span></span>|<span data-ttu-id="3dddc-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dddc-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3dddc-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="3dddc-164">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="3dddc-165">Applica i criteri di reflection di runtime a un costruttore o a un metodo.</span><span class="sxs-lookup"><span data-stu-id="3dddc-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="3dddc-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="3dddc-166">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="3dddc-167">Applica i criteri di reflection di runtime a un determinato tipo, ad esempio una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="3dddc-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dddc-168">Note</span><span class="sxs-lookup"><span data-stu-id="3dddc-168">Remarks</span></span>  
 <span data-ttu-id="3dddc-169">L'elemento `<GenericParameter>` è figlio dell'elemento [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) o [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) ed è usato per applicare i criteri a un determinato parametro di tipo generico, specificato mediante il nome nella firma del tipo o del metodo generico.</span><span class="sxs-lookup"><span data-stu-id="3dddc-169">The `<GenericParameter>` element is a child of either the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) or [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="3dddc-170">L'elemento `<GenericParameter>` è molto utile se usato con i serializzatori.</span><span class="sxs-lookup"><span data-stu-id="3dddc-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="3dddc-171">L'esempio seguente usa l'elemento `<GenericParameter>` per applicare i criteri al tipo `T` nelle chiamate agli overload del metodo [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) del serializzatore JSON NewtonSoft.</span><span class="sxs-lookup"><span data-stu-id="3dddc-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3dddc-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dddc-172">See also</span></span>
- [<span data-ttu-id="3dddc-173">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="3dddc-173">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
- [<span data-ttu-id="3dddc-174">\<Tipo > elemento</span><span class="sxs-lookup"><span data-stu-id="3dddc-174">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)
- [<span data-ttu-id="3dddc-175">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="3dddc-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="3dddc-176">Impostazioni dei criteri delle direttive di runtime</span><span class="sxs-lookup"><span data-stu-id="3dddc-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [<span data-ttu-id="3dddc-177">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="3dddc-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
