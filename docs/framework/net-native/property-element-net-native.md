---
title: Elemento &lt;Property&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ed75d377814a740edece2b6a69e44acbd8ef0c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45676811"
---
# <a name="ltpropertygt-element-net-native"></a><span data-ttu-id="ad2aa-102">Elemento &lt;Property&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="ad2aa-102">&lt;Property&gt; Element (.NET Native)</span></span>
<span data-ttu-id="ad2aa-103">Applica i criteri di reflection di runtime a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad2aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad2aa-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad2aa-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ad2aa-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ad2aa-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad2aa-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="ad2aa-107">Attributes</span></span>  
  
|<span data-ttu-id="ad2aa-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ad2aa-108">Attribute</span></span>|<span data-ttu-id="ad2aa-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="ad2aa-109">Attribute type</span></span>|<span data-ttu-id="ad2aa-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad2aa-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="ad2aa-111">Generale</span><span class="sxs-lookup"><span data-stu-id="ad2aa-111">General</span></span>|<span data-ttu-id="ad2aa-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-112">Required attribute.</span></span> <span data-ttu-id="ad2aa-113">Specifica il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="ad2aa-114">Reflection</span><span class="sxs-lookup"><span data-stu-id="ad2aa-114">Reflection</span></span>|<span data-ttu-id="ad2aa-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-115">Optional attribute.</span></span> <span data-ttu-id="ad2aa-116">Controlla le query per le informazioni o per l'enumerazione della proprietà, ma non abilita l'accesso dinamico al runtime.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="ad2aa-117">Reflection</span><span class="sxs-lookup"><span data-stu-id="ad2aa-117">Reflection</span></span>|<span data-ttu-id="ad2aa-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-118">Optional attribute.</span></span> <span data-ttu-id="ad2aa-119">Controlla l'accesso in fase di esecuzione alla proprietà per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="ad2aa-120">Questo criterio assicura che una proprietà può essere impostata o recuperata dinamicamente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="ad2aa-121">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="ad2aa-121">Serialization</span></span>|<span data-ttu-id="ad2aa-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-122">Optional attribute.</span></span> <span data-ttu-id="ad2aa-123">Controlla l'accesso in fase di esecuzione a una proprietà per abilitare le istanze di tipo da serializzare in librerie quali il serializzatore JSON Newtonsoft o da usare per il data binding.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="ad2aa-124">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="ad2aa-124">Name attribute</span></span>  
  
|<span data-ttu-id="ad2aa-125">Valore</span><span class="sxs-lookup"><span data-stu-id="ad2aa-125">Value</span></span>|<span data-ttu-id="ad2aa-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad2aa-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ad2aa-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="ad2aa-127">*method_name*</span></span>|<span data-ttu-id="ad2aa-128">Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-128">The property name.</span></span> <span data-ttu-id="ad2aa-129">Il tipo di proprietà viene definito dall'elemento padre [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="ad2aa-129">The type of the property is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="ad2aa-130">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="ad2aa-130">All other attributes</span></span>  
  
|<span data-ttu-id="ad2aa-131">Valore</span><span class="sxs-lookup"><span data-stu-id="ad2aa-131">Value</span></span>|<span data-ttu-id="ad2aa-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad2aa-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ad2aa-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="ad2aa-133">*policy_setting*</span></span>|<span data-ttu-id="ad2aa-134">L'impostazione da applicare a questo tipo di criteri per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="ad2aa-135">I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="ad2aa-136">Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="ad2aa-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad2aa-137">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ad2aa-137">Child Elements</span></span>  
 <span data-ttu-id="ad2aa-138">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad2aa-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ad2aa-139">Parent Elements</span></span>  
  
|<span data-ttu-id="ad2aa-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad2aa-140">Element</span></span>|<span data-ttu-id="ad2aa-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad2aa-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad2aa-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="ad2aa-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="ad2aa-143">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="ad2aa-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="ad2aa-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="ad2aa-145">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad2aa-146">Note</span><span class="sxs-lookup"><span data-stu-id="ad2aa-146">Remarks</span></span>  
 <span data-ttu-id="ad2aa-147">Se i criteri di una proprietà non sono definiti esplicitamente, la proprietà eredita i criteri di runtime dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad2aa-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad2aa-148">Example</span></span>  
 <span data-ttu-id="ad2aa-149">Nell'esempio seguente si usa la reflection per creare un'istanza di un oggetto `Book` e visualizzare i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="ad2aa-150">Il file originale default.rd.xml per il progetto viene visualizzato come segue:</span><span class="sxs-lookup"><span data-stu-id="ad2aa-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="ad2aa-151">Il file applica il valore `All` ai criteri `Activate` per la classe `Book`, che consente di accedere ai costruttori della classe tramite la reflection.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="ad2aa-152">I criteri `Browse` per la classe `Book` vengono ereditati dal relativo spazio dei nomi padre.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="ad2aa-153">Questa proprietà è impostata su `Required Public`, che rende disponibili i metadati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="ad2aa-154">Di seguito viene riportato il codice sorgente per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-154">The following is the source code for the example.</span></span> <span data-ttu-id="ad2aa-155">La variabile `outputBlock` rappresenta un controllo [TextBlock](https://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad2aa-155">The `outputBlock` variable represents a [TextBlock](https://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx) control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="ad2aa-156">Tuttavia, la compilazione e l'esecuzione di questo esempio genera un'eccezione [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="ad2aa-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="ad2aa-157">Anche se i metadati per il tipo `Book` sono stati resi disponibili, non è stato possibile rendere disponibili le implementazioni di funzioni Get di proprietà in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="ad2aa-158">È possibile correggere l'errore in uno di due modi:</span><span class="sxs-lookup"><span data-stu-id="ad2aa-158">We can correct this error by either in one of two ways:</span></span>  
  
-   <span data-ttu-id="ad2aa-159">Definendo i criteri `Dynamic` per il tipo `Book` nel relativo elemento [\<Type>](../../../docs/framework/net-native/type-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="ad2aa-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element.</span></span>  
  
-   <span data-ttu-id="ad2aa-160">Aggiungendo un elemento [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) annidato per ogni proprietà per cui si intende richiamare il getter, come nel seguente file default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="ad2aa-160">By adding a nested [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ad2aa-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad2aa-161">See Also</span></span>  
 [<span data-ttu-id="ad2aa-162">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="ad2aa-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="ad2aa-163">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="ad2aa-163">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="ad2aa-164">Impostazioni dei criteri delle direttive di runtime</span><span class="sxs-lookup"><span data-stu-id="ad2aa-164">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
