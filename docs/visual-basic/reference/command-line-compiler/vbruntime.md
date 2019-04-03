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
ms.openlocfilehash: a1988fcd19c6629d85ae0e739681fd39fe033c0d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843864"
---
# <a name="-vbruntime"></a><span data-ttu-id="8c285-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="8c285-102">-vbruntime</span></span>
<span data-ttu-id="8c285-103">Indica che il compilatore deve compilare senza un riferimento alla libreria di runtime di Visual Basic oppure con un riferimento a una libreria di runtime specifica.</span><span class="sxs-lookup"><span data-stu-id="8c285-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c285-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c285-104">Syntax</span></span>  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="8c285-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8c285-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="8c285-106">Compilare senza un riferimento alla libreria di Runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8c285-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="8c285-107">Eseguire la compilazione con un riferimento per il valore predefinito della libreria di Runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8c285-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="8c285-108">Compilare senza un riferimento alla libreria di Runtime di Visual Basic e incorporare funzionalità di base dalla libreria di Runtime di Visual Basic nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8c285-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="8c285-109">Eseguire la compilazione con un riferimento alla libreria (DLL) specificato.</span><span class="sxs-lookup"><span data-stu-id="8c285-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c285-110">Note</span><span class="sxs-lookup"><span data-stu-id="8c285-110">Remarks</span></span>  
 <span data-ttu-id="8c285-111">Il `-vbruntime` opzione del compilatore consente di specificare che il compilatore deve compilare senza un riferimento alla libreria di Runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8c285-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="8c285-112">Se esegue la compilazione senza un riferimento alla libreria di Runtime di Visual Basic, vengono registrati errori o avvisi in costrutti di linguaggio o codice che generano una chiamata a un helper di runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8c285-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="8c285-113">(Un *helper di runtime di Visual Basic* è una funzione definita nel VisualBasic che viene chiamato in fase di esecuzione per l'esecuzione di un linguaggio specifico di semantico.)</span><span class="sxs-lookup"><span data-stu-id="8c285-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="8c285-114">Il `-vbruntime+` opzione produce lo stesso comportamento che si verifica se nessun `-vbruntime` viene specificata l'opzione.</span><span class="sxs-lookup"><span data-stu-id="8c285-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="8c285-115">È possibile usare la `-vbruntime+` opzione per eseguire l'override precedente `-vbruntime` commutatori.</span><span class="sxs-lookup"><span data-stu-id="8c285-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="8c285-116">La maggior parte degli oggetti del `My` tipo non sono disponibili quando si usa la `-vbruntime-` o `-vbruntime:path` opzioni.</span><span class="sxs-lookup"><span data-stu-id="8c285-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="8c285-117">Incorporamento di funzionalità di base di Runtime di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c285-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="8c285-118">Il `-vbruntime*` opzione consente di eseguire la compilazione senza un riferimento a una libreria di runtime.</span><span class="sxs-lookup"><span data-stu-id="8c285-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="8c285-119">Al contrario, la funzionalità di base dalla libreria di Runtime di Visual Basic è incorporata nell'assembly utente.</span><span class="sxs-lookup"><span data-stu-id="8c285-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="8c285-120">È possibile usare questa opzione se l'applicazione viene eseguita su piattaforme che non contengono il runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8c285-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="8c285-121">I membri di runtime seguenti sono incorporati:</span><span class="sxs-lookup"><span data-stu-id="8c285-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="8c285-122">Classe <xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="8c285-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="8c285-123">Metodo <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="8c285-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="8c285-124">Metodo <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="8c285-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="8c285-125">Metodo <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="8c285-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="8c285-126"><xref:Microsoft.VisualBasic.Constants.vbBack> Costante</span><span class="sxs-lookup"><span data-stu-id="8c285-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="8c285-127"><xref:Microsoft.VisualBasic.Constants.vbCr> Costante</span><span class="sxs-lookup"><span data-stu-id="8c285-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="8c285-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> Costante</span><span class="sxs-lookup"><span data-stu-id="8c285-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="8c285-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> Costante</span><span class="sxs-lookup"><span data-stu-id="8c285-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="8c285-130"><xref:Microsoft.VisualBasic.Constants.vbLf> Costante</span><span class="sxs-lookup"><span data-stu-id="8c285-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="8c285-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> Costante</span><span class="sxs-lookup"><span data-stu-id="8c285-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="8c285-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> Costante</span><span class="sxs-lookup"><span data-stu-id="8c285-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="8c285-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> Costante</span><span class="sxs-lookup"><span data-stu-id="8c285-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="8c285-134"><xref:Microsoft.VisualBasic.Constants.vbTab> Costante</span><span class="sxs-lookup"><span data-stu-id="8c285-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="8c285-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Costante</span><span class="sxs-lookup"><span data-stu-id="8c285-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="8c285-136">Alcuni oggetti del `My` tipo</span><span class="sxs-lookup"><span data-stu-id="8c285-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="8c285-137">Se si esegue la compilazione usando il `-vbruntime*` opzione e il codice fa riferimento a un membro dalla libreria di Runtime di Visual Basic che non sono incorporati con le funzionalità di base, il compilatore restituisce un errore che indica che il membro non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="8c285-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="8c285-138">Riferimento a una libreria specificata</span><span class="sxs-lookup"><span data-stu-id="8c285-138">Referencing a specified library</span></span>  
 <span data-ttu-id="8c285-139">È possibile usare il `path` argomento per la compilazione con un riferimento a una libreria di runtime personalizzato anziché il valore predefinito della libreria di Runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8c285-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="8c285-140">Se il valore per il `path` argomento è un percorso completo di una DLL, il compilatore userà tale file come libreria di runtime.</span><span class="sxs-lookup"><span data-stu-id="8c285-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="8c285-141">Se il valore per il `path` argomento non è un percorso completo di una DLL, il compilatore Visual Basic cercherà le DLL identificata nella cartella corrente prima di tutto.</span><span class="sxs-lookup"><span data-stu-id="8c285-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="8c285-142">Quindi cercherà nel percorso specificato usando il [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="8c285-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="8c285-143">Se il `-sdkpath` l'opzione del compilatore non viene utilizzato, il compilatore eseguirà la ricerca per la DLL identificata nella cartella di .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="8c285-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c285-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c285-144">Example</span></span>  
 <span data-ttu-id="8c285-145">Nell'esempio seguente viene illustrato come utilizzare il `-vbruntime` opzione per la compilazione con un riferimento a una libreria personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8c285-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c285-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c285-146">See also</span></span>

- [<span data-ttu-id="8c285-147">Core di Visual Basic: nuova modalità di compilazione in Visual Studio 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="8c285-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="8c285-148">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c285-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8c285-149">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="8c285-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="8c285-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="8c285-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
