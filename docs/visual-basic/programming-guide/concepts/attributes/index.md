---
title: Panoramica degli attributi
ms.date: 07/20/2015
ms.assetid: 1449f69b-c063-41de-8d89-f0bbdcf96ac6
ms.openlocfilehash: a0a080d44796289cc3562803c84ec915dcedd314
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400707"
---
# <a name="attributes-overview-visual-basic"></a><span data-ttu-id="b62ff-102">Panoramica degli attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b62ff-102">Attributes overview (Visual Basic)</span></span>

<span data-ttu-id="b62ff-103">Gli attributi offrono un metodo efficace per l'associazione di metadati o informazioni dichiarative con il codice (assembly, tipi, metodi, proprietà e così via).</span><span class="sxs-lookup"><span data-stu-id="b62ff-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="b62ff-104">Dopo aver associato un attributo a un'entità di programma, in fase di esecuzione è possibile eseguire una query su tale attributo usando una tecnica denominata *reflection*.</span><span class="sxs-lookup"><span data-stu-id="b62ff-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="b62ff-105">Per altre informazioni, vedere [Reflection (Visual Basic)](../reflection.md).</span><span class="sxs-lookup"><span data-stu-id="b62ff-105">For more information, see [Reflection (Visual Basic)](../reflection.md).</span></span>

<span data-ttu-id="b62ff-106">Di seguito sono riportate le proprietà degli attributi:</span><span class="sxs-lookup"><span data-stu-id="b62ff-106">Attributes have the following properties:</span></span>

- <span data-ttu-id="b62ff-107">Gli attributi aggiungono metadati al programma.</span><span class="sxs-lookup"><span data-stu-id="b62ff-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="b62ff-108">I *metadati* sono informazioni relative ai tipi definiti in un programma.</span><span class="sxs-lookup"><span data-stu-id="b62ff-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="b62ff-109">Tutti gli assembly .NET contengono un set specificato di metadati che descrive i tipi e membri dei tipi definiti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b62ff-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="b62ff-110">È possibile aggiungere attributi personalizzati per specificare altre informazioni eventualmente necessarie.</span><span class="sxs-lookup"><span data-stu-id="b62ff-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="b62ff-111">Per altre informazioni, vedere [Creazione di attributi personalizzati (Visual Basic)](creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b62ff-111">For more information, see, [Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md).</span></span>

- <span data-ttu-id="b62ff-112">È possibile applicare uno o più attributi a interi assembly, moduli o elementi di programma di minori dimensioni, ad esempio classi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="b62ff-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>

- <span data-ttu-id="b62ff-113">Gli attributi possono accettare argomenti nello stesso modo dei metodi e delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b62ff-113">Attributes can accept arguments in the same way as methods and properties.</span></span>

- <span data-ttu-id="b62ff-114">Il programma può esaminare i propri metadati oppure i metadati di un altro programma tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="b62ff-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="b62ff-115">Per altre informazioni, vedere [Accesso agli attributi tramite reflection (Visual Basic)](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="b62ff-115">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="using-attributes"></a><span data-ttu-id="b62ff-116">Uso degli attributi</span><span class="sxs-lookup"><span data-stu-id="b62ff-116">Using Attributes</span></span>

<span data-ttu-id="b62ff-117">È possibile usare attributi nella maggior parte delle dichiarazioni, anche se la validità di un attributo specifico può essere limitata ad alcuni tipi di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="b62ff-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="b62ff-118">In Visual Basic, un attributo è racchiuso tra parentesi acute ( \< > ).</span><span class="sxs-lookup"><span data-stu-id="b62ff-118">In Visual Basic, an attribute is enclosed in angle brackets (\< >).</span></span> <span data-ttu-id="b62ff-119">e deve apparire immediatamente prima dell'elemento a cui viene applicato, sulla stessa riga.</span><span class="sxs-lookup"><span data-stu-id="b62ff-119">It must appear immediately before the element to which it is applied, on the same line.</span></span>

<span data-ttu-id="b62ff-120">Nell'esempio seguente l'attributo <xref:System.SerializableAttribute> viene usato per applicare una caratteristica specifica a una classe:</span><span class="sxs-lookup"><span data-stu-id="b62ff-120">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>

```vb
<System.Serializable()> Public Class SampleClass
    ' Objects of this type can be serialized.
End Class
```

 <span data-ttu-id="b62ff-121">Un metodo con l'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> è dichiarato come segue:</span><span class="sxs-lookup"><span data-stu-id="b62ff-121">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>

```vb
Imports System.Runtime.InteropServices
```

```vb
<System.Runtime.InteropServices.DllImport("user32.dll")>
Sub SampleMethod()
End Sub
```

<span data-ttu-id="b62ff-122">In una dichiarazione è possibile inserire più attributi:</span><span class="sxs-lookup"><span data-stu-id="b62ff-122">More than one attribute can be placed on a declaration:</span></span>

```vb
Imports System.Runtime.InteropServices
```

```vb
Sub MethodA(<[In](), Out()> ByVal x As Double)
End Sub
Sub MethodB(<Out(), [In]()> ByVal x As Double)
End Sub
```

