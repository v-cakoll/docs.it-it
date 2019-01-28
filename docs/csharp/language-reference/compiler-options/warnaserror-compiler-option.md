---
title: -warnaserror (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
ms.openlocfilehash: b208f6e4e768e400af203117d185944be285cb72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634610"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="a2fc4-102">-warnaserror (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="a2fc4-102">-warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="a2fc4-103">L'opzione **-warnaserror+** considera tutti gli avvisi come errori</span><span class="sxs-lookup"><span data-stu-id="a2fc4-103">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2fc4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2fc4-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="a2fc4-105">Note</span><span class="sxs-lookup"><span data-stu-id="a2fc4-105">Remarks</span></span>  
 <span data-ttu-id="a2fc4-106">I messaggi che in genere vengono segnalati come avvisi sono invece segnalati come errori e il processo di compilazione viene interrotto (non viene compilato alcun file di output).</span><span class="sxs-lookup"><span data-stu-id="a2fc4-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="a2fc4-107">Per impostazione predefinita, l'opzione **-warnaserror-** è attiva e fa in modo che gli avvisi non impediscano la generazione di un file di output.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-107">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="a2fc4-108">**-warnaserror**, che equivale a **-warnaserror+**, fa in modo che gli avvisi vengano considerati errori.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-108">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="a2fc4-109">Facoltativamente, se si vuole che solo determinati avvisi vengano considerati errori, è possibile specificare un elenco delimitato da virgole di numeri di avvisi da considerare errori.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
 <span data-ttu-id="a2fc4-110">Usare [-warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) per specificare il livello degli avvisi da visualizzare nel compilatore.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-110">Use [-warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="a2fc4-111">Usare [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) per disabilitare avvisi specifici.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-111">Use [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a2fc4-112">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a2fc4-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="a2fc4-113">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="a2fc4-114">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-114">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="a2fc4-115">Modificare la proprietà **Considera gli avvisi come errori**.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-115">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="a2fc4-116">Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-116">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2fc4-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2fc4-117">Example</span></span>  
 <span data-ttu-id="a2fc4-118">Compilare `in.cs` e fare in modo che il compilatore non visualizzi gli avvisi:</span><span class="sxs-lookup"><span data-stu-id="a2fc4-118">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2fc4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2fc4-119">See also</span></span>

- [<span data-ttu-id="a2fc4-120">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="a2fc4-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="a2fc4-121">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="a2fc4-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
