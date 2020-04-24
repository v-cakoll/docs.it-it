---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
ms.openlocfilehash: 8c7789c6af7b82ecb40ecd73d09f64aa1da3fd4b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005048"
---
# <a name="-vbruntime"></a><span data-ttu-id="35c9d-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="35c9d-102">-vbruntime</span></span>
<span data-ttu-id="35c9d-103">Indica che il compilatore deve compilare senza un riferimento alla libreria di runtime di Visual Basic oppure con un riferimento a una libreria di runtime specifica.</span><span class="sxs-lookup"><span data-stu-id="35c9d-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35c9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35c9d-104">Syntax</span></span>  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="35c9d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="35c9d-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="35c9d-106">Eseguire la compilazione senza un riferimento alla libreria di runtime Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="35c9d-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="35c9d-107">Compilare con un riferimento alla libreria di runtime Visual Basic predefinita.</span><span class="sxs-lookup"><span data-stu-id="35c9d-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="35c9d-108">Eseguire la compilazione senza un riferimento alla libreria di runtime Visual Basic e incorporare la funzionalità di base dalla libreria di runtime Visual Basic nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="35c9d-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="35c9d-109">Compilare con un riferimento alla libreria (DLL) specificata.</span><span class="sxs-lookup"><span data-stu-id="35c9d-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35c9d-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="35c9d-110">Remarks</span></span>  
 <span data-ttu-id="35c9d-111">L' `-vbruntime` opzione del compilatore consente di specificare che il compilatore deve compilare senza un riferimento alla libreria di runtime Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="35c9d-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="35c9d-112">Se si compila senza un riferimento alla libreria di runtime Visual Basic, gli errori o gli avvisi vengono registrati nel codice o nei costrutti di linguaggio che generano una chiamata a un helper del runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="35c9d-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="35c9d-113">Un *helper Visual Basic Runtime* è una funzione definita in Microsoft. VisualBasic. dll che viene chiamata in fase di esecuzione per eseguire una semantica di linguaggio specifica.</span><span class="sxs-lookup"><span data-stu-id="35c9d-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="35c9d-114">L' `-vbruntime+` opzione produce lo stesso comportamento che si verifica se `-vbruntime` non è specificata alcuna opzione.</span><span class="sxs-lookup"><span data-stu-id="35c9d-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="35c9d-115">È possibile usare l' `-vbruntime+` opzione per eseguire l' `-vbruntime` override delle opzioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="35c9d-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="35c9d-116">La maggior parte degli `My` oggetti del tipo non sono disponibili quando `-vbruntime-` si `-vbruntime:path` usano le opzioni o.</span><span class="sxs-lookup"><span data-stu-id="35c9d-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="35c9d-117">Incorporamento della funzionalità di base di Visual Basic Runtime</span><span class="sxs-lookup"><span data-stu-id="35c9d-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="35c9d-118">L' `-vbruntime*` opzione consente di compilare senza un riferimento a una libreria di Runtime.</span><span class="sxs-lookup"><span data-stu-id="35c9d-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="35c9d-119">Al contrario, la funzionalità di base della libreria di runtime Visual Basic è incorporata nell'assembly utente.</span><span class="sxs-lookup"><span data-stu-id="35c9d-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="35c9d-120">È possibile usare questa opzione se l'applicazione viene eseguita su piattaforme che non contengono il runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="35c9d-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="35c9d-121">Sono incorporati i membri runtime seguenti:</span><span class="sxs-lookup"><span data-stu-id="35c9d-121">The following runtime members are embedded:</span></span>  
  