<span data-ttu-id="b62ff-123">Alcuni attributi possono essere specificati più volte per una stessa entità.</span><span class="sxs-lookup"><span data-stu-id="b62ff-123">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="b62ff-124">Un esempio di attributo multiuso è <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="b62ff-124">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>

```vb
<Conditional("DEBUG"), Conditional("TEST1")>
Sub TraceMethod()
End Sub
```

> [!NOTE]
> <span data-ttu-id="b62ff-125">Per convenzione tutti i nomi di attributo terminano con la parola "Attribute", in modo che sia possibile distinguerli da altri elementi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b62ff-125">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="b62ff-126">Tuttavia, quando gli attributi vengono usati nel codice, non è necessario specificare il suffisso Attribute.</span><span class="sxs-lookup"><span data-stu-id="b62ff-126">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="b62ff-127">Ad esempio, `[DllImport]` è equivalente a `[DllImportAttribute]`, mentre `DllImportAttribute` è il nome effettivo dell'attributo in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b62ff-127">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>

### <a name="attribute-parameters"></a><span data-ttu-id="b62ff-128">Parametri degli attributi</span><span class="sxs-lookup"><span data-stu-id="b62ff-128">Attribute Parameters</span></span>

<span data-ttu-id="b62ff-129">Diversi attributi dispongono di parametri, che possono essere posizionali, senza nome o denominati.</span><span class="sxs-lookup"><span data-stu-id="b62ff-129">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="b62ff-130">I parametri posizionali devono essere specificati in un determinato ordine e non possono essere omessi. I parametri denominati sono invece facoltativi e possono essere specificati in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="b62ff-130">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="b62ff-131">I parametri posizionali vengono specificati per primi.</span><span class="sxs-lookup"><span data-stu-id="b62ff-131">Positional parameters are specified first.</span></span> <span data-ttu-id="b62ff-132">I tre attributi seguenti, ad esempio, sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="b62ff-132">For example, these three attributes are equivalent:</span></span>

```vb
<DllImport("user32.dll")>
<DllImport("user32.dll", SetLastError:=False, ExactSpelling:=False)>
<DllImport("user32.dll", ExactSpelling:=False, SetLastError:=False)>
```

<span data-ttu-id="b62ff-133">Il primo parametro, ovvero il nome della DLL, è posizionale ed è sempre specificato per primo. Gli altri parametri sono denominati.</span><span class="sxs-lookup"><span data-stu-id="b62ff-133">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="b62ff-134">In questo caso, entrambi i parametri denominati sono impostati automaticamente su false e possono quindi essere omessi.</span><span class="sxs-lookup"><span data-stu-id="b62ff-134">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="b62ff-135">Per informazioni sui valori predefiniti dei parametri, fare riferimento alla documentazione di ciascun attributo.</span><span class="sxs-lookup"><span data-stu-id="b62ff-135">Refer to the individual attribute's documentation for information on default parameter values.</span></span>

### <a name="attribute-targets"></a><span data-ttu-id="b62ff-136">Destinazioni degli attributi</span><span class="sxs-lookup"><span data-stu-id="b62ff-136">Attribute Targets</span></span>

<span data-ttu-id="b62ff-137">La *destinazione* di un attributo è l'entità a cui tale attributo viene applicato.</span><span class="sxs-lookup"><span data-stu-id="b62ff-137">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="b62ff-138">Un attributo, ad esempio, può essere applicato a una classe, a un metodo particolare o a un intero assembly.</span><span class="sxs-lookup"><span data-stu-id="b62ff-138">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="b62ff-139">Per impostazione predefinita, un attributo viene applicato all'elemento che lo segue.</span><span class="sxs-lookup"><span data-stu-id="b62ff-139">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="b62ff-140">È tuttavia possibile identificare in modo esplicito, ad esempio, se un attributo viene applicato a un metodo, al relativo parametro o al relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="b62ff-140">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>

<span data-ttu-id="b62ff-141">Per identificare in modo esplicito la destinazione di un attributo, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b62ff-141">To explicitly identify an attribute target, use the following syntax:</span></span>

```vb
<target : attribute-list>
```

<span data-ttu-id="b62ff-142">Nella tabella seguente sono elencati i possibili valori di `target`.</span><span class="sxs-lookup"><span data-stu-id="b62ff-142">The list of possible `target` values is shown in the following table.</span></span>

|<span data-ttu-id="b62ff-143">Valore di destinazione</span><span class="sxs-lookup"><span data-stu-id="b62ff-143">Target value</span></span>|<span data-ttu-id="b62ff-144">Si applica a</span><span class="sxs-lookup"><span data-stu-id="b62ff-144">Applies to</span></span>|
|------------------|----------------|
|`assembly`|<span data-ttu-id="b62ff-145">Intero assembly</span><span class="sxs-lookup"><span data-stu-id="b62ff-145">Entire assembly</span></span>|
|`module`|<span data-ttu-id="b62ff-146">Modulo dell'assembly corrente (diverso da un modulo di Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b62ff-146">Current assembly module (which is different from a Visual Basic Module)</span></span>|

 <span data-ttu-id="b62ff-147">Nell'esempio seguente viene illustrato come applicare attributi ad assembly e moduli.</span><span class="sxs-lookup"><span data-stu-id="b62ff-147">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="b62ff-148">Per altre informazioni, vedere [Attributi comuni (Visual Basic)](common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b62ff-148">For more information, see [Common Attributes (Visual Basic)](common-attributes.md).</span></span>

