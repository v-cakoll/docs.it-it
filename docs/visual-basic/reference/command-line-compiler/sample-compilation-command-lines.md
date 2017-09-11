---
title: Esempio di righe di comando di compilazione (Visual Basic) | Documenti di Microsoft
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
- command line, compilers
- compilation, command-line
- command-line compilers
- compiling source code, from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e58006c05f498ec1a9dbf5194fbc9bcdd281ab63
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="4e3b2-102">Esempi di righe di comando di compilazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e3b2-102">Sample Compilation Command Lines (Visual Basic)</span></span>
<span data-ttu-id="4e3b2-103">In alternativa alla compilazione [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programmi dall'interno [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], è possibile compilare dalla riga di comando per generare file di libreria a collegamento dinamico (DLL) o eseguibili (.exe).</span><span class="sxs-lookup"><span data-stu-id="4e3b2-103">As an alternative to compiling [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programs from within [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="4e3b2-104">Il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore da riga di comando supporta un set completo di opzioni che controllano i file di input e outpui, assembly e il debug e le opzioni per il preprocessore.</span><span class="sxs-lookup"><span data-stu-id="4e3b2-104">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="4e3b2-105">Ogni opzione è disponibile in due formati intercambiabili: `-``option` e `/``option`.</span><span class="sxs-lookup"><span data-stu-id="4e3b2-105">Each option is available in two interchangeable forms: `-``option` and `/``option`.</span></span> <span data-ttu-id="4e3b2-106">Questa documentazione viene visualizzato soltanto il `/``option` form.</span><span class="sxs-lookup"><span data-stu-id="4e3b2-106">This documentation shows only the `/``option` form.</span></span>  
  
 <span data-ttu-id="4e3b2-107">Nella tabella seguente sono elencate alcune righe di comando di esempio che è possibile modificare per uso personale.</span><span class="sxs-lookup"><span data-stu-id="4e3b2-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="4e3b2-108">Per</span><span class="sxs-lookup"><span data-stu-id="4e3b2-108">To</span></span>|<span data-ttu-id="4e3b2-109">Usare</span><span class="sxs-lookup"><span data-stu-id="4e3b2-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="4e3b2-110">Compilare i file. vb e creare File.exe</span><span class="sxs-lookup"><span data-stu-id="4e3b2-110">Compile File.vb and create File.exe</span></span>|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="4e3b2-111">Compilare i file. vb e creare file. dll</span><span class="sxs-lookup"><span data-stu-id="4e3b2-111">Compile File.vb and create File.dll</span></span>|`vbc /target:library File.vb`|  
|<span data-ttu-id="4e3b2-112">Compilare i file. vb e creare My.exe</span><span class="sxs-lookup"><span data-stu-id="4e3b2-112">Compile File.vb and create My.exe</span></span>|`vbc /out:My.exe File.vb`|  
|<span data-ttu-id="4e3b2-113">Compilare tutti [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] file nella directory corrente, con le ottimizzazioni e `DEBUG` simbolo definito, generando File2.exe</span><span class="sxs-lookup"><span data-stu-id="4e3b2-113">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|<span data-ttu-id="4e3b2-114">Compilare tutti [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] file nella directory corrente, generando una versione di debug di File2. dll senza visualizzare il logo o avvisi</span><span class="sxs-lookup"><span data-stu-id="4e3b2-114">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|<span data-ttu-id="4e3b2-115">Compilare tutti [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] file nella directory corrente in qualcosa. dll</span><span class="sxs-lookup"><span data-stu-id="4e3b2-115">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory to Something.dll</span></span>|`vbc /target:library /out:Something.dll *.vb`|  
  
 <span data-ttu-id="4e3b2-116">Durante la compilazione dalla riga di comando, è necessario fare esplicitamente riferimento Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] libreria di runtime tramite il `/reference` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="4e3b2-116">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="4e3b2-117">Quando si compila un progetto utilizzando l'IDE di Visual Studio, è possibile visualizzare informazioni su associata **vbc** comando con le opzioni del compilatore nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="4e3b2-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="4e3b2-118">Per visualizzare queste informazioni, aprire il [la finestra di dialogo Opzioni, progetti e soluzioni, compila ed Esegui](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il **livello di dettaglio di output di compilazione progetto MSBuild** a **normale** o un livello di dettaglio superiore.</span><span class="sxs-lookup"><span data-stu-id="4e3b2-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="4e3b2-119">Per altre informazioni, vedere [Procedura: Visualizzare, salvare e configurare file di log di compilazione](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="4e3b2-119">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3b2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e3b2-120">See Also</span></span>  
 <span data-ttu-id="4e3b2-121">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e3b2-121">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="4e3b2-122"> [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span><span class="sxs-lookup"><span data-stu-id="4e3b2-122"> [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span></span>
