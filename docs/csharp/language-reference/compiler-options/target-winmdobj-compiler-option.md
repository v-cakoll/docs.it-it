---
title: -target:winmdobj (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
ms.openlocfilehash: fe1332f9ed6de9c50c2509e29f22ed7c0e57ade9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606353"
---
# <a name="-targetwinmdobj-c-compiler-options"></a><span data-ttu-id="7f0ed-102">-target:winmdobj (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="7f0ed-102">-target:winmdobj (C# Compiler Options)</span></span>
<span data-ttu-id="7f0ed-103">Se si usa l'opzione del compilatore **-target:winmdobj**, viene creato un file intermedio con estensione winmdobj che è possibile convertire in un file binario di Windows Runtime (con estensione winmd).</span><span class="sxs-lookup"><span data-stu-id="7f0ed-103">If you use the **-target:winmdobj** compiler option, the compiler creates an intermediate .winmdobj file that you can convert to a Windows Runtime binary (.winmd) file.</span></span> <span data-ttu-id="7f0ed-104">Il file con estensione winmd può quindi essere utilizzato dai programmi C++ e JavaScript, oltre ai programmi di linguaggi gestiti.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-104">The .winmd file can then be consumed by JavaScript and C++ programs, in addition to managed language programs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f0ed-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f0ed-105">Syntax</span></span>  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a><span data-ttu-id="7f0ed-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7f0ed-106">Remarks</span></span>  
 <span data-ttu-id="7f0ed-107">L'impostazione **winmdobj** segnala al compilatore che è richiesto un modulo intermedio.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-107">The **winmdobj** setting signals to the compiler that an intermediate module is required.</span></span> <span data-ttu-id="7f0ed-108">In risposta, Visual Studio consente di compilare la libreria di classi C# come file con estensione winmdobj.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-108">In response, Visual Studio compiles the C# class library as a .winmdobj file.</span></span> <span data-ttu-id="7f0ed-109">Il file con estensione winmdobj può quindi essere inserito dallo strumento di esportazione <xref:Microsoft.Build.Tasks.WinMDExp> per produrre un file di metadati Windows (winmd).</span><span class="sxs-lookup"><span data-stu-id="7f0ed-109">The .winmdobj file can then be fed through the <xref:Microsoft.Build.Tasks.WinMDExp> export tool to produce a Windows metadata (.winmd) file.</span></span> <span data-ttu-id="7f0ed-110">Il file con estensione winmd contiene il codice della libreria originale e i metadati di WinMD utilizzati da JavaScript o C++ e da Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-110">The .winmd file contains both the code from the original library and the WinMD metadata that is used by JavaScript or C++ and by the Windows Runtime.</span></span>  
  
 <span data-ttu-id="7f0ed-111">L'output di un file compilato usando l'opzione del compilatore **-target:winmdobj** è progettato per essere usato solo come input dell'utilità di esportazione WimMDExp. Al file con estensione winmdobj non viene fatto riferimento direttamente.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-111">The output of a file that’s compiled by using the **-target:winmdobj** compiler option is designed to be used only as input for the WimMDExp export tool; the .winmdobj file itself isn’t referenced directly.</span></span>  
  
 <span data-ttu-id="7f0ed-112">A meno che non si usi l'opzione [-out](./out-compiler-option.md), il nome del file di output corrisponderà al nome del primo file di input.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-112">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span> <span data-ttu-id="7f0ed-113">Non è richiesto un metodo [principale](../../programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="7f0ed-113">A [Main](../../programming-guide/main-and-command-args/index.md) method isn’t required.</span></span>  
  
 <span data-ttu-id="7f0ed-114">Se si specifica l'opzione -target:winmdobj al prompt dei comandi, tutti i file fino alla successiva opzione **-out** o [-target:module](./target-module-compiler-option.md) vengono usati per creare il programma per Windows.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-114">If you specify the -target:winmdobj option at a command prompt, all files until the next **-out** or [-target:module](./target-module-compiler-option.md) option are used to create the Windows program.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a><span data-ttu-id="7f0ed-115">Per impostare l'opzione del compilatore nell'IDE di Visual Studio per un'applicazione Windows Store</span><span class="sxs-lookup"><span data-stu-id="7f0ed-115">To set this compiler option in the Visual Studio IDE for a Windows Store app</span></span>  
  
1. <span data-ttu-id="7f0ed-116">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-116">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="7f0ed-117">Scegliere la scheda **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-117">Choose the **Application** tab.</span></span>  
  
3. <span data-ttu-id="7f0ed-118">Nell'elenco **Tipo di output** scegliere **File WinMD**.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-118">In the **Output type** list, choose **WinMD File**.</span></span>  
  
     <span data-ttu-id="7f0ed-119">L'opzione **File WinMD** è disponibile solo per i modelli di applicazione [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f0ed-119">The **WinMD File** option is available only for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] app templates.</span></span>  
  
 <span data-ttu-id="7f0ed-120">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-120">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f0ed-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f0ed-121">Example</span></span>  
 <span data-ttu-id="7f0ed-122">Il seguente comando consente di compilare `filename.cs` in un file intermedio con estensione winmdobj.</span><span class="sxs-lookup"><span data-stu-id="7f0ed-122">The following command compiles `filename.cs` into an intermediate .winmdobj file.</span></span>  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f0ed-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f0ed-123">See also</span></span>

- [<span data-ttu-id="7f0ed-124">-target (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="7f0ed-124">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="7f0ed-125">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="7f0ed-125">C# Compiler Options</span></span>](./index.md)
