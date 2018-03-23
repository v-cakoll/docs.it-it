---
title: Esempi di righe di comando di compilazione (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf20e2916efd2eb10065be22c319e34ddb2bda9a
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="37853-102">Esempi di righe di comando compilazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37853-102">Sample compilation command lines (Visual Basic)</span></span>
<span data-ttu-id="37853-103">In alternativa alla compilazione dei programmi Visual Basic dall'interno [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], è possibile compilare dalla riga di comando per generare file di libreria a collegamento dinamico (DLL) o file eseguibile (.exe).</span><span class="sxs-lookup"><span data-stu-id="37853-103">As an alternative to compiling Visual Basic programs from within [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="37853-104">Il compilatore della riga di comando di Visual Basic supporta un set completo di opzioni che controllano l'input e output di file, gli assembly, debug e le opzioni per il preprocessore.</span><span class="sxs-lookup"><span data-stu-id="37853-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="37853-105">Ogni opzione è disponibile in due formati intercambiabili: `-option` e `/option`.</span><span class="sxs-lookup"><span data-stu-id="37853-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="37853-106">Questa documentazione viene visualizzato soltanto il `-option` form.</span><span class="sxs-lookup"><span data-stu-id="37853-106">This documentation shows only the `-option` form.</span></span>  
  
 <span data-ttu-id="37853-107">Nella tabella seguente sono elencati alcuni esempi di righe di comando che è possibile modificare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="37853-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="37853-108">A</span><span class="sxs-lookup"><span data-stu-id="37853-108">To</span></span>|<span data-ttu-id="37853-109">Usa</span><span class="sxs-lookup"><span data-stu-id="37853-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="37853-110">Compilare i file. vb e creare File.exe</span><span class="sxs-lookup"><span data-stu-id="37853-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="37853-111">Compilare i file. vb e creare file. dll</span><span class="sxs-lookup"><span data-stu-id="37853-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|  
|<span data-ttu-id="37853-112">Compilare i file. vb e creare My.exe</span><span class="sxs-lookup"><span data-stu-id="37853-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|  
|<span data-ttu-id="37853-113">Compilare i file. vb e creare una libreria sia un assembly di riferimento denominata DLL</span><span class="sxs-lookup"><span data-stu-id="37853-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="37853-114">Compilare tutti i file di Visual Basic nella directory corrente, con le ottimizzazioni in e `DEBUG` simbolo definito, generando File2.exe</span><span class="sxs-lookup"><span data-stu-id="37853-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|<span data-ttu-id="37853-115">Compilare tutti i file di Visual Basic nella directory corrente, generando una versione di debug di File2 senza visualizzare il logo o gli avvisi</span><span class="sxs-lookup"><span data-stu-id="37853-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|<span data-ttu-id="37853-116">Compilare tutti i file di Visual Basic nella directory corrente in qualcosa. dll</span><span class="sxs-lookup"><span data-stu-id="37853-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  <span data-ttu-id="37853-117">Quando si compila un progetto tramite l'IDE di Visual Studio, è possibile visualizzare informazioni su associato **vbc** comando con le opzioni del compilatore nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="37853-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="37853-118">Per visualizzare queste informazioni, aprire il [la finestra di dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il **dettaglio di output di compilazione progetto MSBuild** a **normale** o un livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="37853-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="37853-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37853-119">See Also</span></span>  
 [<span data-ttu-id="37853-120">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37853-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="37853-121">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="37853-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