- <span data-ttu-id="35c9d-122">Classe <xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="35c9d-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
- <span data-ttu-id="35c9d-123">Metodo <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="35c9d-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
- <span data-ttu-id="35c9d-124">Metodo <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="35c9d-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
- <span data-ttu-id="35c9d-125">Metodo <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="35c9d-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
- <span data-ttu-id="35c9d-126"><xref:Microsoft.VisualBasic.Constants.vbBack>costante</span><span class="sxs-lookup"><span data-stu-id="35c9d-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
- <span data-ttu-id="35c9d-127"><xref:Microsoft.VisualBasic.Constants.vbCr>costante</span><span class="sxs-lookup"><span data-stu-id="35c9d-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
- <span data-ttu-id="35c9d-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf>costante</span><span class="sxs-lookup"><span data-stu-id="35c9d-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
- <span data-ttu-id="35c9d-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed>costante</span><span class="sxs-lookup"><span data-stu-id="35c9d-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
- <span data-ttu-id="35c9d-130"><xref:Microsoft.VisualBasic.Constants.vbLf>costante</span><span class="sxs-lookup"><span data-stu-id="35c9d-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
- <span data-ttu-id="35c9d-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine>costante</span><span class="sxs-lookup"><span data-stu-id="35c9d-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
- <span data-ttu-id="35c9d-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar>costante</span><span class="sxs-lookup"><span data-stu-id="35c9d-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
- <span data-ttu-id="35c9d-133"><xref:Microsoft.VisualBasic.Constants.vbNullString>costante</span><span class="sxs-lookup"><span data-stu-id="35c9d-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
- <span data-ttu-id="35c9d-134"><xref:Microsoft.VisualBasic.Constants.vbTab>costante</span><span class="sxs-lookup"><span data-stu-id="35c9d-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
- <span data-ttu-id="35c9d-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab>costante</span><span class="sxs-lookup"><span data-stu-id="35c9d-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
- <span data-ttu-id="35c9d-136">Alcuni oggetti del `My` tipo</span><span class="sxs-lookup"><span data-stu-id="35c9d-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="35c9d-137">Se si esegue la compilazione `-vbruntime*` con l'opzione e il codice fa riferimento a un membro dalla libreria di runtime Visual Basic che non è incorporato con la funzionalità di base, il compilatore restituisce un errore che indica che il membro non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="35c9d-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="35c9d-138">Riferimento a una libreria specificata</span><span class="sxs-lookup"><span data-stu-id="35c9d-138">Referencing a specified library</span></span>  
 <span data-ttu-id="35c9d-139">È possibile usare l' `path` argomento per compilare con un riferimento a una libreria di runtime personalizzata anziché la libreria di runtime Visual Basic predefinita.</span><span class="sxs-lookup"><span data-stu-id="35c9d-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="35c9d-140">Se il valore per l' `path` argomento è un percorso completo di una dll, il compilatore utilizzerà tale file come libreria di Runtime.</span><span class="sxs-lookup"><span data-stu-id="35c9d-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="35c9d-141">Se il valore dell' `path` argomento non è un percorso completo di una dll, il Visual Basic compilatore cercherà prima la DLL identificata nella cartella corrente.</span><span class="sxs-lookup"><span data-stu-id="35c9d-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="35c9d-142">Verrà quindi cercata nel percorso specificato tramite l'opzione del compilatore [-sdkpath (](../../../visual-basic/reference/command-line-compiler/sdkpath.md) .</span><span class="sxs-lookup"><span data-stu-id="35c9d-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="35c9d-143">Se non `-sdkpath` si usa l'opzione del compilatore, il compilatore cercherà la DLL identificata nella cartella .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="35c9d-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35c9d-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="35c9d-144">Example</span></span>  
 <span data-ttu-id="35c9d-145">Nell'esempio seguente viene illustrato come utilizzare l' `-vbruntime` opzione per compilare con un riferimento a una libreria personalizzata.</span><span class="sxs-lookup"><span data-stu-id="35c9d-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="35c9d-146">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="35c9d-146">See also</span></span>

- [<span data-ttu-id="35c9d-147">Visual Basic Core-nuova modalità di compilazione in Visual Studio 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="35c9d-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="35c9d-148">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="35c9d-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="35c9d-149">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="35c9d-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="35c9d-150">-sdkpath (</span><span class="sxs-lookup"><span data-stu-id="35c9d-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
