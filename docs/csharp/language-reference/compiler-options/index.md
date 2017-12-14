---
title: Opzioni del compilatore C#
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 28878fca5bccf23f906395298c8b2b5b7499fd40
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="c-compiler-options"></a><span data-ttu-id="eb2ca-102">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="eb2ca-102">C# Compiler Options</span></span>
<span data-ttu-id="eb2ca-103">Tramite il compilatore vengono generati file eseguibili (con estensione exe), librerie a collegamento dinamico (con estensione dll) o moduli di codice (con estensione netmodule).</span><span class="sxs-lookup"><span data-stu-id="eb2ca-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>  
  
 <span data-ttu-id="eb2ca-104">Ogni opzione del compilatore è disponibile in due forme: **-opzione** e **(opzione)**.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="eb2ca-105">La documentazione mostra solo la forma **/opzione**.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-105">The documentation only shows the **/option** form.</span></span>  
  
 <span data-ttu-id="eb2ca-106">In Visual Studio, le opzioni del compilatore vengono impostate nel file web.config.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-106">In Visual Studio, you set compiler options in the web.config file.</span></span> <span data-ttu-id="eb2ca-107">Per altre informazioni, vedere [Elemento \<compiler>](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="eb2ca-107">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb2ca-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="eb2ca-108">In This Section</span></span>  
 [<span data-ttu-id="eb2ca-109">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="eb2ca-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 <span data-ttu-id="eb2ca-110">Informazioni sulla creazione di un'applicazione Visual C# dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-110">Information about building a Visual C# application from the command line.</span></span>  
  
 [<span data-ttu-id="eb2ca-111">Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eb2ca-111">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 <span data-ttu-id="eb2ca-112">Descrizione della procedura per eseguire vsvars32. bat per abilitare le compilazioni dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-112">Provides steps for running vsvars32.bat  to enable command-line builds.</span></span>  
  
 [<span data-ttu-id="eb2ca-113">Opzioni del compilatore C# elencate per categoria</span><span class="sxs-lookup"><span data-stu-id="eb2ca-113">C# Compiler Options Listed by Category</span></span>](../../../csharp/language-reference/compiler-options/listed-by-category.md)  
 <span data-ttu-id="eb2ca-114">Elenco organizzato per categorie delle opzioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-114">A categorical listing of the compiler options.</span></span>  
  
 [<span data-ttu-id="eb2ca-115">Opzioni del compilatore C# in ordine alfabetico</span><span class="sxs-lookup"><span data-stu-id="eb2ca-115">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 <span data-ttu-id="eb2ca-116">Elenco alfabetico delle opzioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-116">An alphabetical listing of the compiler options.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eb2ca-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="eb2ca-117">Related Sections</span></span>  
 [<span data-ttu-id="eb2ca-118">Pagina Compilazione, Progettazione progetti</span><span class="sxs-lookup"><span data-stu-id="eb2ca-118">Build Page, Project Designer</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)  
 <span data-ttu-id="eb2ca-119">Impostazione delle proprietà che controllano le modalità di compilazione, generazione e debug del progetto.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-119">Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="eb2ca-120">Include informazioni sulle istruzioni di compilazione personalizzate nei progetti Visual C#.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-120">Includes information about custom build steps in Visual C# projects.</span></span>  
  
 [<span data-ttu-id="eb2ca-121">Compilazioni predefinite e personalizzate</span><span class="sxs-lookup"><span data-stu-id="eb2ca-121">Default and Custom Builds</span></span>](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 <span data-ttu-id="eb2ca-122">Informazioni sui tipi e le configurazioni di compilazione.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-122">Information on build types and configurations.</span></span>  
  
 [<span data-ttu-id="eb2ca-123">Preparazione e gestione delle compilazioni</span><span class="sxs-lookup"><span data-stu-id="eb2ca-123">Preparing and Managing Builds</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="eb2ca-124">Procedure per la compilazione nell'ambiente di sviluppo di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="eb2ca-124">Procedures for building within the Visual Studio development environment.</span></span>
