---
title: Compilazione dalla riga di comando
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
ms.openlocfilehash: ec6ae3328c2042af950d1ee78a33d3de97219f10
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414298"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="fbe70-102">Compilazione dalla riga di comando (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fbe70-102">Building from the Command Line (Visual Basic)</span></span>

<span data-ttu-id="fbe70-103">Un progetto Visual Basic è costituito da uno o più file di origine separati.</span><span class="sxs-lookup"><span data-stu-id="fbe70-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="fbe70-104">Durante il processo noto come compilazione, questi file vengono raggruppati in un unico pacchetto, ovvero un singolo file eseguibile che può essere eseguito come applicazione.</span><span class="sxs-lookup"><span data-stu-id="fbe70-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>

<span data-ttu-id="fbe70-105">Visual Basic fornisce un compilatore da riga di comando come alternativa alla compilazione di programmi dall'interno di Visual Studio Integrated Development Environment (IDE).</span><span class="sxs-lookup"><span data-stu-id="fbe70-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="fbe70-106">Il compilatore da riga di comando è progettato per le situazioni in cui non è necessario il set completo di funzionalità nell'IDE, ad esempio quando si usa o si scrive per computer con memoria di sistema limitata o spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fbe70-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>

<span data-ttu-id="fbe70-107">Per compilare i file di origine dall'IDE di Visual Studio, scegliere il comando **Compila** dal menu **Compila** .</span><span class="sxs-lookup"><span data-stu-id="fbe70-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>

> [!TIP]
> <span data-ttu-id="fbe70-108">Quando si compilano i file di progetto usando l'IDE di Visual Studio, è possibile visualizzare informazioni sul comando **vbc** associato e sulle relative opzioni nella finestra output.</span><span class="sxs-lookup"><span data-stu-id="fbe70-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="fbe70-109">Per visualizzare queste informazioni, aprire la finestra di [dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il livello di **dettaglio dell'output di compilazione del progetto MSBuild** su **normale** o su un livello di dettaglio superiore.</span><span class="sxs-lookup"><span data-stu-id="fbe70-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="fbe70-110">Per altre informazioni, vedere [procedura: visualizzare, salvare e configurare i file di log di compilazione](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span><span class="sxs-lookup"><span data-stu-id="fbe70-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>

<span data-ttu-id="fbe70-111">È possibile compilare file di progetto (con estensione vbproj) da un prompt dei comandi utilizzando MSBuild.</span><span class="sxs-lookup"><span data-stu-id="fbe70-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="fbe70-112">Per altre informazioni, vedere Guida di [riferimento alla riga di comando](/visualstudio/msbuild/msbuild-command-line-reference) e [procedura dettagliata: uso di MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span><span class="sxs-lookup"><span data-stu-id="fbe70-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="fbe70-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="fbe70-113">In This Section</span></span>

<span data-ttu-id="fbe70-114">[Procedura: richiamare il compilatore da riga di comando](how-to-invoke-the-command-line-compiler.md) </span><span class="sxs-lookup"><span data-stu-id="fbe70-114">[How to: Invoke the Command-Line Compiler](how-to-invoke-the-command-line-compiler.md) </span></span>\
<span data-ttu-id="fbe70-115">Viene descritto come richiamare il compilatore da riga di comando al prompt di MS-DOS o da una sottodirectory specifica.</span><span class="sxs-lookup"><span data-stu-id="fbe70-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>

<span data-ttu-id="fbe70-116">[Esempi di righe di comando di compilazione](sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="fbe70-116">[Sample Compilation Command Lines](sample-compilation-command-lines.md) </span></span>\
<span data-ttu-id="fbe70-117">Fornisce un elenco di righe di comando di esempio che è possibile modificare per uso personale.</span><span class="sxs-lookup"><span data-stu-id="fbe70-117">Provides a list of sample command lines that you can modify for your own use.</span></span>

## <a name="related-sections"></a><span data-ttu-id="fbe70-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="fbe70-118">Related Sections</span></span>

<span data-ttu-id="fbe70-119">[Visual Basic compilatore da riga di comando](index.md) </span><span class="sxs-lookup"><span data-stu-id="fbe70-119">[Visual Basic Command-Line Compiler](index.md) </span></span>\
<span data-ttu-id="fbe70-120">Fornisce elenchi di opzioni del compilatore, organizzate in ordine alfabetico o per scopo.</span><span class="sxs-lookup"><span data-stu-id="fbe70-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>

<span data-ttu-id="fbe70-121">[Compilazione condizionale](../../programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="fbe70-121">[Conditional Compilation](../../programming-guide/program-structure/conditional-compilation.md) </span></span>\
<span data-ttu-id="fbe70-122">Viene descritto come compilare sezioni di codice specifiche.</span><span class="sxs-lookup"><span data-stu-id="fbe70-122">Describes how to compile particular sections of code.</span></span>

<span data-ttu-id="fbe70-123">[Compilazione e pulizia di progetti e soluzioni in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="fbe70-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span></span>\
<span data-ttu-id="fbe70-124">Viene descritto come organizzare gli elementi che verranno inclusi in compilazioni diverse, scegliere le proprietà del progetto e assicurarsi che i progetti vengano compilati in base all'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="fbe70-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
