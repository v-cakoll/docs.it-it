---
title: /vbruntime | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
dev_langs:
- VB
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
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
ms.openlocfilehash: cb07ed8c2f6070079cc51c290ff5a61305c5a5d3
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="vbruntime"></a><span data-ttu-id="18b6d-102">/vbruntime</span><span class="sxs-lookup"><span data-stu-id="18b6d-102">/vbruntime</span></span>
<span data-ttu-id="18b6d-103">Indica che il compilatore deve compilare senza un riferimento alla libreria di runtime di Visual Basic oppure con un riferimento a una libreria di runtime specifica.</span><span class="sxs-lookup"><span data-stu-id="18b6d-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18b6d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18b6d-104">Syntax</span></span>  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="18b6d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="18b6d-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="18b6d-106">Compilare senza un riferimento alla libreria di Runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="18b6d-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="18b6d-107">Esegue la compilazione con un riferimento per il valore predefinito della libreria di Runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="18b6d-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="18b6d-108">La compilazione senza un riferimento alla libreria di Runtime di Visual Basic e incorpora le funzionalità principali dalla libreria di Runtime di Visual Basic in un assembly.</span><span class="sxs-lookup"><span data-stu-id="18b6d-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="18b6d-109">Esegue la compilazione con un riferimento alla libreria (DLL) specificato.</span><span class="sxs-lookup"><span data-stu-id="18b6d-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18b6d-110">Note</span><span class="sxs-lookup"><span data-stu-id="18b6d-110">Remarks</span></span>  
 <span data-ttu-id="18b6d-111">Il `/vbruntime` l'opzione del compilatore consente di specificare che il compilatore esegue la compilazione senza un riferimento alla libreria di Runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="18b6d-111">The `/vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="18b6d-112">Se esegue la compilazione senza un riferimento alla libreria di Runtime di Visual Basic, errori o avvisi vengono registrati in costrutti di linguaggio o codice che generano una chiamata a un supporto di runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="18b6d-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="18b6d-113">(A *helper di runtime di Visual Basic* è una funzione definita in Microsoft.VisualBasic.dll che viene chiamato in fase di esecuzione per eseguire una semantica di linguaggio specifica.)</span><span class="sxs-lookup"><span data-stu-id="18b6d-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="18b6d-114">Il `/vbruntime+` opzione produce lo stesso comportamento che si verifica quando non `/vbruntime` viene specificata l'opzione.</span><span class="sxs-lookup"><span data-stu-id="18b6d-114">The `/vbruntime+` option produces the same behavior that occurs if no `/vbruntime` switch is specified.</span></span> <span data-ttu-id="18b6d-115">È possibile utilizzare il `/vbruntime+` opzione per eseguire l'override precedente `/vbruntime` commutatori.</span><span class="sxs-lookup"><span data-stu-id="18b6d-115">You can use the `/vbruntime+` option to override previous `/vbruntime` switches.</span></span>  
  
 <span data-ttu-id="18b6d-116">Maggior parte degli oggetti di `My` tipo non sono disponibili quando si utilizza il `/vbruntime-` o `vbruntime:``path` opzioni.</span><span class="sxs-lookup"><span data-stu-id="18b6d-116">Most objects of the `My` type are unavailable when you use the `/vbruntime-` or `vbruntime:``path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="18b6d-117">Incorporare funzionalità di base di Runtime di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18b6d-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="18b6d-118">Il `/vbruntime*` consente di eseguire la compilazione senza un riferimento a una libreria di runtime.</span><span class="sxs-lookup"><span data-stu-id="18b6d-118">The `/vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="18b6d-119">Al contrario, la funzionalità di base dalla libreria di Runtime di Visual Basic è incorporata nell'assembly utente.</span><span class="sxs-lookup"><span data-stu-id="18b6d-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="18b6d-120">È possibile utilizzare questa opzione se l'applicazione viene eseguita su piattaforme che non contengono il runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="18b6d-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="18b6d-121">I membri di runtime seguenti sono incorporati:</span><span class="sxs-lookup"><span data-stu-id="18b6d-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="18b6d-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions>classe</xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="18b6d-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="18b6d-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>metodo</xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="18b6d-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="18b6d-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>metodo</xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="18b6d-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="18b6d-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>metodo</xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="18b6d-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="18b6d-126"><xref:Microsoft.VisualBasic.Constants.vbBack>(costante)</xref:Microsoft.VisualBasic.Constants.vbBack></span><span class="sxs-lookup"><span data-stu-id="18b6d-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="18b6d-127"><xref:Microsoft.VisualBasic.Constants.vbCr>(costante)</xref:Microsoft.VisualBasic.Constants.vbCr></span><span class="sxs-lookup"><span data-stu-id="18b6d-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="18b6d-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf>(costante)</xref:Microsoft.VisualBasic.Constants.vbCrLf></span><span class="sxs-lookup"><span data-stu-id="18b6d-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="18b6d-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed>(costante)</xref:Microsoft.VisualBasic.Constants.vbFormFeed></span><span class="sxs-lookup"><span data-stu-id="18b6d-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="18b6d-130"><xref:Microsoft.VisualBasic.Constants.vbLf>(costante)</xref:Microsoft.VisualBasic.Constants.vbLf></span><span class="sxs-lookup"><span data-stu-id="18b6d-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="18b6d-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine>(costante)</xref:Microsoft.VisualBasic.Constants.vbNewLine></span><span class="sxs-lookup"><span data-stu-id="18b6d-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="18b6d-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar>(costante)</xref:Microsoft.VisualBasic.Constants.vbNullChar></span><span class="sxs-lookup"><span data-stu-id="18b6d-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="18b6d-133"><xref:Microsoft.VisualBasic.Constants.vbNullString>(costante)</xref:Microsoft.VisualBasic.Constants.vbNullString></span><span class="sxs-lookup"><span data-stu-id="18b6d-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="18b6d-134"><xref:Microsoft.VisualBasic.Constants.vbTab>(costante)</xref:Microsoft.VisualBasic.Constants.vbTab></span><span class="sxs-lookup"><span data-stu-id="18b6d-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="18b6d-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab>(costante)</xref:Microsoft.VisualBasic.Constants.vbVerticalTab></span><span class="sxs-lookup"><span data-stu-id="18b6d-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="18b6d-136">Alcuni oggetti del `My` tipo</span><span class="sxs-lookup"><span data-stu-id="18b6d-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="18b6d-137">Se si esegue la compilazione utilizzando il `/vbruntime*` opzione e il codice fa riferimento a un membro dalla libreria di Runtime di Visual Basic che non sono incorporati con le funzionalità di base, il compilatore restituisce un errore che indica che il membro non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="18b6d-137">If you compile using the `/vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="18b6d-138">Riferimento a una libreria specificata</span><span class="sxs-lookup"><span data-stu-id="18b6d-138">Referencing a specified library</span></span>  
 <span data-ttu-id="18b6d-139">È possibile utilizzare il `path` argomento per la compilazione con un riferimento a una libreria di runtime personalizzato anziché il valore predefinito della libreria di Runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="18b6d-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="18b6d-140">Se il valore per il `path` argomento è un percorso completo di una DLL, il compilatore utilizzerà quel file come libreria di runtime.</span><span class="sxs-lookup"><span data-stu-id="18b6d-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="18b6d-141">Se il valore per il `path` argomento non è un percorso completo di una DLL, il compilatore Visual Basic cercherà la DLL identificata nella cartella corrente prima.</span><span class="sxs-lookup"><span data-stu-id="18b6d-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="18b6d-142">Quindi, la cercherà nel percorso specificato utilizzando il [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="18b6d-142">It will then search in the path that you have specified by using the [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="18b6d-143">Se il `/sdkpath` l'opzione del compilatore non viene utilizzato, il compilatore effettuerà la ricerca per la DLL identificata nella cartella di .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="18b6d-143">If the `/sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18b6d-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="18b6d-144">Example</span></span>  
 <span data-ttu-id="18b6d-145">Nell'esempio seguente viene illustrato come utilizzare il `/vbruntime` opzione di compilazione con un riferimento a una libreria personalizzata.</span><span class="sxs-lookup"><span data-stu-id="18b6d-145">The following example shows how to use the `/vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="18b6d-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18b6d-146">See Also</span></span>  
 <span data-ttu-id="18b6d-147">[Core di Visual Basic-nuova modalità di compilazione in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx) </span><span class="sxs-lookup"><span data-stu-id="18b6d-147">[Visual Basic Core – New compilation mode in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx) </span></span>  
<span data-ttu-id="18b6d-148"> [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="18b6d-148"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="18b6d-149"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="18b6d-149"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="18b6d-150"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span><span class="sxs-lookup"><span data-stu-id="18b6d-150"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span></span>
