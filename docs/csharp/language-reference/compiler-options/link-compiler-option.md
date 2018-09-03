---
title: -link (opzioni del compilatore C#)
ms.date: 07/20/2015
helpviewer_keywords:
- /l compiler option [C#]
- /link compiler option [C#]
- -l compiler option [C#]
- EmbedInteropTypes
- l compiler option [C#]
- embed interop types [COM Interop]
- -link compiler option [C#]
- link compiler option [C#]
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
ms.openlocfilehash: 00cfda489feb468c7e3c140ab63369b408b09152
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484452"
---
# <a name="-link-c-compiler-options"></a><span data-ttu-id="f725e-102">-link (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f725e-102">-link (C# Compiler Options)</span></span>
<span data-ttu-id="f725e-103">Indica al compilatore di rendere disponibili al progetto in fase di compilazione le informazioni sui tipi COM presenti negli assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="f725e-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f725e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f725e-104">Syntax</span></span>  
  
```console  
-link:fileList  
// -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="f725e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f725e-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="f725e-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f725e-106">Required.</span></span> <span data-ttu-id="f725e-107">Elenco di nomi di file di assembly delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="f725e-107">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="f725e-108">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="f725e-108">If the file name contains a space, enclose the name in quotation marks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f725e-109">Note</span><span class="sxs-lookup"><span data-stu-id="f725e-109">Remarks</span></span>  
 <span data-ttu-id="f725e-110">L'opzione `-link`consente di distribuire un'applicazione in cui sono incorporate informazioni sul tipo.</span><span class="sxs-lookup"><span data-stu-id="f725e-110">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="f725e-111">L'applicazione può quindi usare i tipi in un assembly di runtime che implementano le informazioni sul tipo incorporate senza dovere far riferimento all'assembly di runtime.</span><span class="sxs-lookup"><span data-stu-id="f725e-111">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="f725e-112">Se vengono pubblicate diverse versioni dell'assembly di runtime, l'applicazione che contiene le informazioni sul tipo incorporate può funzionare con le diverse versioni senza che sia necessaria la ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="f725e-112">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="f725e-113">Per un esempio, vedere [Procedura dettagliata: incorporamento dei tipi da assembly gestiti](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="f725e-113">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md).</span></span>  
  
 <span data-ttu-id="f725e-114">L'opzione `-link` è particolarmente utile quando si usa l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="f725e-114">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="f725e-115">È possibile incorporare tipi COM in modo che per l'applicazione non sia più necessario un assembly di interoperabilità primario nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f725e-115">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="f725e-116">L'opzione `-link` indica al compilatore di incorporare le informazioni sul tipo COM dall'assembly di interoperabilità a cui si fa riferimento nel codice compilato risultante.</span><span class="sxs-lookup"><span data-stu-id="f725e-116">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="f725e-117">Il tipo COM viene identificato dal valore CLSID (GUID).</span><span class="sxs-lookup"><span data-stu-id="f725e-117">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="f725e-118">Di conseguenza, l'applicazione può essere eseguita in un computer di destinazione in cui sono stati installati gli stessi tipi COM con gli stessi valori CLSID.</span><span class="sxs-lookup"><span data-stu-id="f725e-118">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="f725e-119">Le applicazioni che consentono di automatizzare Microsoft Office costituiscono un valido esempio.</span><span class="sxs-lookup"><span data-stu-id="f725e-119">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="f725e-120">Poiché applicazioni come Office mantengono in genere lo stesso valore CLSID in versioni diverse, l'applicazione può usare i tipi COM a cui si fa riferimento purché .NET Framework 4 o versioni successive sia installato nel computer di destinazione e l'applicazione usi metodi, proprietà o eventi inclusi nei tipi COM a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="f725e-120">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="f725e-121">L'opzione `-link` incorpora solo interfacce, strutture e delegati.</span><span class="sxs-lookup"><span data-stu-id="f725e-121">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="f725e-122">L'incorporamento di classi COM non è supportato.</span><span class="sxs-lookup"><span data-stu-id="f725e-122">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f725e-123">Quando si crea un'istanza di un tipo COM incorporato nel codice, è necessario creare l'istanza usando l'interfaccia appropriata.</span><span class="sxs-lookup"><span data-stu-id="f725e-123">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="f725e-124">Il tentativo di creare un'istanza di un tipo COM incorporato usando la coclasse genera un errore.</span><span class="sxs-lookup"><span data-stu-id="f725e-124">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="f725e-125">Per impostare l'opzione `-link` in Visual Studio, aggiungere un riferimento all'assembly e impostare la proprietà `Embed Interop Types` su **true**.</span><span class="sxs-lookup"><span data-stu-id="f725e-125">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="f725e-126">Il valore predefinito della proprietà `Embed Interop Types` è **false**.</span><span class="sxs-lookup"><span data-stu-id="f725e-126">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="f725e-127">Se si collega a un assembly COM (assembly A) che fa riferimento a un altro assembly COM (assembly B), è necessario eseguire il collegamento anche all'assembly B se si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f725e-127">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="f725e-128">Un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="f725e-128">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="f725e-129">Viene richiamato un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="f725e-129">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="f725e-130">Come l'opzione del compilatore [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md), anche l'opzione `-link` usa il file di risposta csc.rsp, che fa riferimento agli assembly [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] di uso più frequente.</span><span class="sxs-lookup"><span data-stu-id="f725e-130">Like the [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option, the `-link` compiler option uses the Csc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.</span></span> <span data-ttu-id="f725e-131">Usare l'opzione del compilatore [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) se non si vuole che il compilatore usi il file csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="f725e-131">Use the [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) compiler option if you do not want the compiler to use the Csc.rsp file.</span></span>  
  
 <span data-ttu-id="f725e-132">La forma breve di `-link` è `-l`.</span><span class="sxs-lookup"><span data-stu-id="f725e-132">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="f725e-133">Generics e tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="f725e-133">Generics and Embedded Types</span></span>  
 <span data-ttu-id="f725e-134">Nelle sezioni seguenti vengono descritte le limitazioni all'uso di tipi generici in applicazioni che incorporano tipi di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="f725e-134">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="f725e-135">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="f725e-135">Generic Interfaces</span></span>  
 <span data-ttu-id="f725e-136">Le interfacce generiche incorporate da un assembly di interoperabilità non possono essere usate,</span><span class="sxs-lookup"><span data-stu-id="f725e-136">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="f725e-137">come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f725e-137">This is shown in the following example.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#1](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_1.cs)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="f725e-138">Tipi con parametri generici</span><span class="sxs-lookup"><span data-stu-id="f725e-138">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="f725e-139">I tipi che hanno un parametro generico il cui tipo è incorporato da un assembly di interoperabilità non possono essere usati se tale tipo proviene da un assembly esterno.</span><span class="sxs-lookup"><span data-stu-id="f725e-139">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="f725e-140">Tale restrizione non si applica tuttavia alle interfacce.</span><span class="sxs-lookup"><span data-stu-id="f725e-140">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="f725e-141">Si consideri ad esempio l'interfaccia <xref:Microsoft.Office.Interop.Excel.Range> definita nell'assembly <xref:Microsoft.Office.Interop.Excel>.</span><span class="sxs-lookup"><span data-stu-id="f725e-141">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="f725e-142">Se una libreria incorpora tipi di interoperabilità dall'assembly <xref:Microsoft.Office.Interop.Excel> ed espone un metodo che restituisce un tipo generico che ha un parametro il cui tipo è l'interfaccia <xref:Microsoft.Office.Interop.Excel.Range>, il metodo deve restituire un'interfaccia generica, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f725e-142">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#2](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_2.cs)]  
[!code-csharp[VbLinkCompilerCS#3](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_3.cs)]  
[!code-csharp[VbLinkCompilerCS#4](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_4.cs)]  
  
 <span data-ttu-id="f725e-143">Nell'esempio seguente, il codice client può chiamare il metodo che restituisce l'interfaccia generica <xref:System.Collections.IList> senza errori.</span><span class="sxs-lookup"><span data-stu-id="f725e-143">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#5](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_5.cs)]  
  
## <a name="example"></a><span data-ttu-id="f725e-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="f725e-144">Example</span></span>  
 <span data-ttu-id="f725e-145">Nel codice riportato di seguito viene compilato il file di origine `OfficeApp.cs` e viene fatto riferimento agli assembly di `COMData1.dll` e `COMData2.dll` per generare `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="f725e-145">The following code compiles source file `OfficeApp.cs` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```csharp  
csc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f725e-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f725e-146">See Also</span></span>

- [<span data-ttu-id="f725e-147">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="f725e-147">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="f725e-148">Procedura dettagliata: Incorporamento dei tipi da assembly gestiti</span><span class="sxs-lookup"><span data-stu-id="f725e-148">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
- [<span data-ttu-id="f725e-149">-reference (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f725e-149">-reference (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)  
- [<span data-ttu-id="f725e-150">-noconfig (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f725e-150">-noconfig (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)  
- [<span data-ttu-id="f725e-151">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="f725e-151">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
- [<span data-ttu-id="f725e-152">Cenni preliminari sull'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f725e-152">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)
