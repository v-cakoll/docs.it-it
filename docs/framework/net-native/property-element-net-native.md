---
title: <Property>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
ms.openlocfilehash: b9bc89804a872dddf1a56c2a3dadc9c3df4f5fd1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128205"
---
# <a name="property-element-net-native"></a><span data-ttu-id="5a67e-102">\<Property>Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="5a67e-102">\<Property> Element (.NET Native)</span></span>
<span data-ttu-id="5a67e-103">Applica i criteri di reflection di runtime a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="5a67e-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a67e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a67e-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a67e-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5a67e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5a67e-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5a67e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a67e-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="5a67e-107">Attributes</span></span>  
  
|<span data-ttu-id="5a67e-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="5a67e-108">Attribute</span></span>|<span data-ttu-id="5a67e-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="5a67e-109">Attribute type</span></span>|<span data-ttu-id="5a67e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a67e-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="5a67e-111">Generale</span><span class="sxs-lookup"><span data-stu-id="5a67e-111">General</span></span>|<span data-ttu-id="5a67e-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5a67e-112">Required attribute.</span></span> <span data-ttu-id="5a67e-113">Specifica il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="5a67e-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="5a67e-114">Reflection</span><span class="sxs-lookup"><span data-stu-id="5a67e-114">Reflection</span></span>|<span data-ttu-id="5a67e-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5a67e-115">Optional attribute.</span></span> <span data-ttu-id="5a67e-116">Controlla le query per le informazioni o per l'enumerazione della proprietà, ma non abilita l'accesso dinamico al runtime.</span><span class="sxs-lookup"><span data-stu-id="5a67e-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="5a67e-117">Reflection</span><span class="sxs-lookup"><span data-stu-id="5a67e-117">Reflection</span></span>|<span data-ttu-id="5a67e-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5a67e-118">Optional attribute.</span></span> <span data-ttu-id="5a67e-119">Controlla l'accesso in fase di esecuzione alla proprietà per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="5a67e-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="5a67e-120">Questo criterio assicura che una proprietà può essere impostata o recuperata dinamicamente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5a67e-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="5a67e-121">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="5a67e-121">Serialization</span></span>|<span data-ttu-id="5a67e-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5a67e-122">Optional attribute.</span></span> <span data-ttu-id="5a67e-123">Controlla l'accesso in fase di esecuzione a una proprietà per abilitare le istanze di tipo da serializzare in librerie quali il serializzatore JSON Newtonsoft o da usare per il data binding.</span><span class="sxs-lookup"><span data-stu-id="5a67e-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="5a67e-124">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="5a67e-124">Name attribute</span></span>  
  
|<span data-ttu-id="5a67e-125">Valore</span><span class="sxs-lookup"><span data-stu-id="5a67e-125">Value</span></span>|<span data-ttu-id="5a67e-126">Description</span><span class="sxs-lookup"><span data-stu-id="5a67e-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a67e-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="5a67e-127">*method_name*</span></span>|<span data-ttu-id="5a67e-128">Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="5a67e-128">The property name.</span></span> <span data-ttu-id="5a67e-129">Il tipo della proprietà viene definito dall' [\<Type>](type-element-net-native.md) elemento padre o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="5a67e-129">The type of the property is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="5a67e-130">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="5a67e-130">All other attributes</span></span>  
  
|<span data-ttu-id="5a67e-131">Valore</span><span class="sxs-lookup"><span data-stu-id="5a67e-131">Value</span></span>|<span data-ttu-id="5a67e-132">Description</span><span class="sxs-lookup"><span data-stu-id="5a67e-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a67e-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="5a67e-133">*policy_setting*</span></span>|<span data-ttu-id="5a67e-134">L'impostazione da applicare a questo tipo di criteri per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="5a67e-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="5a67e-135">I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`.</span><span class="sxs-lookup"><span data-stu-id="5a67e-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="5a67e-136">Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="5a67e-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a67e-137">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5a67e-137">Child Elements</span></span>  
 <span data-ttu-id="5a67e-138">No.</span><span class="sxs-lookup"><span data-stu-id="5a67e-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a67e-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5a67e-139">Parent Elements</span></span>  
  
|<span data-ttu-id="5a67e-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a67e-140">Element</span></span>|<span data-ttu-id="5a67e-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a67e-141">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="5a67e-142">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="5a67e-142">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="5a67e-143">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="5a67e-143">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a67e-144">Commenti</span><span class="sxs-lookup"><span data-stu-id="5a67e-144">Remarks</span></span>  
 <span data-ttu-id="5a67e-145">Se i criteri di una proprietà non sono definiti esplicitamente, la proprietà eredita i criteri di runtime dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="5a67e-145">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a67e-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a67e-146">Example</span></span>  
 <span data-ttu-id="5a67e-147">Nell'esempio seguente si usa la reflection per creare un'istanza di un oggetto `Book` e visualizzare i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="5a67e-147">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="5a67e-148">Il file originale default.rd.xml per il progetto viene visualizzato come segue:</span><span class="sxs-lookup"><span data-stu-id="5a67e-148">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="5a67e-149">Il file applica il valore `All` ai criteri `Activate` per la classe `Book`, che consente di accedere ai costruttori della classe tramite la reflection.</span><span class="sxs-lookup"><span data-stu-id="5a67e-149">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="5a67e-150">I criteri `Browse` per la classe `Book` vengono ereditati dal relativo spazio dei nomi padre.</span><span class="sxs-lookup"><span data-stu-id="5a67e-150">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="5a67e-151">Questa proprietà è impostata su `Required Public`, che rende disponibili i metadati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5a67e-151">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="5a67e-152">Di seguito viene riportato il codice sorgente per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="5a67e-152">The following is the source code for the example.</span></span> <span data-ttu-id="5a67e-153">La `outputBlock` variabile rappresenta un <xref:Windows.UI.Xaml.Controls.TextBlock> controllo.</span><span class="sxs-lookup"><span data-stu-id="5a67e-153">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="5a67e-154">Tuttavia, la compilazione e l'esecuzione di questo esempio genera un'eccezione [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="5a67e-154">However, compiling and executing this example throws a [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="5a67e-155">Anche se i metadati per il tipo `Book` sono stati resi disponibili, non è stato possibile rendere disponibili le implementazioni di funzioni Get di proprietà in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="5a67e-155">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="5a67e-156">È possibile correggere l'errore in uno di due modi:</span><span class="sxs-lookup"><span data-stu-id="5a67e-156">We can correct this error by either in one of two ways:</span></span>  
  
- <span data-ttu-id="5a67e-157">definendo i `Dynamic` criteri per il `Book` tipo nel relativo [\<Type>](type-element-net-native.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="5a67e-157">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](type-element-net-native.md) element.</span></span>  
  
- <span data-ttu-id="5a67e-158">Con l'aggiunta di un elemento annidato [\<Property>](property-element-net-native.md) per ogni proprietà di cui si desidera richiamare il getter, come nel seguente file default. Rd. XML.</span><span class="sxs-lookup"><span data-stu-id="5a67e-158">By adding a nested [\<Property>](property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5a67e-159">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5a67e-159">See also</span></span>

- [<span data-ttu-id="5a67e-160">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="5a67e-160">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="5a67e-161">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="5a67e-161">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="5a67e-162">Impostazioni dei criteri della direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="5a67e-162">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
