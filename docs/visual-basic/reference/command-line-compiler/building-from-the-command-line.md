---
title: Compilazione dalla riga di comando (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d982506af2c4f01e80ae5b3862fcbcfff2aa9d99
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="57cb2-102">Compilazione dalla riga di comando (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57cb2-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="57cb2-103">Oggetto [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] progetto è costituito da uno o più file di origine distinta.</span><span class="sxs-lookup"><span data-stu-id="57cb2-103">A [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] project is made up of one or more separate source files.</span></span> <span data-ttu-id="57cb2-104">Durante il processo è noto come compilazione, questi file vengono riuniti in un pacchetto, ovvero un singolo file eseguibile che può essere eseguito come un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="57cb2-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="57cb2-105">fornisce un compilatore da riga di comando come alternativa alla compilazione dei programmi dall'interno di [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] ambiente di sviluppo integrato (IDE).</span><span class="sxs-lookup"><span data-stu-id="57cb2-105"> provides a command-line compiler as an alternative to compiling programs from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrated development environment (IDE).</span></span> <span data-ttu-id="57cb2-106">Il compilatore della riga di comando è progettato per situazioni che non richiedono il set completo di funzionalità nell'IDE, ad esempio, quando utilizzano o scrittura per i computer con sistema limitato della memoria o spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="57cb2-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
 <span data-ttu-id="57cb2-107">Durante la compilazione dalla riga di comando, è necessario fare riferimento esplicitamente Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] libreria di runtime tramite il `/reference` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="57cb2-107">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
 <span data-ttu-id="57cb2-108">Per compilare i file di origine dall'interno di [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] IDE, scegliere il **compilare** comando il **compilare** menu.</span><span class="sxs-lookup"><span data-stu-id="57cb2-108">To compile source files from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="57cb2-109">Quando si compila i file di progetto tramite l'IDE di Visual Studio, è possibile visualizzare informazioni su associato **vbc** comando e le opzioni nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="57cb2-109">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="57cb2-110">Per visualizzare queste informazioni, aprire il [la finestra di dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il **dettaglio di output di compilazione progetto MSBuild** a **normale** o un livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="57cb2-110">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="57cb2-111">Per altre informazioni, vedere [Procedura: Visualizzare, salvare e configurare file di log di compilazione](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="57cb2-111">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
 <span data-ttu-id="57cb2-112">È possibile compilare i file di progetto (con estensione vbproj) in un prompt dei comandi tramite MSBuild.</span><span class="sxs-lookup"><span data-stu-id="57cb2-112">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="57cb2-113">Per ulteriori informazioni, vedere [riferimento della riga di comando](/visualstudio/msbuild/msbuild-command-line-reference) e [procedura dettagliata: uso di MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span><span class="sxs-lookup"><span data-stu-id="57cb2-113">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57cb2-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="57cb2-114">In This Section</span></span>  
 [<span data-ttu-id="57cb2-115">Procedura:Richiamare il compilatore da riga di comando</span><span class="sxs-lookup"><span data-stu-id="57cb2-115">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="57cb2-116">Viene descritto come richiamare il compilatore della riga di comando al prompt di MS-DOS o da una sottodirectory specifica.</span><span class="sxs-lookup"><span data-stu-id="57cb2-116">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="57cb2-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="57cb2-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="57cb2-118">Fornisce un elenco delle righe di comando di esempio che è possibile modificare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="57cb2-118">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="57cb2-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="57cb2-119">Related Sections</span></span>  
 [<span data-ttu-id="57cb2-120">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57cb2-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="57cb2-121">Vengono forniti elenchi di opzioni del compilatore, organizzati in ordine alfabetico in base allo scopo.</span><span class="sxs-lookup"><span data-stu-id="57cb2-121">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="57cb2-122">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="57cb2-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="57cb2-123">Viene descritto come compilare particolari sezioni di codice.</span><span class="sxs-lookup"><span data-stu-id="57cb2-123">Describes how to compile particular sections of code.</span></span>  
  
 <span data-ttu-id="57cb2-124">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) (Compilazione e pulizia di progetti e soluzioni in Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="57cb2-124">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)</span></span>  
 <span data-ttu-id="57cb2-125">Viene descritto come organizzare gli elementi verranno inclusi nelle compilazioni diverse, scegliere le proprietà del progetto e generare i progetti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="57cb2-125">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
