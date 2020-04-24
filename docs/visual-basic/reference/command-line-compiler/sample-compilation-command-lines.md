---
title: Esempi di righe di comando di compilazione
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 27a20a5a3525353ffbced729b8ac9c98b3e48fc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350847"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="89cc0-102">Righe di comando di compilazione di esempio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89cc0-102">Sample compilation command lines (Visual Basic)</span></span>

<span data-ttu-id="89cc0-103">In alternativa alla compilazione di Visual Basic programmi da Visual Studio, è possibile eseguire la compilazione dalla riga di comando per produrre file eseguibili (exe) o file dll (Dynamic-Link Library).</span><span class="sxs-lookup"><span data-stu-id="89cc0-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>

<span data-ttu-id="89cc0-104">Il Visual Basic compilatore della riga di comando supporta un set completo di opzioni che controllano i file di input e di output, gli assembly e le opzioni di debug e preprocessore.</span><span class="sxs-lookup"><span data-stu-id="89cc0-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="89cc0-105">Ogni opzione è disponibile in due forme intercambiabili: `-option` e. `/option`</span><span class="sxs-lookup"><span data-stu-id="89cc0-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="89cc0-106">Questa documentazione Mostra solo il `-option` modulo.</span><span class="sxs-lookup"><span data-stu-id="89cc0-106">This documentation shows only the `-option` form.</span></span>

<span data-ttu-id="89cc0-107">La tabella seguente elenca alcune righe di comando di esempio che è possibile modificare per uso personale.</span><span class="sxs-lookup"><span data-stu-id="89cc0-107">The following table lists some sample command lines you can modify for your own use.</span></span>

|<span data-ttu-id="89cc0-108">A</span><span class="sxs-lookup"><span data-stu-id="89cc0-108">To</span></span>|<span data-ttu-id="89cc0-109">Uso</span><span class="sxs-lookup"><span data-stu-id="89cc0-109">Use</span></span>|
|--------|---------|
|<span data-ttu-id="89cc0-110">Compilare file. vb e creare file. exe</span><span class="sxs-lookup"><span data-stu-id="89cc0-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|<span data-ttu-id="89cc0-111">Compilare file. vb e creare file. dll</span><span class="sxs-lookup"><span data-stu-id="89cc0-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|
|<span data-ttu-id="89cc0-112">Compilare file. vb e creare My. exe</span><span class="sxs-lookup"><span data-stu-id="89cc0-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|
|<span data-ttu-id="89cc0-113">Compilare file. vb e creare una libreria e un assembly di riferimento denominato file. dll</span><span class="sxs-lookup"><span data-stu-id="89cc0-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="89cc0-114">Compila tutti i file Visual Basic nella directory corrente, con le ottimizzazioni su e `DEBUG` il simbolo definito, producendo file2. exe</span><span class="sxs-lookup"><span data-stu-id="89cc0-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|<span data-ttu-id="89cc0-115">Compila tutti i file di Visual Basic nella directory corrente, producendo una versione di debug di file2. dll senza visualizzare il logo o gli avvisi</span><span class="sxs-lookup"><span data-stu-id="89cc0-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|<span data-ttu-id="89cc0-116">Compila tutti i file di Visual Basic della directory corrente in something. dll</span><span class="sxs-lookup"><span data-stu-id="89cc0-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> <span data-ttu-id="89cc0-117">Quando si compila un progetto usando l'IDE di Visual Studio, è possibile visualizzare informazioni sul comando **vbc** associato con le relative opzioni del compilatore nella finestra output.</span><span class="sxs-lookup"><span data-stu-id="89cc0-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="89cc0-118">Per visualizzare queste informazioni, aprire la finestra di [dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il livello di **dettaglio dell'output di compilazione del progetto MSBuild** su **normale** o su un livello di dettaglio superiore.</span><span class="sxs-lookup"><span data-stu-id="89cc0-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>

## <a name="see-also"></a><span data-ttu-id="89cc0-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="89cc0-119">See also</span></span>

- [<span data-ttu-id="89cc0-120">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89cc0-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="89cc0-121">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="89cc0-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
