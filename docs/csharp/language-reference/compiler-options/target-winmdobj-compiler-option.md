---
title: -target:winmdobj (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 444fcd69db327ea9d9c3dc739b42520bb9472c4d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="-targetwinmdobj-c-compiler-options"></a><span data-ttu-id="7d169-102">-target:winmdobj (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="7d169-102">-target:winmdobj (C# Compiler Options)</span></span>
<span data-ttu-id="7d169-103">Se si usa l'opzione del compilatore **-target:winmdobj**, viene creato un file intermedio con estensione winmdobj che è possibile convertire in un file binario di Windows Runtime (con estensione winmd).</span><span class="sxs-lookup"><span data-stu-id="7d169-103">If you use the **-target:winmdobj** compiler option, the compiler creates an intermediate .winmdobj file that you can convert to a Windows Runtime binary (.winmd) file.</span></span> <span data-ttu-id="7d169-104">Il file con estensione winmd può quindi essere utilizzato dai programmi C++ e JavaScript, oltre ai programmi di linguaggi gestiti.</span><span class="sxs-lookup"><span data-stu-id="7d169-104">The .winmd file can then be consumed by JavaScript and C++ programs, in addition to managed language programs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d169-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d169-105">Syntax</span></span>  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a><span data-ttu-id="7d169-106">Note</span><span class="sxs-lookup"><span data-stu-id="7d169-106">Remarks</span></span>  
 <span data-ttu-id="7d169-107">L'impostazione **winmdobj** segnala al compilatore che è richiesto un modulo intermedio.</span><span class="sxs-lookup"><span data-stu-id="7d169-107">The **winmdobj** setting signals to the compiler that an intermediate module is required.</span></span> <span data-ttu-id="7d169-108">In risposta, Visual Studio consente di compilare la libreria di classi C# come file con estensione winmdobj.</span><span class="sxs-lookup"><span data-stu-id="7d169-108">In response, Visual Studio compiles the C# class library as a .winmdobj file.</span></span> <span data-ttu-id="7d169-109">Il file con estensione winmdobj può quindi essere inserito dallo strumento di esportazione <xref:Microsoft.Build.Tasks.WinMDExp> per produrre un file di metadati Windows (winmd).</span><span class="sxs-lookup"><span data-stu-id="7d169-109">The .winmdobj file can then be fed through the <xref:Microsoft.Build.Tasks.WinMDExp> export tool to produce a Windows metadata (.winmd) file.</span></span> <span data-ttu-id="7d169-110">Il file con estensione winmd contiene il codice della libreria originale e i metadati di WinMD utilizzati da JavaScript o C++ e da Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="7d169-110">The .winmd file contains both the code from the original library and the WinMD metadata that is used by JavaScript or C++ and by the Windows Runtime.</span></span>  
  
 <span data-ttu-id="7d169-111">L'output di un file compilato usando l'opzione del compilatore **-target:winmdobj** è progettato per essere usato solo come input dell'utilità di esportazione WimMDExp. Al file con estensione winmdobj non viene fatto riferimento direttamente.</span><span class="sxs-lookup"><span data-stu-id="7d169-111">The output of a file that’s compiled by using the **-target:winmdobj** compiler option is designed to be used only as input for the WimMDExp export tool; the .winmdobj file itself isn’t referenced directly.</span></span>  
  
 <span data-ttu-id="7d169-112">A meno che non si usi l'opzione [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del primo file di input.</span><span class="sxs-lookup"><span data-stu-id="7d169-112">Unless you use the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span> <span data-ttu-id="7d169-113">Non è richiesto un metodo [principale](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="7d169-113">A [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method isn’t required.</span></span>  
  
 <span data-ttu-id="7d169-114">Se si specifica l'opzione -target:winmdobj al prompt dei comandi, tutti i file fino alla successiva opzione **-out** o [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) vengono usati per creare il programma per Windows.</span><span class="sxs-lookup"><span data-stu-id="7d169-114">If you specify the -target:winmdobj option at a command prompt, all files until the next **-out** or [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) option are used to create the Windows program.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a><span data-ttu-id="7d169-115">Per impostare l'opzione del compilatore nell'IDE di Visual Studio per un'applicazione Windows Store</span><span class="sxs-lookup"><span data-stu-id="7d169-115">To set this compiler option in the Visual Studio IDE for a Windows Store app</span></span>  
  
1.  <span data-ttu-id="7d169-116">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7d169-116">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="7d169-117">Scegliere la scheda **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="7d169-117">Choose the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="7d169-118">Nell'elenco **Tipo di output** scegliere **File WinMD**.</span><span class="sxs-lookup"><span data-stu-id="7d169-118">In the **Output type** list, choose **WinMD File**.</span></span>  
  
     <span data-ttu-id="7d169-119">L'opzione **File WinMD** è disponibile solo per i modelli di applicazione [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d169-119">The **WinMD File** option is available only for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] app templates.</span></span>  
  
 <span data-ttu-id="7d169-120">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d169-120">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d169-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d169-121">Example</span></span>  
 <span data-ttu-id="7d169-122">Il seguente comando consente di compilare `filename.cs` in un file intermedio con estensione winmdobj.</span><span class="sxs-lookup"><span data-stu-id="7d169-122">The following command compiles `filename.cs` into an intermediate .winmdobj file.</span></span>  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d169-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d169-123">See Also</span></span>  
 [<span data-ttu-id="7d169-124">-target (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="7d169-124">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="7d169-125">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="7d169-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
