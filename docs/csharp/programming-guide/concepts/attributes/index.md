---
title: Attributi (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f148f13f-a0d5-4f22-9c87-4b73d5dde270
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f9fc23cf7afbd28f0c9ae438cbce298cbf362fbd
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="attributes-c"></a><span data-ttu-id="ad0b9-102">Attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="ad0b9-102">Attributes (C#)</span></span>
<span data-ttu-id="ad0b9-103">Gli attributi offrono un metodo efficace per l'associazione di metadati o informazioni dichiarative con il codice (assembly, tipi, metodi, proprietà e così via).</span><span class="sxs-lookup"><span data-stu-id="ad0b9-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="ad0b9-104">Dopo aver associato un attributo a un'entità di programma, in fase di esecuzione è possibile eseguire una query su tale attributo usando una tecnica denominata *reflection*.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="ad0b9-105">Per altre informazioni, vedere [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md).</span><span class="sxs-lookup"><span data-stu-id="ad0b9-105">For more information, see [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md).</span></span>  
  
 <span data-ttu-id="ad0b9-106">Di seguito sono riportate le proprietà degli attributi:</span><span class="sxs-lookup"><span data-stu-id="ad0b9-106">Attributes have the following properties:</span></span>  
  
-   <span data-ttu-id="ad0b9-107">Gli attributi aggiungono metadati al programma.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="ad0b9-108">I *metadati* sono informazioni relative ai tipi definiti in un programma.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="ad0b9-109">Tutti gli assembly .NET contengono un set specificato di metadati che descrive i tipi e membri dei tipi definiti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="ad0b9-110">È possibile aggiungere attributi personalizzati per specificare altre informazioni eventualmente necessarie.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="ad0b9-111">Per altre informazioni, vedere [Creazione di attributi personalizzati (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ad0b9-111">For more information, see, [Creating Custom Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>  
  
-   <span data-ttu-id="ad0b9-112">È possibile applicare uno o più attributi a interi assembly, moduli o elementi di programma di minori dimensioni, ad esempio classi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>  
  
-   <span data-ttu-id="ad0b9-113">Gli attributi possono accettare argomenti nello stesso modo dei metodi e delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-113">Attributes can accept arguments in the same way as methods and properties.</span></span>  
  
-   <span data-ttu-id="ad0b9-114">Il programma può esaminare i propri metadati oppure i metadati di un altro programma tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="ad0b9-115">Per altre informazioni, vedere [Accesso agli attributi tramite reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="ad0b9-115">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="using-attributes"></a><span data-ttu-id="ad0b9-116">Uso degli attributi</span><span class="sxs-lookup"><span data-stu-id="ad0b9-116">Using Attributes</span></span>  
 <span data-ttu-id="ad0b9-117">È possibile usare attributi nella maggior parte delle dichiarazioni, anche se la validità di un attributo specifico può essere limitata ad alcuni tipi di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="ad0b9-118">Per specificare un attributo in C#, inserire il nome dell'attributo, racchiuso tra parentesi quadre ([]), sopra la dichiarazione dell'entità a cui è applicato.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-118">In C#, you specify an attribute by placing the name of the attribute, enclosed in square brackets ([]), above the declaration of the entity to which it applies.</span></span>  
  
 <span data-ttu-id="ad0b9-119">Nell'esempio seguente l'attributo <xref:System.SerializableAttribute> viene usato per applicare una caratteristica specifica a una classe:</span><span class="sxs-lookup"><span data-stu-id="ad0b9-119">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>  
  
```csharp  
[System.Serializable]  
public class SampleClass  
{  
    // Objects of this type can be serialized.  
}  
```  
  
 <span data-ttu-id="ad0b9-120">Un metodo con l'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> è dichiarato come segue:</span><span class="sxs-lookup"><span data-stu-id="ad0b9-120">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
[System.Runtime.InteropServices.DllImport("user32.dll")]  
extern static void SampleMethod();  
```  
  
 <span data-ttu-id="ad0b9-121">In una dichiarazione è possibile inserire più attributi:</span><span class="sxs-lookup"><span data-stu-id="ad0b9-121">More than one attribute can be placed on a declaration:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
void MethodA([In][Out] ref double x) { }  
void MethodB([Out][In] ref double x) { }  
void MethodC([In, Out] ref double x) { }  
```  
  
 <span data-ttu-id="ad0b9-122">Alcuni attributi possono essere specificati più volte per una stessa entità.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-122">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="ad0b9-123">Un esempio di attributo multiuso è <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="ad0b9-123">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>  
  
```csharp  
[Conditional("DEBUG"), Conditional("TEST1")]  
void TraceMethod()  
{  
    // ...  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="ad0b9-124">Per convenzione tutti i nomi di attributo terminano con la parola "Attribute", in modo che sia possibile distinguerli da altri elementi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-124">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="ad0b9-125">Tuttavia, quando gli attributi vengono usati nel codice, non è necessario specificare il suffisso Attribute.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-125">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="ad0b9-126">Ad esempio, `[DllImport]` è equivalente a `[DllImportAttribute]`, mentre `DllImportAttribute` è il nome effettivo dell'attributo in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-126">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>  
  
### <a name="attribute-parameters"></a><span data-ttu-id="ad0b9-127">Parametri degli attributi</span><span class="sxs-lookup"><span data-stu-id="ad0b9-127">Attribute Parameters</span></span>  
 <span data-ttu-id="ad0b9-128">Diversi attributi dispongono di parametri, che possono essere posizionali, senza nome o denominati.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-128">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="ad0b9-129">I parametri posizionali devono essere specificati in un determinato ordine e non possono essere omessi. I parametri denominati sono invece facoltativi e possono essere specificati in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-129">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="ad0b9-130">I parametri posizionali vengono specificati per primi.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-130">Positional parameters are specified first.</span></span> <span data-ttu-id="ad0b9-131">I tre attributi seguenti, ad esempio, sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="ad0b9-131">For example, these three attributes are equivalent:</span></span>  
  
```csharp  
[DllImport("user32.dll")]  
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]  
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]  
```  
  
 <span data-ttu-id="ad0b9-132">Il primo parametro, ovvero il nome della DLL, è posizionale ed è sempre specificato per primo. Gli altri parametri sono denominati.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-132">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="ad0b9-133">In questo caso, entrambi i parametri denominati sono impostati automaticamente su false e possono quindi essere omessi.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-133">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="ad0b9-134">Per informazioni sui valori predefiniti dei parametri, fare riferimento alla documentazione di ciascun attributo.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-134">Refer to the individual attribute's documentation for information on default parameter values.</span></span>  
  
### <a name="attribute-targets"></a><span data-ttu-id="ad0b9-135">Destinazioni degli attributi</span><span class="sxs-lookup"><span data-stu-id="ad0b9-135">Attribute Targets</span></span>  
 <span data-ttu-id="ad0b9-136">La *destinazione* di un attributo è l'entità a cui tale attributo viene applicato.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-136">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="ad0b9-137">Un attributo, ad esempio, può essere applicato a una classe, a un metodo particolare o a un intero assembly.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-137">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="ad0b9-138">Per impostazione predefinita, un attributo viene applicato all'elemento che lo segue.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-138">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="ad0b9-139">È tuttavia possibile identificare in modo esplicito, ad esempio, se un attributo viene applicato a un metodo, al relativo parametro o al relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-139">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>  
  
 <span data-ttu-id="ad0b9-140">Per identificare in modo esplicito la destinazione di un attributo, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ad0b9-140">To explicitly identify an attribute target, use the following syntax:</span></span>  
  
```csharp  
[target : attribute-list]  
```  
  
 <span data-ttu-id="ad0b9-141">Nella tabella seguente sono elencati i possibili valori di `target`.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-141">The list of possible `target` values is shown in the following table.</span></span>  
  
|<span data-ttu-id="ad0b9-142">Valore di destinazione</span><span class="sxs-lookup"><span data-stu-id="ad0b9-142">Target value</span></span>|<span data-ttu-id="ad0b9-143">Si applica a</span><span class="sxs-lookup"><span data-stu-id="ad0b9-143">Applies to</span></span>|  
|------------------|----------------|  
|`assembly`|<span data-ttu-id="ad0b9-144">Intero assembly</span><span class="sxs-lookup"><span data-stu-id="ad0b9-144">Entire assembly</span></span>|  
|`module`|<span data-ttu-id="ad0b9-145">Modulo di assembly corrente</span><span class="sxs-lookup"><span data-stu-id="ad0b9-145">Current assembly module</span></span>|  
|`field`|<span data-ttu-id="ad0b9-146">Campo in una classe o uno struct</span><span class="sxs-lookup"><span data-stu-id="ad0b9-146">Field in a class or a struct</span></span>|  
|`event`|<span data-ttu-id="ad0b9-147">Evento</span><span class="sxs-lookup"><span data-stu-id="ad0b9-147">Event</span></span>|  
|`method`|<span data-ttu-id="ad0b9-148">Metodo o funzioni di accesso alle proprietà `get` e `set`</span><span class="sxs-lookup"><span data-stu-id="ad0b9-148">Method or `get` and `set` property accessors</span></span>|  
|`param`|<span data-ttu-id="ad0b9-149">Parametri del metodo o parametri della funzione di accesso alla proprietà `set`</span><span class="sxs-lookup"><span data-stu-id="ad0b9-149">Method parameters or `set` property accessor parameters</span></span>|  
|`property`|<span data-ttu-id="ad0b9-150">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ad0b9-150">Property</span></span>|  
|`return`|<span data-ttu-id="ad0b9-151">Valore restituito di un metodo, un indicizzatore di proprietà o una funzione di accesso alla proprietà `get`</span><span class="sxs-lookup"><span data-stu-id="ad0b9-151">Return value of a method, property indexer, or `get` property accessor</span></span>|  
|`type`|<span data-ttu-id="ad0b9-152">Struct, classe, interfaccia, enumeratore o delegato</span><span class="sxs-lookup"><span data-stu-id="ad0b9-152">Struct, class, interface, enum, or delegate</span></span>|  
  
 <span data-ttu-id="ad0b9-153">Nell'esempio seguente viene illustrato come applicare attributi ad assembly e moduli.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-153">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="ad0b9-154">Per altre informazioni, vedere [Attributi comuni (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ad0b9-154">For more information, see [Common Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
```csharp  
using System;  
using System.Reflection;  
[assembly: AssemblyTitleAttribute("Production assembly 4")]  
[module: CLSCompliant(true)]  
```  
  
 <span data-ttu-id="ad0b9-155">Nell'esempio seguente viene illustrato come applicare gli attributi a metodi, parametri di metodo e valori restituiti dal metodo in C#.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-155">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>  
  
```csharp  
// default: applies to method  
[SomeAttr]  
int Method1() { return 0; }  
  
// applies to method  
[method: SomeAttr]  
int Method2() { return 0; }  
  
// applies to return value  
[return: SomeAttr]  
int Method3() { return 0; }  
```  
  
> [!NOTE]
>  <span data-ttu-id="ad0b9-156">Indipendentemente dalle destinazioni in cui l'oggetto `SomeAttr` è definito come valido, è necessario specificare la destinazione `return`, anche se `SomeAttr` viene definito in modo da essere valido solo per i valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-156">Regardless of the targets on which `SomeAttr` is defined to be valid, the `return` target has to be specified, even if `SomeAttr` were defined to apply only to return values.</span></span> <span data-ttu-id="ad0b9-157">In altre parole, il compilatore non usa le informazioni `AttributeUsage` per risolvere le destinazioni degli attributi ambigue.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-157">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="ad0b9-158">Per altre informazioni, vedere [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).</span><span class="sxs-lookup"><span data-stu-id="ad0b9-158">For more information, see [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).</span></span>  
  
## <a name="common-uses-for-attributes"></a><span data-ttu-id="ad0b9-159">Usi comuni degli attributi</span><span class="sxs-lookup"><span data-stu-id="ad0b9-159">Common Uses for Attributes</span></span>  
 <span data-ttu-id="ad0b9-160">Di seguito vengono elencati alcuni degli usi comuni degli attributi nel codice:</span><span class="sxs-lookup"><span data-stu-id="ad0b9-160">The following list includes a few of the common uses of attributes in code:</span></span>  
  
-   <span data-ttu-id="ad0b9-161">Contrassegno dei metodi mediante l'attributo `WebMethod` nei servizi Web per indicare che è possibile chiamare il metodo tramite il protocollo SOAP.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-161">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="ad0b9-162">Per altre informazioni, vedere <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-162">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
-   <span data-ttu-id="ad0b9-163">Descrizione della procedura di marshalling dei parametri del metodo durante l'interazione con il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-163">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="ad0b9-164">Per altre informazioni, vedere <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-164">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>  
  
-   <span data-ttu-id="ad0b9-165">Descrizione delle proprietà COM per classi, metodi e interfacce.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-165">Describing the COM properties for classes, methods, and interfaces.</span></span>  
  
-   <span data-ttu-id="ad0b9-166">Chiamata al codice non gestito che usa la classe <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-166">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>  
  
-   <span data-ttu-id="ad0b9-167">Descrizione dell'assembly con indicazione di titolo, versione, descrizione o marchio.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-167">Describing your assembly in terms of title, version, description, or trademark.</span></span>  
  
-   <span data-ttu-id="ad0b9-168">Descrizione dei membri della classe da serializzare per la persistenza.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-168">Describing which members of a class to serialize for persistence.</span></span>  
  
-   <span data-ttu-id="ad0b9-169">Descrizione della procedura di mapping tra membri di una classe e nodi XML per la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-169">Describing how to map between class members and XML nodes for XML serialization.</span></span>  
  
-   <span data-ttu-id="ad0b9-170">Descrizione dei requisiti di sicurezza per i metodi.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-170">Describing the security requirements for methods.</span></span>  
  
-   <span data-ttu-id="ad0b9-171">Definizione delle caratteristiche usate per garantire la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-171">Specifying characteristics used to enforce security.</span></span>  
  
-   <span data-ttu-id="ad0b9-172">Controllo delle ottimizzazioni tramite il compilatore JIT (Just-In-Time), in modo da garantire un semplice debug del codice.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-172">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>  
  
-   <span data-ttu-id="ad0b9-173">Recupero di informazioni relative al chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="ad0b9-173">Obtaining information about the caller to a method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ad0b9-174">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ad0b9-174">Related Sections</span></span>  
 <span data-ttu-id="ad0b9-175">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="ad0b9-175">For more information, see:</span></span>  
  
-   [<span data-ttu-id="ad0b9-176">Creazione di attributi personalizzati (C#)</span><span class="sxs-lookup"><span data-stu-id="ad0b9-176">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
  
-   <span data-ttu-id="ad0b9-177">[Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Accesso agli attributi tramite reflection (C#))</span><span class="sxs-lookup"><span data-stu-id="ad0b9-177">[Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>  
  
-   [<span data-ttu-id="ad0b9-178">Procedura: Creare un'unione C-C++ tramite attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="ad0b9-178">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
-   [<span data-ttu-id="ad0b9-179">Attributi comuni (C#)</span><span class="sxs-lookup"><span data-stu-id="ad0b9-179">Common Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
  
-   [<span data-ttu-id="ad0b9-180">Informazioni sul chiamante (C#)</span><span class="sxs-lookup"><span data-stu-id="ad0b9-180">Caller Information (C#)</span></span>](../../../../csharp/programming-guide/concepts/caller-information.md)  
  
## <a name="see-also"></a><span data-ttu-id="ad0b9-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad0b9-181">See Also</span></span>  
 [<span data-ttu-id="ad0b9-182">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ad0b9-182">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ad0b9-183">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="ad0b9-183">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="ad0b9-184">Attributi</span><span class="sxs-lookup"><span data-stu-id="ad0b9-184">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)
