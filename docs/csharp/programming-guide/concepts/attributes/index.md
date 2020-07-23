---
title: Attributi (C#)
description: Informazioni su come usare gli attributi per associare metadati o informazioni dichiarative con il codice in C#. Un attributo può essere sottoposto a query in fase di esecuzione tramite reflection.
ms.date: 04/26/2018
ms.openlocfilehash: 5c57838b649531d8e8fe89919771adf8830e7f54
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924985"
---
# <a name="attributes-c"></a><span data-ttu-id="25f8b-104">Attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="25f8b-104">Attributes (C#)</span></span>

<span data-ttu-id="25f8b-105">Gli attributi offrono un metodo efficace per l'associazione di metadati o informazioni dichiarative con il codice (assembly, tipi, metodi, proprietà e così via).</span><span class="sxs-lookup"><span data-stu-id="25f8b-105">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="25f8b-106">Dopo aver associato un attributo a un'entità di programma, in fase di esecuzione è possibile eseguire una query su tale attributo usando una tecnica denominata *reflection*.</span><span class="sxs-lookup"><span data-stu-id="25f8b-106">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="25f8b-107">Per altre informazioni, vedere [Reflection (C#)](../reflection.md).</span><span class="sxs-lookup"><span data-stu-id="25f8b-107">For more information, see [Reflection (C#)](../reflection.md).</span></span>

<span data-ttu-id="25f8b-108">Di seguito sono riportate le proprietà degli attributi:</span><span class="sxs-lookup"><span data-stu-id="25f8b-108">Attributes have the following properties:</span></span>

- <span data-ttu-id="25f8b-109">Gli attributi aggiungono metadati al programma.</span><span class="sxs-lookup"><span data-stu-id="25f8b-109">Attributes add metadata to your program.</span></span> <span data-ttu-id="25f8b-110">I *metadati* sono informazioni relative ai tipi definiti in un programma.</span><span class="sxs-lookup"><span data-stu-id="25f8b-110">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="25f8b-111">Tutti gli assembly .NET contengono un set specificato di metadati che descrive i tipi e membri dei tipi definiti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="25f8b-111">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="25f8b-112">È possibile aggiungere attributi personalizzati per specificare altre informazioni eventualmente necessarie.</span><span class="sxs-lookup"><span data-stu-id="25f8b-112">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="25f8b-113">Per altre informazioni, vedere [Creazione di attributi personalizzati (C#)](creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="25f8b-113">For more information, see, [Creating Custom Attributes (C#)](creating-custom-attributes.md).</span></span>
- <span data-ttu-id="25f8b-114">È possibile applicare uno o più attributi a interi assembly, moduli o elementi di programma di minori dimensioni, ad esempio classi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="25f8b-114">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>
- <span data-ttu-id="25f8b-115">Gli attributi possono accettare argomenti nello stesso modo dei metodi e delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="25f8b-115">Attributes can accept arguments in the same way as methods and properties.</span></span>
- <span data-ttu-id="25f8b-116">Il programma può esaminare i propri metadati oppure i metadati di un altro programma tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="25f8b-116">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="25f8b-117">Per altre informazioni, vedere [Accesso agli attributi tramite reflection (C#)](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="25f8b-117">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="using-attributes"></a><span data-ttu-id="25f8b-118">Utilizzo di attributi</span><span class="sxs-lookup"><span data-stu-id="25f8b-118">Using attributes</span></span>

<span data-ttu-id="25f8b-119">È possibile usare attributi nella maggior parte delle dichiarazioni, anche se la validità di un attributo specifico può essere limitata ad alcuni tipi di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="25f8b-119">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="25f8b-120">Per specificare un attributo in C# inserire il nome dell'attributo racchiuso tra parentesi quadre ([]) sopra la dichiarazione dell'entità a cui è applicato.</span><span class="sxs-lookup"><span data-stu-id="25f8b-120">In C#, you specify an attribute by placing the name of the attribute enclosed in square brackets ([]) above the declaration of the entity to which it applies.</span></span>

<span data-ttu-id="25f8b-121">Nell'esempio seguente l'attributo <xref:System.SerializableAttribute> viene usato per applicare una caratteristica specifica a una classe:</span><span class="sxs-lookup"><span data-stu-id="25f8b-121">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>

[!code-csharp[Using the serializable attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#1)]

<span data-ttu-id="25f8b-122">Un metodo con l'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> è dichiarato come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="25f8b-122">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like the following example:</span></span>

[!code-csharp[Declaring a method to import from an external library](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#2)]

<span data-ttu-id="25f8b-123">In una dichiarazione è possibile inserire più attributi, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="25f8b-123">More than one attribute can be placed on a declaration as the following example shows:</span></span>

[!code-csharp[Including the interop namespace](~/samples/snippets/csharp/attributes/AttributesOverview.cs#3)]
[!code-csharp[Declaring two way marshaling for arguments](~/samples/snippets/csharp/attributes/AttributesOverview.cs#4)]

<span data-ttu-id="25f8b-124">Alcuni attributi possono essere specificati più volte per una stessa entità.</span><span class="sxs-lookup"><span data-stu-id="25f8b-124">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="25f8b-125">Un esempio di attributo multiuso è <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="25f8b-125">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>

[!code-csharp[Using the conditional attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#5)]

> [!NOTE]
> <span data-ttu-id="25f8b-126">Per convenzione tutti i nomi di attributo terminano con la parola "Attribute", in modo che sia possibile distinguerli da altri elementi delle librerie .NET.</span><span class="sxs-lookup"><span data-stu-id="25f8b-126">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET libraries.</span></span> <span data-ttu-id="25f8b-127">Tuttavia, quando gli attributi vengono usati nel codice, non è necessario specificare il suffisso Attribute.</span><span class="sxs-lookup"><span data-stu-id="25f8b-127">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="25f8b-128">Ad esempio, `[DllImport]` è equivalente a `[DllImportAttribute]` , ma `DllImportAttribute` è il nome effettivo dell'attributo nella libreria di classi .NET.</span><span class="sxs-lookup"><span data-stu-id="25f8b-128">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Class Library.</span></span>

### <a name="attribute-parameters"></a><span data-ttu-id="25f8b-129">Parametri degli attributi</span><span class="sxs-lookup"><span data-stu-id="25f8b-129">Attribute parameters</span></span>

<span data-ttu-id="25f8b-130">Diversi attributi dispongono di parametri, che possono essere posizionali, senza nome o denominati.</span><span class="sxs-lookup"><span data-stu-id="25f8b-130">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="25f8b-131">I parametri posizionali devono essere specificati in un determinato ordine e non possono essere omessi.</span><span class="sxs-lookup"><span data-stu-id="25f8b-131">Any positional parameters must be specified in a certain order and cannot be omitted.</span></span> <span data-ttu-id="25f8b-132">I parametri denominati sono facoltativi e possono essere specificati in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="25f8b-132">Named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="25f8b-133">I parametri posizionali vengono specificati per primi.</span><span class="sxs-lookup"><span data-stu-id="25f8b-133">Positional parameters are specified first.</span></span> <span data-ttu-id="25f8b-134">I tre attributi seguenti, ad esempio, sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="25f8b-134">For example, these three attributes are equivalent:</span></span>

```csharp
[DllImport("user32.dll")]
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]
```

<span data-ttu-id="25f8b-135">Il primo parametro, ovvero il nome della DLL, è posizionale ed è sempre specificato per primo. Gli altri parametri sono denominati.</span><span class="sxs-lookup"><span data-stu-id="25f8b-135">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="25f8b-136">In questo caso, entrambi i parametri denominati sono impostati automaticamente su false e possono quindi essere omessi.</span><span class="sxs-lookup"><span data-stu-id="25f8b-136">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="25f8b-137">I parametri posizionali corrispondono ai parametri del costruttore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="25f8b-137">Positional parameters correspond to the parameters of the attribute constructor.</span></span> <span data-ttu-id="25f8b-138">I parametri denominati o facoltativi corrispondono a proprietà o campi dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="25f8b-138">Named or optional parameters correspond to either properties or fields of the attribute.</span></span> <span data-ttu-id="25f8b-139">Per informazioni sui valori predefiniti dei parametri, fare riferimento alla documentazione di ciascun attributo.</span><span class="sxs-lookup"><span data-stu-id="25f8b-139">Refer to the individual attribute's documentation for information on default parameter values.</span></span>

### <a name="attribute-targets"></a><span data-ttu-id="25f8b-140">Destinazioni degli attributi</span><span class="sxs-lookup"><span data-stu-id="25f8b-140">Attribute targets</span></span>

<span data-ttu-id="25f8b-141">La *destinazione* di un attributo è l'entità a cui tale attributo viene applicato.</span><span class="sxs-lookup"><span data-stu-id="25f8b-141">The *target* of an attribute is the entity which the attribute applies to.</span></span> <span data-ttu-id="25f8b-142">Un attributo, ad esempio, può essere applicato a una classe, a un metodo particolare o a un intero assembly.</span><span class="sxs-lookup"><span data-stu-id="25f8b-142">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="25f8b-143">Per impostazione predefinita, un attributo viene applicato all'elemento che lo segue.</span><span class="sxs-lookup"><span data-stu-id="25f8b-143">By default, an attribute applies to the element that follows it.</span></span> <span data-ttu-id="25f8b-144">È tuttavia possibile identificare in modo esplicito, ad esempio, se un attributo viene applicato a un metodo, al relativo parametro o al relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="25f8b-144">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>

<span data-ttu-id="25f8b-145">Per identificare in modo esplicito la destinazione di un attributo, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="25f8b-145">To explicitly identify an attribute target, use the following syntax:</span></span>

```csharp
[target : attribute-list]
```

<span data-ttu-id="25f8b-146">Nella tabella seguente sono elencati i possibili valori di `target`.</span><span class="sxs-lookup"><span data-stu-id="25f8b-146">The list of possible `target` values is shown in the following table.</span></span>

|<span data-ttu-id="25f8b-147">Valore di destinazione</span><span class="sxs-lookup"><span data-stu-id="25f8b-147">Target value</span></span>|<span data-ttu-id="25f8b-148">Si applica a</span><span class="sxs-lookup"><span data-stu-id="25f8b-148">Applies to</span></span>|
|------------------|----------------|
|`assembly`|<span data-ttu-id="25f8b-149">Intero assembly</span><span class="sxs-lookup"><span data-stu-id="25f8b-149">Entire assembly</span></span>|
|`module`|<span data-ttu-id="25f8b-150">Modulo di assembly corrente</span><span class="sxs-lookup"><span data-stu-id="25f8b-150">Current assembly module</span></span>|
|`field`|<span data-ttu-id="25f8b-151">Campo in una classe o uno struct</span><span class="sxs-lookup"><span data-stu-id="25f8b-151">Field in a class or a struct</span></span>|
|`event`|<span data-ttu-id="25f8b-152">Evento</span><span class="sxs-lookup"><span data-stu-id="25f8b-152">Event</span></span>|
|`method`|<span data-ttu-id="25f8b-153">Metodo o funzioni di accesso alle proprietà `get` e `set`</span><span class="sxs-lookup"><span data-stu-id="25f8b-153">Method or `get` and `set` property accessors</span></span>|
|`param`|<span data-ttu-id="25f8b-154">Parametri del metodo o parametri della funzione di accesso alla proprietà `set`</span><span class="sxs-lookup"><span data-stu-id="25f8b-154">Method parameters or `set` property accessor parameters</span></span>|
|`property`|<span data-ttu-id="25f8b-155">Proprietà</span><span class="sxs-lookup"><span data-stu-id="25f8b-155">Property</span></span>|
|`return`|<span data-ttu-id="25f8b-156">Valore restituito di un metodo, un indicizzatore di proprietà o una funzione di accesso alla proprietà `get`</span><span class="sxs-lookup"><span data-stu-id="25f8b-156">Return value of a method, property indexer, or `get` property accessor</span></span>|
|`type`|<span data-ttu-id="25f8b-157">Struct, classe, interfaccia, enumeratore o delegato</span><span class="sxs-lookup"><span data-stu-id="25f8b-157">Struct, class, interface, enum, or delegate</span></span>|

<span data-ttu-id="25f8b-158">È necessario specificare il valore di destinazione `field` per applicare un attributo al campo sottostante creato per una [proprietà implementata automaticamente](../../../properties.md).</span><span class="sxs-lookup"><span data-stu-id="25f8b-158">You would specify the `field` target value to apply an attribute to the backing field created for an [auto-implemented property](../../../properties.md).</span></span>

<span data-ttu-id="25f8b-159">Nell'esempio seguente viene illustrato come applicare attributi ad assembly e moduli.</span><span class="sxs-lookup"><span data-stu-id="25f8b-159">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="25f8b-160">Per altre informazioni, vedere [Attributi comuni (C#)](../../../language-reference/attributes/global.md).</span><span class="sxs-lookup"><span data-stu-id="25f8b-160">For more information, see [Common Attributes (C#)](../../../language-reference/attributes/global.md).</span></span>

```csharp
using System;
using System.Reflection;
[assembly: AssemblyTitleAttribute("Production assembly 4")]
[module: CLSCompliant(true)]
```

<span data-ttu-id="25f8b-161">Nell'esempio seguente viene illustrato come applicare gli attributi a metodi, parametri di metodo e valori restituiti dal metodo in C#.</span><span class="sxs-lookup"><span data-stu-id="25f8b-161">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>

[!code-csharp[Applying attributes to different code elements](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#6)]

> [!NOTE]
> <span data-ttu-id="25f8b-162">Indipendentemente dalle destinazioni in cui l'oggetto `ValidatedContract` è definito come valido, è necessario specificare la destinazione `return`, anche se `ValidatedContract` viene definito in modo da essere valido solo per i valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="25f8b-162">Regardless of the targets on which `ValidatedContract` is defined to be valid, the `return` target has to be specified, even if `ValidatedContract` were defined to apply only to return values.</span></span> <span data-ttu-id="25f8b-163">In altre parole, il compilatore non usa le informazioni `AttributeUsage` per risolvere le destinazioni degli attributi ambigue.</span><span class="sxs-lookup"><span data-stu-id="25f8b-163">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="25f8b-164">Per altre informazioni, vedere [AttributeUsage (C#)](../../../language-reference/attributes/general.md).</span><span class="sxs-lookup"><span data-stu-id="25f8b-164">For more information, see [AttributeUsage (C#)](../../../language-reference/attributes/general.md).</span></span>

## <a name="common-uses-for-attributes"></a><span data-ttu-id="25f8b-165">Usi comuni degli attributi</span><span class="sxs-lookup"><span data-stu-id="25f8b-165">Common uses for attributes</span></span>

<span data-ttu-id="25f8b-166">Di seguito vengono elencati alcuni degli usi comuni degli attributi nel codice:</span><span class="sxs-lookup"><span data-stu-id="25f8b-166">The following list includes a few of the common uses of attributes in code:</span></span>

- <span data-ttu-id="25f8b-167">Contrassegno dei metodi mediante l'attributo `WebMethod` nei servizi Web per indicare che è possibile chiamare il metodo tramite il protocollo SOAP.</span><span class="sxs-lookup"><span data-stu-id="25f8b-167">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="25f8b-168">Per altre informazioni, vedere <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="25f8b-168">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>
- <span data-ttu-id="25f8b-169">Descrizione della procedura di marshalling dei parametri del metodo durante l'interazione con il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="25f8b-169">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="25f8b-170">Per altre informazioni, vedere <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="25f8b-170">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>
- <span data-ttu-id="25f8b-171">Descrizione delle proprietà COM per classi, metodi e interfacce.</span><span class="sxs-lookup"><span data-stu-id="25f8b-171">Describing the COM properties for classes, methods, and interfaces.</span></span>
- <span data-ttu-id="25f8b-172">Chiamata al codice non gestito che usa la classe <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="25f8b-172">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>
- <span data-ttu-id="25f8b-173">Descrizione dell'assembly con indicazione di titolo, versione, descrizione o marchio.</span><span class="sxs-lookup"><span data-stu-id="25f8b-173">Describing your assembly in terms of title, version, description, or trademark.</span></span>
- <span data-ttu-id="25f8b-174">Descrizione dei membri della classe da serializzare per la persistenza.</span><span class="sxs-lookup"><span data-stu-id="25f8b-174">Describing which members of a class to serialize for persistence.</span></span>
- <span data-ttu-id="25f8b-175">Descrizione della procedura di mapping tra membri di una classe e nodi XML per la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="25f8b-175">Describing how to map between class members and XML nodes for XML serialization.</span></span>
- <span data-ttu-id="25f8b-176">Descrizione dei requisiti di sicurezza per i metodi.</span><span class="sxs-lookup"><span data-stu-id="25f8b-176">Describing the security requirements for methods.</span></span>
- <span data-ttu-id="25f8b-177">Definizione delle caratteristiche usate per garantire la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="25f8b-177">Specifying characteristics used to enforce security.</span></span>
- <span data-ttu-id="25f8b-178">Controllo delle ottimizzazioni tramite il compilatore JIT (Just-In-Time), in modo da garantire un semplice debug del codice.</span><span class="sxs-lookup"><span data-stu-id="25f8b-178">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>
- <span data-ttu-id="25f8b-179">Recupero di informazioni relative al chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="25f8b-179">Obtaining information about the caller to a method.</span></span>

## <a name="related-sections"></a><span data-ttu-id="25f8b-180">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="25f8b-180">Related sections</span></span>

<span data-ttu-id="25f8b-181">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="25f8b-181">For more information, see:</span></span>

- [<span data-ttu-id="25f8b-182">Creazione di attributi personalizzati (C#)</span><span class="sxs-lookup"><span data-stu-id="25f8b-182">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)  
- <span data-ttu-id="25f8b-183">[Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md) (Accesso agli attributi con reflection (C#))</span><span class="sxs-lookup"><span data-stu-id="25f8b-183">[Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md)</span></span>  
- [<span data-ttu-id="25f8b-184">Come creare un'Unione C/C++ usando gli attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="25f8b-184">How to create a C/C++ union by using attributes (C#)</span></span>](how-to-create-a-c-cpp-union-by-using-attributes.md)  
- [<span data-ttu-id="25f8b-185">Attributi comuni (C#)</span><span class="sxs-lookup"><span data-stu-id="25f8b-185">Common Attributes (C#)</span></span>](../../../language-reference/attributes/global.md)  
- [<span data-ttu-id="25f8b-186">Informazioni sul chiamante (C#)</span><span class="sxs-lookup"><span data-stu-id="25f8b-186">Caller Information (C#)</span></span>](../../../language-reference/attributes/caller-information.md)  

## <a name="see-also"></a><span data-ttu-id="25f8b-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25f8b-187">See also</span></span>

- [<span data-ttu-id="25f8b-188">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="25f8b-188">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="25f8b-189">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="25f8b-189">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="25f8b-190">Attributes (Attributi)</span><span class="sxs-lookup"><span data-stu-id="25f8b-190">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="25f8b-191">Uso degli attributi in C#</span><span class="sxs-lookup"><span data-stu-id="25f8b-191">Using Attributes in C#</span></span>](../../../tutorials/attributes.md)
