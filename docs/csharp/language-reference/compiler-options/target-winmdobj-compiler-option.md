---
title: -target:winmdobj (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3967f7f9326652271ce55aa286e9f42f94dee775
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="targetwinmdobj-c-compiler-options"></a><span data-ttu-id="6feda-102">/target:winmdobj (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="6feda-102">/target:winmdobj (C# Compiler Options)</span></span>
<span data-ttu-id="6feda-103">Se si usa l'opzione del compilatore **/target:winmdobj**, viene creato un file intermedio con estensione winmdobj che è possibile convertire in un file binario di Windows Runtime (winmd).</span><span class="sxs-lookup"><span data-stu-id="6feda-103">If you use the **/target:winmdobj** compiler option, the compiler creates an intermediate .winmdobj file that you can convert to a Windows Runtime binary (.winmd) file.</span></span> <span data-ttu-id="6feda-104">Il file con estensione winmd può quindi essere utilizzato dai programmi C++ e JavaScript, oltre ai programmi di linguaggi gestiti.</span><span class="sxs-lookup"><span data-stu-id="6feda-104">The .winmd file can then be consumed by JavaScript and C++ programs, in addition to managed language programs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6feda-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6feda-105">Syntax</span></span>  
  
```console  
/target:winmdobj  
```  
  
## <a name="remarks"></a><span data-ttu-id="6feda-106">Note</span><span class="sxs-lookup"><span data-stu-id="6feda-106">Remarks</span></span>  
 <span data-ttu-id="6feda-107">L'impostazione **winmdobj** segnala al compilatore che è richiesto un modulo intermedio.</span><span class="sxs-lookup"><span data-stu-id="6feda-107">The **winmdobj** setting signals to the compiler that an intermediate module is required.</span></span> <span data-ttu-id="6feda-108">In risposta, Visual Studio consente di compilare la libreria di classi C# come file con estensione winmdobj.</span><span class="sxs-lookup"><span data-stu-id="6feda-108">In response, Visual Studio compiles the C# class library as a .winmdobj file.</span></span> <span data-ttu-id="6feda-109">Il file con estensione winmdobj può quindi essere inserito dallo strumento di esportazione <xref:Microsoft.Build.Tasks.WinMDExp> per produrre un file di metadati Windows (winmd).</span><span class="sxs-lookup"><span data-stu-id="6feda-109">The .winmdobj file can then be fed through the <xref:Microsoft.Build.Tasks.WinMDExp> export tool to produce a Windows metadata (.winmd) file.</span></span> <span data-ttu-id="6feda-110">Il file con estensione winmd contiene il codice della libreria originale e i metadati di WinMD utilizzati da JavaScript o C++ e da Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="6feda-110">The .winmd file contains both the code from the original library and the WinMD metadata that is used by JavaScript or C++ and by the Windows Runtime.</span></span>  
  
 <span data-ttu-id="6feda-111">L'output di un file compilato usando l'opzione del compilatore **/target:winmdobj** è progettato per essere usato solo come input dell'utilità di esportazione WimMDExp. Al file con estensione winmdobj non viene fatto riferimento direttamente.</span><span class="sxs-lookup"><span data-stu-id="6feda-111">The output of a file that’s compiled by using the **/target:winmdobj** compiler option is designed to be used only as input for the WimMDExp export tool; the .winmdobj file itself isn’t referenced directly.</span></span>  
  
 <span data-ttu-id="6feda-112">A meno che non si usi l'opzione [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del primo file di input.</span><span class="sxs-lookup"><span data-stu-id="6feda-112">Unless you use the [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span> <span data-ttu-id="6feda-113">Non è richiesto un metodo [principale](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="6feda-113">A [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method isn’t required.</span></span>  
  
 <span data-ttu-id="6feda-114">Se si specifica l'opzione /target:winmdobj da un prompt dei comandi, tutti i file fino alla successiva opzione **/out** o [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) vengono usati per creare il programma per Windows.</span><span class="sxs-lookup"><span data-stu-id="6feda-114">If you specify the /target:winmdobj option at a command prompt, all files until the next **/out** or [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) option are used to create the Windows program.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a><span data-ttu-id="6feda-115">Per impostare l'opzione del compilatore nell'IDE di Visual Studio per un'applicazione Windows Store</span><span class="sxs-lookup"><span data-stu-id="6feda-115">To set this compiler option in the Visual Studio IDE for a Windows Store app</span></span>  
  
1.  <span data-ttu-id="6feda-116">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6feda-116">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="6feda-117">Scegliere la scheda **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="6feda-117">Choose the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="6feda-118">Nell'elenco **Tipo di output** scegliere **File WinMD**.</span><span class="sxs-lookup"><span data-stu-id="6feda-118">In the **Output type** list, choose **WinMD File**.</span></span>  
  
     <span data-ttu-id="6feda-119">L'opzione **File WinMD** è disponibile solo per i modelli di applicazione [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6feda-119">The **WinMD File** option is available only for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] app templates.</span></span>  
  
 <span data-ttu-id="6feda-120">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="6feda-120">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6feda-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="6feda-121">Example</span></span>  
 <span data-ttu-id="6feda-122">Il seguente comando consente di compilare `filename.cs` in un file intermedio con estensione winmdobj.</span><span class="sxs-lookup"><span data-stu-id="6feda-122">The following command compiles `filename.cs` into an intermediate .winmdobj file.</span></span>  
  
```console  
csc /target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="6feda-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6feda-123">See Also</span></span>  
 <span data-ttu-id="6feda-124">[-target (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="6feda-124">[/target (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-compiler-option.md) </span></span>  
 [<span data-ttu-id="6feda-125">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="6feda-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

