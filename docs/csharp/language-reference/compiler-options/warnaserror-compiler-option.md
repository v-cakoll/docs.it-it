---
title: -warnaserror (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /warnaserror
dev_langs:
- CSharp
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: df29fd760e0e4a002f1b5078d85370a74f322e23
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="warnaserror-c-compiler-options"></a><span data-ttu-id="d94e6-102">/warnaserror (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="d94e6-102">/warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="d94e6-103">L'opzione **/warnaserror+** considera tutti gli avvisi come errori</span><span class="sxs-lookup"><span data-stu-id="d94e6-103">The **/warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d94e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d94e6-104">Syntax</span></span>  
  
```console  
/warnaserror[<U>+</U> | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="d94e6-105">Note</span><span class="sxs-lookup"><span data-stu-id="d94e6-105">Remarks</span></span>  
 <span data-ttu-id="d94e6-106">I messaggi che in genere vengono segnalati come avvisi sono invece segnalati come errori e il processo di compilazione viene interrotto (non viene compilato alcun file di output).</span><span class="sxs-lookup"><span data-stu-id="d94e6-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="d94e6-107">Per impostazione predefinita, è attiva l'opzione **/warnaserror-**, che fa in modo che gli avvisi non impediscano la generazione di un file di output.</span><span class="sxs-lookup"><span data-stu-id="d94e6-107">By default, **/warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="d94e6-108">**/warnaserror**, che equivale a **/warnaserror+**, fa in modo che gli avvisi vengano considerati errori.</span><span class="sxs-lookup"><span data-stu-id="d94e6-108">**/warnaserror**, which is the same as **/warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="d94e6-109">Facoltativamente, se si vuole che solo determinati avvisi vengano considerati errori, è possibile specificare un elenco delimitato da virgole di numeri di avvisi da considerare errori.</span><span class="sxs-lookup"><span data-stu-id="d94e6-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
 <span data-ttu-id="d94e6-110">Usare [/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) per specificare il livello degli avvisi da visualizzare nel compilatore.</span><span class="sxs-lookup"><span data-stu-id="d94e6-110">Use [/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="d94e6-111">Usare [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) per disabilitare determinati avvisi.</span><span class="sxs-lookup"><span data-stu-id="d94e6-111">Use [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="d94e6-112">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d94e6-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="d94e6-113">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="d94e6-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="d94e6-114">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="d94e6-114">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="d94e6-115">Modificare la proprietà **Considera gli avvisi come errori**.</span><span class="sxs-lookup"><span data-stu-id="d94e6-115">Modify the **Treat Warnings As Errors** property.</span></span>  
  
     <span data-ttu-id="d94e6-116">Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="d94e6-116">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d94e6-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="d94e6-117">Example</span></span>  
 <span data-ttu-id="d94e6-118">Compilare `in.cs` e fare in modo che il compilatore non visualizzi gli avvisi:</span><span class="sxs-lookup"><span data-stu-id="d94e6-118">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc /warnaserror in.cs  
csc /warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="d94e6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d94e6-119">See Also</span></span>  
 <span data-ttu-id="d94e6-120">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="d94e6-120">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="d94e6-121">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="d94e6-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

