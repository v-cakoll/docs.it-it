---
title: Attributi (C#)
ms.date: 04/26/2018
ms.openlocfilehash: 2a07035ea97bb0ff1a8f4793fe8a30d3a42c34a7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79399749"
---
# <a name="attributes-c"></a><span data-ttu-id="32a4e-102">Attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="32a4e-102">Attributes (C#)</span></span>

<span data-ttu-id="32a4e-103">Gli attributi offrono un metodo efficace per l'associazione di metadati o informazioni dichiarative con il codice (assembly, tipi, metodi, proprietà e così via).</span><span class="sxs-lookup"><span data-stu-id="32a4e-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="32a4e-104">Dopo aver associato un attributo a un'entità di programma, in fase di esecuzione è possibile eseguire una query su tale attributo usando una tecnica denominata *reflection*.</span><span class="sxs-lookup"><span data-stu-id="32a4e-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="32a4e-105">Per altre informazioni, vedere [Reflection (C#)](../reflection.md).</span><span class="sxs-lookup"><span data-stu-id="32a4e-105">For more information, see [Reflection (C#)](../reflection.md).</span></span>

<span data-ttu-id="32a4e-106">Di seguito sono riportate le proprietà degli attributi:</span><span class="sxs-lookup"><span data-stu-id="32a4e-106">Attributes have the following properties:</span></span>

- <span data-ttu-id="32a4e-107">Gli attributi aggiungono metadati al programma.</span><span class="sxs-lookup"><span data-stu-id="32a4e-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="32a4e-108">I *metadati* sono informazioni relative ai tipi definiti in un programma.</span><span class="sxs-lookup"><span data-stu-id="32a4e-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="32a4e-109">Tutti gli assembly .NET contengono un set specificato di metadati che descrive i tipi e membri dei tipi definiti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="32a4e-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="32a4e-110">È possibile aggiungere attributi personalizzati per specificare altre informazioni eventualmente necessarie.</span><span class="sxs-lookup"><span data-stu-id="32a4e-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="32a4e-111">Per altre informazioni, vedere [Creazione di attributi personalizzati (C#)](creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="32a4e-111">For more information, see, [Creating Custom Attributes (C#)](creating-custom-attributes.md).</span></span>
- <span data-ttu-id="32a4e-112">È possibile applicare uno o più attributi a interi assembly, moduli o elementi di programma di minori dimensioni, ad esempio classi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="32a4e-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>
- <span data-ttu-id="32a4e-113">Gli attributi possono accettare argomenti nello stesso modo dei metodi e delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="32a4e-113">Attributes can accept arguments in the same way as methods and properties.</span></span>
- <span data-ttu-id="32a4e-114">Il programma può esaminare i propri metadati oppure i metadati di un altro programma tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="32a4e-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="32a4e-115">Per altre informazioni, vedere [Accesso agli attributi tramite reflection (C#)](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="32a4e-115">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="using-attributes"></a><span data-ttu-id="32a4e-116">Utilizzo di attributi</span><span class="sxs-lookup"><span data-stu-id="32a4e-116">Using attributes</span></span>

<span data-ttu-id="32a4e-117">È possibile usare attributi nella maggior parte delle dichiarazioni, anche se la validità di un attributo specifico può essere limitata ad alcuni tipi di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="32a4e-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="32a4e-118">Per specificare un attributo in C# inserire il nome dell'attributo racchiuso tra parentesi quadre ([]) sopra la dichiarazione dell'entità a cui è applicato.</span><span class="sxs-lookup"><span data-stu-id="32a4e-118">In C#, you specify an attribute by placing the name of the attribute enclosed in square brackets ([]) above the declaration of the entity to which it applies.</span></span>

<span data-ttu-id="32a4e-119">Nell'esempio seguente l'attributo <xref:System.SerializableAttribute> viene usato per applicare una caratteristica specifica a una classe:</span><span class="sxs-lookup"><span data-stu-id="32a4e-119">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>

[!code-csharp[Using the serializable attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#1)]

<span data-ttu-id="32a4e-120">Un metodo con l'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> è dichiarato come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="32a4e-120">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like the following example:</span></span>

[!code-csharp[Declaring a method to import from an external library](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#2)]

<span data-ttu-id="32a4e-121">In una dichiarazione è possibile inserire più attributi, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="32a4e-121">More than one attribute can be placed on a declaration as the following example shows:</span></span>

[!code-csharp[Including the interop namespace](~/samples/snippets/csharp/attributes/AttributesOverview.cs#3)]
[!code-csharp[Declaring two way marshaling for arguments](~/samples/snippets/csharp/attributes/AttributesOverview.cs#4)]

<span data-ttu-id="32a4e-122">Alcuni attributi possono essere specificati più volte per una stessa entità.</span><span class="sxs-lookup"><span data-stu-id="32a4e-122">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="32a4e-123">Un esempio di attributo multiuso è <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="32a4e-123">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>

[!code-csharp[Using the conditional attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#5)]

> [!NOTE]
> <span data-ttu-id="32a4e-124">Per convenzione tutti i nomi di attributo terminano con la parola "Attribute", in modo che sia possibile distinguerli da altri elementi delle librerie .NET.</span><span class="sxs-lookup"><span data-stu-id="32a4e-124">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET libraries.</span></span> <span data-ttu-id="32a4e-125">Tuttavia, quando gli attributi vengono usati nel codice, non è necessario specificare il suffisso Attribute.</span><span class="sxs-lookup"><span data-stu-id="32a4e-125">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="32a4e-126">Ad esempio `[DllImport]` è equivalente a `[DllImportAttribute]`, mentre `DllImportAttribute` è il nome effettivo dell'attributo nella libreria di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="32a4e-126">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework Class Library.</span></span>

### <a name="attribute-parameters"></a><span data-ttu-id="32a4e-127">Parametri degli attributi</span><span class="sxs-lookup"><span data-stu-id="32a4e-127">Attribute parameters</span></span>

<span data-ttu-id="32a4e-128">Diversi attributi dispongono di parametri, che possono essere posizionali, senza nome o denominati.</span><span class="sxs-lookup"><span data-stu-id="32a4e-128">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="32a4e-129">I parametri posizionali devono essere specificati in un determinato ordine e non possono essere omessi.</span><span class="sxs-lookup"><span data-stu-id="32a4e-129">Any positional parameters must be specified in a certain order and cannot be omitted.</span></span> <span data-ttu-id="32a4e-130">I parametri denominati sono facoltativi e possono essere specificati in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="32a4e-130">Named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="32a4e-131">I parametri posizionali vengono specificati per primi.</span><span class="sxs-lookup"><span data-stu-id="32a4e-131">Positional parameters are specified first.</span></span> <span data-ttu-id="32a4e-132">I tre attributi seguenti, ad esempio, sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="32a4e-132">For example, these three attributes are equivalent:</span></span>

```csharp
[DllImport("user32.dll")]
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]
```

<span data-ttu-id="32a4e-133">Il primo parametro, ovvero il nome della DLL, è posizionale ed è sempre specificato per primo. Gli altri parametri sono denominati.</span><span class="sxs-lookup"><span data-stu-id="32a4e-133">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="32a4e-134">In questo caso, entrambi i parametri denominati sono impostati automaticamente su false e possono quindi essere omessi.</span><span class="sxs-lookup"><span data-stu-id="32a4e-134">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="32a4e-135">I parametri posizionali corrispondono ai parametri del costruttore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="32a4e-135">Positional parameters correspond to the parameters of the attribute constructor.</span></span> <span data-ttu-id="32a4e-136">I parametri denominati o facoltativi corrispondono a proprietà o campi dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="32a4e-136">Named or optional parameters correspond to either properties or fields of the attribute.</span></span> <span data-ttu-id="32a4e-137">Per informazioni sui valori predefiniti dei parametri, fare riferimento alla documentazione di ciascun attributo.</span><span class="sxs-lookup"><span data-stu-id="32a4e-137">Refer to the individual attribute's documentation for information on default parameter values.</span></span>

### <a name="attribute-targets"></a><span data-ttu-id="32a4e-138">Destinazioni degli attributi</span><span class="sxs-lookup"><span data-stu-id="32a4e-138">Attribute targets</span></span>

<span data-ttu-id="32a4e-139">La *destinazione* di un attributo è l'entità a cui tale attributo viene applicato.</span><span class="sxs-lookup"><span data-stu-id="32a4e-139">The *target* of an attribute is the entity which the attribute applies to.</span></span> <span data-ttu-id="32a4e-140">Un attributo, ad esempio, può essere applicato a una classe, a un metodo particolare o a un intero assembly.</span><span class="sxs-lookup"><span data-stu-id="32a4e-140">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="32a4e-141">Per impostazione predefinita, un attributo si applica all'elemento che lo segue.</span><span class="sxs-lookup"><span data-stu-id="32a4e-141">By default, an attribute applies to the element that follows it.</span></span> <span data-ttu-id="32a4e-142">È tuttavia possibile identificare in modo esplicito, ad esempio, se un attributo viene applicato a un metodo, al relativo parametro o al relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="32a4e-142">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>

<span data-ttu-id="32a4e-143">Per identificare in modo esplicito la destinazione di un attributo, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="32a4e-143">To explicitly identify an attribute target, use the following syntax:</span></span>

```csharp
[target : attribute-list]
```

<span data-ttu-id="32a4e-144">Nella tabella seguente sono elencati i possibili valori di `target`.</span><span class="sxs-lookup"><span data-stu-id="32a4e-144">The list of possible `target` values is shown in the following table.</span></span>

|<span data-ttu-id="32a4e-145">Valore di destinazione</span><span class="sxs-lookup"><span data-stu-id="32a4e-145">Target value</span></span>|<span data-ttu-id="32a4e-146">Si applica a</span><span class="sxs-lookup"><span data-stu-id="32a4e-146">Applies to</span></span>|
|------------------|----------------|
|`assembly`|<span data-ttu-id="32a4e-147">Intero assembly</span><span class="sxs-lookup"><span data-stu-id="32a4e-147">Entire assembly</span></span>|
|`module`|<span data-ttu-id="32a4e-148">Modulo di assembly corrente</span><span class="sxs-lookup"><span data-stu-id="32a4e-148">Current assembly module</span></span>|
|`field`|<span data-ttu-id="32a4e-149">Campo in una classe o uno struct</span><span class="sxs-lookup"><span data-stu-id="32a4e-149">Field in a class or a struct</span></span>|
|`event`|<span data-ttu-id="32a4e-150">Event</span><span class="sxs-lookup"><span data-stu-id="32a4e-150">Event</span></span>|
|`method`|<span data-ttu-id="32a4e-151">Metodo o funzioni di accesso alle proprietà `get` e `set`</span><span class="sxs-lookup"><span data-stu-id="32a4e-151">Method or `get` and `set` property accessors</span></span>|
|`param`|<span data-ttu-id="32a4e-152">Parametri del metodo o parametri della funzione di accesso alla proprietà `set`</span><span class="sxs-lookup"><span data-stu-id="32a4e-152">Method parameters or `set` property accessor parameters</span></span>|
|`property`|<span data-ttu-id="32a4e-153">Proprietà</span><span class="sxs-lookup"><span data-stu-id="32a4e-153">Property</span></span>|
|`return`|<span data-ttu-id="32a4e-154">Valore restituito di un metodo, un indicizzatore di proprietà o una funzione di accesso alla proprietà `get`</span><span class="sxs-lookup"><span data-stu-id="32a4e-154">Return value of a method, property indexer, or `get` property accessor</span></span>|
|`type`|<span data-ttu-id="32a4e-155">Struct, classe, interfaccia, enumeratore o delegato</span><span class="sxs-lookup"><span data-stu-id="32a4e-155">Struct, class, interface, enum, or delegate</span></span>|

<span data-ttu-id="32a4e-156">È necessario specificare il valore di destinazione `field` per applicare un attributo al campo sottostante creato per una [proprietà implementata automaticamente](../../../properties.md).</span><span class="sxs-lookup"><span data-stu-id="32a4e-156">You would specify the `field` target value to apply an attribute to the backing field created for an [auto-implemented property](../../../properties.md).</span></span>

<span data-ttu-id="32a4e-157">Nell'esempio seguente viene illustrato come applicare attributi ad assembly e moduli.</span><span class="sxs-lookup"><span data-stu-id="32a4e-157">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="32a4e-158">Per altre informazioni, vedere [Attributi comuni (C#)](common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="32a4e-158">For more information, see [Common Attributes (C#)](common-attributes.md).</span></span>

```csharp
using System;
using System.Reflection;
[assembly: AssemblyTitleAttribute("Production assembly 4")]
[module: CLSCompliant(true)]
```

<span data-ttu-id="32a4e-159">Nell'esempio seguente viene illustrato come applicare gli attributi a metodi, parametri di metodo e valori restituiti dal metodo in C#.</span><span class="sxs-lookup"><span data-stu-id="32a4e-159">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>

[!code-csharp[Applying attributes to different code elements](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#6)]

> [!NOTE]
> <span data-ttu-id="32a4e-160">Indipendentemente dalle destinazioni in cui l'oggetto `ValidatedContract` è definito come valido, è necessario specificare la destinazione `return`, anche se `ValidatedContract` viene definito in modo da essere valido solo per i valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="32a4e-160">Regardless of the targets on which `ValidatedContract` is defined to be valid, the `return` target has to be specified, even if `ValidatedContract` were defined to apply only to return values.</span></span> <span data-ttu-id="32a4e-161">In altre parole, il compilatore non usa le informazioni `AttributeUsage` per risolvere le destinazioni degli attributi ambigue.</span><span class="sxs-lookup"><span data-stu-id="32a4e-161">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="32a4e-162">Per altre informazioni, vedere [AttributeUsage (C#)](attributeusage.md).</span><span class="sxs-lookup"><span data-stu-id="32a4e-162">For more information, see [AttributeUsage (C#)](attributeusage.md).</span></span>

## <a name="common-uses-for-attributes"></a><span data-ttu-id="32a4e-163">Usi comuni degli attributi</span><span class="sxs-lookup"><span data-stu-id="32a4e-163">Common uses for attributes</span></span>

<span data-ttu-id="32a4e-164">Di seguito vengono elencati alcuni degli usi comuni degli attributi nel codice:</span><span class="sxs-lookup"><span data-stu-id="32a4e-164">The following list includes a few of the common uses of attributes in code:</span></span>

- <span data-ttu-id="32a4e-165">Contrassegno dei metodi mediante l'attributo `WebMethod` nei servizi Web per indicare che è possibile chiamare il metodo tramite il protocollo SOAP.</span><span class="sxs-lookup"><span data-stu-id="32a4e-165">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="32a4e-166">Per altre informazioni, vedere <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="32a4e-166">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>
- <span data-ttu-id="32a4e-167">Descrizione della procedura di marshalling dei parametri del metodo durante l'interazione con il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="32a4e-167">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="32a4e-168">Per altre informazioni, vedere <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="32a4e-168">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>
- <span data-ttu-id="32a4e-169">Descrizione delle proprietà COM per classi, metodi e interfacce.</span><span class="sxs-lookup"><span data-stu-id="32a4e-169">Describing the COM properties for classes, methods, and interfaces.</span></span>
- <span data-ttu-id="32a4e-170">Chiamata al codice non gestito che usa la classe <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="32a4e-170">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>
- <span data-ttu-id="32a4e-171">Descrizione dell'assembly con indicazione di titolo, versione, descrizione o marchio.</span><span class="sxs-lookup"><span data-stu-id="32a4e-171">Describing your assembly in terms of title, version, description, or trademark.</span></span>
- <span data-ttu-id="32a4e-172">Descrizione dei membri della classe da serializzare per la persistenza.</span><span class="sxs-lookup"><span data-stu-id="32a4e-172">Describing which members of a class to serialize for persistence.</span></span>
- <span data-ttu-id="32a4e-173">Descrizione della procedura di mapping tra membri di una classe e nodi XML per la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="32a4e-173">Describing how to map between class members and XML nodes for XML serialization.</span></span>
- <span data-ttu-id="32a4e-174">Descrizione dei requisiti di sicurezza per i metodi.</span><span class="sxs-lookup"><span data-stu-id="32a4e-174">Describing the security requirements for methods.</span></span>
- <span data-ttu-id="32a4e-175">Definizione delle caratteristiche usate per garantire la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="32a4e-175">Specifying characteristics used to enforce security.</span></span>
- <span data-ttu-id="32a4e-176">Controllo delle ottimizzazioni tramite il compilatore JIT (Just-In-Time), in modo da garantire un semplice debug del codice.</span><span class="sxs-lookup"><span data-stu-id="32a4e-176">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>
- <span data-ttu-id="32a4e-177">Recupero di informazioni relative al chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="32a4e-177">Obtaining information about the caller to a method.</span></span>

## <a name="related-sections"></a><span data-ttu-id="32a4e-178">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="32a4e-178">Related sections</span></span>

<span data-ttu-id="32a4e-179">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="32a4e-179">For more information, see:</span></span>

- [<span data-ttu-id="32a4e-180">Creazione di attributi personalizzati (C#)</span><span class="sxs-lookup"><span data-stu-id="32a4e-180">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)  
- <span data-ttu-id="32a4e-181">[Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md) (Accesso agli attributi con reflection (C#))</span><span class="sxs-lookup"><span data-stu-id="32a4e-181">[Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md)</span></span>  
- [<span data-ttu-id="32a4e-182">Come creare un'unione C/C</span><span class="sxs-lookup"><span data-stu-id="32a4e-182">How to create a C/C++ union by using attributes (C#)</span></span>](how-to-create-a-c-cpp-union-by-using-attributes.md)  
- [<span data-ttu-id="32a4e-183">Attributi comuni (C#)</span><span class="sxs-lookup"><span data-stu-id="32a4e-183">Common Attributes (C#)</span></span>](common-attributes.md)  
- [<span data-ttu-id="32a4e-184">Informazioni sul chiamante (C#)</span><span class="sxs-lookup"><span data-stu-id="32a4e-184">Caller Information (C#)</span></span>](../caller-information.md)  

## <a name="see-also"></a><span data-ttu-id="32a4e-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32a4e-185">See also</span></span>

- [<span data-ttu-id="32a4e-186">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="32a4e-186">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="32a4e-187">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="32a4e-187">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="32a4e-188">Attributi</span><span class="sxs-lookup"><span data-stu-id="32a4e-188">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="32a4e-189">Uso degli attributi in C#</span><span class="sxs-lookup"><span data-stu-id="32a4e-189">Using Attributes in C#</span></span>](../../../tutorials/attributes.md)