```vb
Imports System.Reflection
<Assembly: AssemblyTitleAttribute("Production assembly 4"),
Module: CLSCompliant(True)>
```

## <a name="common-uses-for-attributes"></a><span data-ttu-id="b62ff-149">Usi comuni degli attributi</span><span class="sxs-lookup"><span data-stu-id="b62ff-149">Common Uses for Attributes</span></span>

<span data-ttu-id="b62ff-150">Di seguito vengono elencati alcuni degli usi comuni degli attributi nel codice:</span><span class="sxs-lookup"><span data-stu-id="b62ff-150">The following list includes a few of the common uses of attributes in code:</span></span>

- <span data-ttu-id="b62ff-151">Contrassegno dei metodi mediante l'attributo `WebMethod` nei servizi Web per indicare che è possibile chiamare il metodo tramite il protocollo SOAP.</span><span class="sxs-lookup"><span data-stu-id="b62ff-151">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="b62ff-152">Per altre informazioni, vedere <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b62ff-152">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>

- <span data-ttu-id="b62ff-153">Descrizione della procedura di marshalling dei parametri del metodo durante l'interazione con il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="b62ff-153">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="b62ff-154">Per altre informazioni, vedere <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b62ff-154">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>

- <span data-ttu-id="b62ff-155">Descrizione delle proprietà COM per classi, metodi e interfacce.</span><span class="sxs-lookup"><span data-stu-id="b62ff-155">Describing the COM properties for classes, methods, and interfaces.</span></span>

- <span data-ttu-id="b62ff-156">Chiamata al codice non gestito che usa la classe <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b62ff-156">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>

- <span data-ttu-id="b62ff-157">Descrizione dell'assembly con indicazione di titolo, versione, descrizione o marchio.</span><span class="sxs-lookup"><span data-stu-id="b62ff-157">Describing your assembly in terms of title, version, description, or trademark.</span></span>

- <span data-ttu-id="b62ff-158">Descrizione dei membri della classe da serializzare per la persistenza.</span><span class="sxs-lookup"><span data-stu-id="b62ff-158">Describing which members of a class to serialize for persistence.</span></span>

- <span data-ttu-id="b62ff-159">Descrizione della procedura di mapping tra membri di una classe e nodi XML per la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="b62ff-159">Describing how to map between class members and XML nodes for XML serialization.</span></span>

- <span data-ttu-id="b62ff-160">Descrizione dei requisiti di sicurezza per i metodi.</span><span class="sxs-lookup"><span data-stu-id="b62ff-160">Describing the security requirements for methods.</span></span>

- <span data-ttu-id="b62ff-161">Definizione delle caratteristiche usate per garantire la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b62ff-161">Specifying characteristics used to enforce security.</span></span>

- <span data-ttu-id="b62ff-162">Controllo delle ottimizzazioni tramite il compilatore JIT (Just-In-Time), in modo da garantire un semplice debug del codice.</span><span class="sxs-lookup"><span data-stu-id="b62ff-162">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>

- <span data-ttu-id="b62ff-163">Recupero di informazioni relative al chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="b62ff-163">Obtaining information about the caller to a method.</span></span>

## <a name="related-sections"></a><span data-ttu-id="b62ff-164">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="b62ff-164">Related Sections</span></span>

<span data-ttu-id="b62ff-165">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="b62ff-165">For more information, see:</span></span>

- [<span data-ttu-id="b62ff-166">Creazione di attributi personalizzati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b62ff-166">Creating Custom Attributes (Visual Basic)</span></span>](creating-custom-attributes.md)

- [<span data-ttu-id="b62ff-167">Accesso agli attributi tramite reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b62ff-167">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](accessing-attributes-by-using-reflection.md)

- [<span data-ttu-id="b62ff-168">Procedura: Creare un'unione C/C++ tramite attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b62ff-168">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>](how-to-create-a-c-cpp-union-by-using-attributes.md)

- [<span data-ttu-id="b62ff-169">Attributi comuni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b62ff-169">Common Attributes (Visual Basic)</span></span>](common-attributes.md)

- [<span data-ttu-id="b62ff-170">Informazioni sul chiamante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b62ff-170">Caller Information (Visual Basic)</span></span>](../caller-information.md)

## <a name="see-also"></a><span data-ttu-id="b62ff-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b62ff-171">See also</span></span>

- [<span data-ttu-id="b62ff-172">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b62ff-172">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="b62ff-173">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b62ff-173">Reflection (Visual Basic)</span></span>](../reflection.md)
- [<span data-ttu-id="b62ff-174">Attributi</span><span class="sxs-lookup"><span data-stu-id="b62ff-174">Attributes</span></span>](../../../../standard/attributes/index.md)
