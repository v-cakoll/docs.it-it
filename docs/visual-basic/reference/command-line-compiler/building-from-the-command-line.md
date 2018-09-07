---
title: Compilazione dalla riga di comando (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: 89bcd6e0e7c1cc867bf853dc9bbe96628942ace2
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078941"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="d5c4d-102">Compilazione dalla riga di comando (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5c4d-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="d5c4d-103">Un progetto Visual Basic è costituito da uno o più file di origine separato.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="d5c4d-104">Durante il processo è noto come la compilazione, questi file vengono riuniti in un pacchetto, ovvero un singolo file eseguibile che può essere eseguito come un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 <span data-ttu-id="d5c4d-105">Visual Basic fornisce un compilatore da riga di comando come alternativa alla compilazione dei programmi dall'interno l'ambiente di sviluppo integrato (IDE) di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="d5c4d-106">Il compilatore della riga di comando è progettato per le situazioni in cui non richiedono il set completo di funzionalità nell'IDE, ad esempio, quando utilizzano o scrittura per i computer con spazio di archiviazione o memoria limitate sul sistema.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
  <span data-ttu-id="d5c4d-107">Per compilare i file di origine nell'IDE di Visual Studio, scegliere il **compilare** dalle **compilazione** menu.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="d5c4d-108">Quando si compila i file di progetto usando l'IDE di Visual Studio, è possibile visualizzare informazioni sull'oggetto associato **vbc** comando e le opzioni nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="d5c4d-109">Per visualizzare queste informazioni, aprire il [finestra di dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il **livello di dettaglio output di compilazione progetto MSBuild** al **normale** o un livello di dettaglio maggiore.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="d5c4d-110">Per altre informazioni, vedere [Procedura: Visualizzare, salvare e configurare file di log di compilazione](https://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="d5c4d-110">For more information, see [How to: View, Save, and Configure Build Log Files](https://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
 <span data-ttu-id="d5c4d-111">È possibile compilare i file di progetto (con estensione vbproj) in un prompt dei comandi usando MSBuild.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="d5c4d-112">Per altre informazioni, vedere [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) e [procedura dettagliata: uso di MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span><span class="sxs-lookup"><span data-stu-id="d5c4d-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5c4d-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d5c4d-113">In This Section</span></span>  
 [<span data-ttu-id="d5c4d-114">Procedura:Richiamare il compilatore da riga di comando</span><span class="sxs-lookup"><span data-stu-id="d5c4d-114">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="d5c4d-115">Viene descritto come richiamare il compilatore della riga di comando al prompt di MS-DOS o da una sottodirectory specifica.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="d5c4d-116">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="d5c4d-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="d5c4d-117">Fornisce un elenco di righe di comando di esempio che è possibile modificare per uso personale.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-117">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d5c4d-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="d5c4d-118">Related Sections</span></span>  
 [<span data-ttu-id="d5c4d-119">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d5c4d-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="d5c4d-120">Fornisce elenchi di opzioni del compilatore, organizzati in ordine alfabetico o per utilizzo generico.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="d5c4d-121">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="d5c4d-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="d5c4d-122">Viene descritto come compilare determinate sezioni di codice.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-122">Describes how to compile particular sections of code.</span></span>  
  
 <span data-ttu-id="d5c4d-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) (Compilazione e pulizia di progetti e soluzioni in Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d5c4d-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)</span></span>  
 <span data-ttu-id="d5c4d-124">Viene descritto come organizzare ciò che verrà incluso nella build diverse, scegliere le proprietà del progetto e assicurarsi che i progetti di compilazione nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="d5c4d-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
