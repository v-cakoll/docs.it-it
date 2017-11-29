---
title: Esempi di righe di comando di compilazione (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e168d40a22ca3737bee18f966df95988a2736a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="49e92-102">Esempi di righe di comando di compilazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49e92-102">Sample Compilation Command Lines (Visual Basic)</span></span>
<span data-ttu-id="49e92-103">In alternativa alla compilazione [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programmi dall'interno [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], è possibile compilare dalla riga di comando per generare file di libreria a collegamento dinamico (DLL) o file eseguibile (.exe).</span><span class="sxs-lookup"><span data-stu-id="49e92-103">As an alternative to compiling [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programs from within [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="49e92-104">Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore da riga di comando supporta un set completo di opzioni che controllano il debug, assembly e i file di input e outpui e le opzioni per il preprocessore.</span><span class="sxs-lookup"><span data-stu-id="49e92-104">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="49e92-105">Ogni opzione è disponibile in due formati intercambiabili: `-``option` e `/``option`.</span><span class="sxs-lookup"><span data-stu-id="49e92-105">Each option is available in two interchangeable forms: `-``option` and `/``option`.</span></span> <span data-ttu-id="49e92-106">Questa documentazione viene visualizzato soltanto il `/``option` form.</span><span class="sxs-lookup"><span data-stu-id="49e92-106">This documentation shows only the `/``option` form.</span></span>  
  
 <span data-ttu-id="49e92-107">Nella tabella seguente sono elencati alcuni esempi di righe di comando che è possibile modificare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="49e92-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="49e92-108">Per</span><span class="sxs-lookup"><span data-stu-id="49e92-108">To</span></span>|<span data-ttu-id="49e92-109">Usare</span><span class="sxs-lookup"><span data-stu-id="49e92-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="49e92-110">Compilare i file. vb e creare File.exe</span><span class="sxs-lookup"><span data-stu-id="49e92-110">Compile File.vb and create File.exe</span></span>|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="49e92-111">Compilare i file. vb e creare file. dll</span><span class="sxs-lookup"><span data-stu-id="49e92-111">Compile File.vb and create File.dll</span></span>|`vbc /target:library File.vb`|  
|<span data-ttu-id="49e92-112">Compilare i file. vb e creare My.exe</span><span class="sxs-lookup"><span data-stu-id="49e92-112">Compile File.vb and create My.exe</span></span>|`vbc /out:My.exe File.vb`|  
|<span data-ttu-id="49e92-113">Compilare tutti [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] dei file nella directory corrente, con le ottimizzazioni di in e `DEBUG` simbolo definito, generando File2.exe</span><span class="sxs-lookup"><span data-stu-id="49e92-113">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|<span data-ttu-id="49e92-114">Compilare tutti [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] file nella directory corrente, generando una versione di debug di File2. dll senza visualizzare il logo o avvisi</span><span class="sxs-lookup"><span data-stu-id="49e92-114">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|<span data-ttu-id="49e92-115">Compilare tutti [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] file nella directory corrente in qualcosa. dll</span><span class="sxs-lookup"><span data-stu-id="49e92-115">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory to Something.dll</span></span>|`vbc /target:library /out:Something.dll *.vb`|  
  
 <span data-ttu-id="49e92-116">Durante la compilazione dalla riga di comando, è necessario fare riferimento esplicitamente Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] libreria di runtime tramite il `/reference` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="49e92-116">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="49e92-117">Quando si compila un progetto tramite l'IDE di Visual Studio, è possibile visualizzare informazioni su associato **vbc** comando con le opzioni del compilatore nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="49e92-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="49e92-118">Per visualizzare queste informazioni, aprire il [la finestra di dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il **dettaglio di output di compilazione progetto MSBuild** a **normale** o un livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="49e92-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="49e92-119">Per altre informazioni, vedere [Procedura: Visualizzare, salvare e configurare file di log di compilazione](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="49e92-119">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e92-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49e92-120">See Also</span></span>  
 [<span data-ttu-id="49e92-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="49e92-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="49e92-122">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="49e92-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
