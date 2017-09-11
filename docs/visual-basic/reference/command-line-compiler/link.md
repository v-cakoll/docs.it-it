---
title: /Link (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 71ecefc898ca37cbf7299d97518e1ce2547a58da
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="link-visual-basic"></a><span data-ttu-id="b8003-102">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8003-102">/link (Visual Basic)</span></span>
<span data-ttu-id="b8003-103">Indica al compilatore di rendere disponibile per il progetto in corso di compilazione informazioni sui tipi COM nei file specificati.</span><span class="sxs-lookup"><span data-stu-id="b8003-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8003-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8003-104">Syntax</span></span>  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="b8003-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b8003-105">Arguments</span></span>  
  
|<span data-ttu-id="b8003-106">Termine</span><span class="sxs-lookup"><span data-stu-id="b8003-106">Term</span></span>|<span data-ttu-id="b8003-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="b8003-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="b8003-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8003-108">Required.</span></span> <span data-ttu-id="b8003-109">Elenco delimitato da virgole di nomi di file di assembly.</span><span class="sxs-lookup"><span data-stu-id="b8003-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="b8003-110">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="b8003-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8003-111">Note</span><span class="sxs-lookup"><span data-stu-id="b8003-111">Remarks</span></span>  
 <span data-ttu-id="b8003-112">Il `/link` consente di distribuire un'applicazione che incorpora informazioni sul tipo.</span><span class="sxs-lookup"><span data-stu-id="b8003-112">The `/link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="b8003-113">L'applicazione può quindi utilizzare tipi che implementano le informazioni sul tipo incorporato senza richiedere un riferimento all'assembly di runtime in un assembly di runtime.</span><span class="sxs-lookup"><span data-stu-id="b8003-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="b8003-114">Se vengono pubblicate diverse versioni dell'assembly di runtime, l'applicazione che contiene le informazioni sul tipo incorporato può funzionare con le diverse versioni senza dover ricompilare.</span><span class="sxs-lookup"><span data-stu-id="b8003-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="b8003-115">Per un esempio, vedere [procedura dettagliata: incorporamento di tipi da assembly gestiti](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span><span class="sxs-lookup"><span data-stu-id="b8003-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="b8003-116">Utilizzo di `/link` opzione è particolarmente utile quando si lavora con interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="b8003-116">Using the `/link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="b8003-117">È possibile incorporare tipi COM in modo che l'applicazione non richiede un assembly di interoperabilità primario (PIA) nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b8003-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="b8003-118">Il `/link` opzione indica al compilatore di incorporare le informazioni sul tipo COM dall'assembly di interoperabilità cui viene fatto riferimento nel codice compilato risulta.</span><span class="sxs-lookup"><span data-stu-id="b8003-118">The `/link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="b8003-119">Il tipo COM è identificato dal valore CLSID (GUID).</span><span class="sxs-lookup"><span data-stu-id="b8003-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="b8003-120">Di conseguenza, l'applicazione può eseguire in un computer di destinazione che ha installato gli stessi tipi COM con gli stessi valori CLSID.</span><span class="sxs-lookup"><span data-stu-id="b8003-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="b8003-121">Le applicazioni che consentono di automatizzare Microsoft Office sono un buon esempio.</span><span class="sxs-lookup"><span data-stu-id="b8003-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="b8003-122">Poiché le applicazioni come Office mantengono in genere lo stesso valore CLSID tra le diverse versioni, l'applicazione può utilizzare i tipi COM di cui viene fatto riferimenti come long come .NET Framework 4 o versione successiva è installato nel computer di destinazione e l'applicazione utilizza metodi, proprietà o eventi che rientrano nei tipi di riferimento COM.</span><span class="sxs-lookup"><span data-stu-id="b8003-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="b8003-123">Il `/link` opzione incorpora solo interfacce, strutture e delegati.</span><span class="sxs-lookup"><span data-stu-id="b8003-123">The `/link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="b8003-124">Incorporamento di classi COM non è supportata.</span><span class="sxs-lookup"><span data-stu-id="b8003-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8003-125">Quando si crea un'istanza di un tipo COM incorporato nel codice, è necessario creare l'istanza utilizzando l'interfaccia appropriata.</span><span class="sxs-lookup"><span data-stu-id="b8003-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="b8003-126">Il tentativo di creare un'istanza di un tipo COM incorporato utilizzando la coclasse provoca un errore.</span><span class="sxs-lookup"><span data-stu-id="b8003-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="b8003-127">Per impostare il `/link` opzione [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], aggiungere un riferimento all'assembly e impostare il `Embed Interop Types` proprietà **true**.</span><span class="sxs-lookup"><span data-stu-id="b8003-127">To set the `/link` option in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="b8003-128">Il valore predefinito per il `Embed Interop Types` è **false**.</span><span class="sxs-lookup"><span data-stu-id="b8003-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="b8003-129">Se si collega a un assembly COM (Assembly a) che a sua volta fa riferimento a un altro assembly COM (Assembly B), è necessario anche collegare all'Assembly B se viene soddisfatta una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8003-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="b8003-130">Un tipo da Assembly A eredita da un tipo o implementa un'interfaccia dell'Assembly B.</span><span class="sxs-lookup"><span data-stu-id="b8003-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="b8003-131">Un campo, proprietà, evento o metodo che presenta un tipo di parametro o tipo restituito dall'Assembly B viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="b8003-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="b8003-132">Utilizzare [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) per specificare la directory in cui si trova una o più riferimenti agli assembly.</span><span class="sxs-lookup"><span data-stu-id="b8003-132">Use [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="b8003-133">Come il [/Reference](../../../visual-basic/reference/command-line-compiler/reference.md) l'opzione del compilatore, il `/link` l'opzione del compilatore utilizza il file di risposta Vbc. rsp, i riferimenti utilizzati [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assembly.</span><span class="sxs-lookup"><span data-stu-id="b8003-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `/link` compiler option uses the Vbc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies.</span></span> <span data-ttu-id="b8003-134">Utilizzare il [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) l'opzione del compilatore se non si desidera al compilatore di utilizzare tale file.</span><span class="sxs-lookup"><span data-stu-id="b8003-134">Use the [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="b8003-135">La versione abbreviata di `/link` è `/l`.</span><span class="sxs-lookup"><span data-stu-id="b8003-135">The short form of `/link` is `/l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="b8003-136">Generics e tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="b8003-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="b8003-137">Nelle sezioni seguenti vengono descrivono le limitazioni all'utilizzo di tipi generici nelle applicazioni che incorporano tipi di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b8003-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="b8003-138">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="b8003-138">Generic Interfaces</span></span>  
 <span data-ttu-id="b8003-139">Impossibile utilizzare le interfacce generiche che sono incorporate da un assembly di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b8003-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="b8003-140">come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b8003-140">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="b8003-141">[!code-vb[VbLinkCompiler n.&1;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b8003-141">[!code-vb[VbLinkCompiler#1](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]</span></span>  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="b8003-142">Tipi che dispongono di parametri generici</span><span class="sxs-lookup"><span data-stu-id="b8003-142">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="b8003-143">Tipi che dispongono di un parametro generico il cui tipo è incorporato a un assembly di interoperabilità non possono essere utilizzati se tale tipo proviene da un assembly esterno.</span><span class="sxs-lookup"><span data-stu-id="b8003-143">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="b8003-144">Questa restrizione non si applica alle interfacce.</span><span class="sxs-lookup"><span data-stu-id="b8003-144">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="b8003-145">Si consideri ad esempio il <xref:Microsoft.Office.Interop.Excel.Range>interfaccia definita nel <xref:Microsoft.Office.Interop.Excel>assembly.</xref:Microsoft.Office.Interop.Excel> </xref:Microsoft.Office.Interop.Excel.Range></span><span class="sxs-lookup"><span data-stu-id="b8003-145">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="b8003-146">Se una libreria incorpora tipi di interoperabilità dal <xref:Microsoft.Office.Interop.Excel>assembly ed espone un metodo che restituisce un tipo generico con un parametro il cui tipo è il <xref:Microsoft.Office.Interop.Excel.Range>interfaccia, che metodo deve restituire un'interfaccia generica, come illustrato nell'esempio di codice seguente.</xref:Microsoft.Office.Interop.Excel.Range> </xref:Microsoft.Office.Interop.Excel></span><span class="sxs-lookup"><span data-stu-id="b8003-146">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 <span data-ttu-id="b8003-147">[!code-vb[VbLinkCompiler n.&2;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b8003-147">[!code-vb[VbLinkCompiler#2](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]</span></span>  
<span data-ttu-id="b8003-148">[!code-vb[VbLinkCompiler n.&3;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b8003-148">[!code-vb[VbLinkCompiler#3](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]</span></span>  
<span data-ttu-id="b8003-149">[!code-vb[VbLinkCompiler n.&4;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b8003-149">[!code-vb[VbLinkCompiler#4](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]</span></span>  
  
 <span data-ttu-id="b8003-150">Nell'esempio seguente, il codice client può chiamare il metodo che restituisce il <xref:System.Collections.IList>interfaccia generica senza errori.</xref:System.Collections.IList></span><span class="sxs-lookup"><span data-stu-id="b8003-150">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 <span data-ttu-id="b8003-151">[!code-vb[VbLinkCompiler n.&5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="b8003-151">[!code-vb[VbLinkCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8003-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8003-152">Example</span></span>  
 <span data-ttu-id="b8003-153">Il codice seguente consente di compilare file di origine `OfficeApp.vb` e fare riferimento agli assembly da `COMData1.dll` e `COMData2.dll` per produrre `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="b8003-153">The following code compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```vb  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8003-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8003-154">See Also</span></span>  
 <span data-ttu-id="b8003-155">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8003-155">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="b8003-156"> [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) </span><span class="sxs-lookup"><span data-stu-id="b8003-156"> [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) </span></span>  
<span data-ttu-id="b8003-157"> [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="b8003-157"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="b8003-158"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="b8003-158"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="b8003-159"> [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) </span><span class="sxs-lookup"><span data-stu-id="b8003-159"> [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) </span></span>  
<span data-ttu-id="b8003-160"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="b8003-160"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="b8003-161"> [Introduzione all'interoperabilità COM](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)</span><span class="sxs-lookup"><span data-stu-id="b8003-161"> [Introduction to COM Interop](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)</span></span>
