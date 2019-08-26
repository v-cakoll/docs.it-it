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
ms.openlocfilehash: 66c78ee56c9d5153b5b878b2e695ad4ee6bffe0b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606269"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="884f7-102">-warnaserror (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="884f7-102">-warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="884f7-103">L'opzione **-warnaserror+** considera tutti gli avvisi come errori</span><span class="sxs-lookup"><span data-stu-id="884f7-103">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="884f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="884f7-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="884f7-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="884f7-105">Remarks</span></span>  
 <span data-ttu-id="884f7-106">I messaggi che in genere vengono segnalati come avvisi sono invece segnalati come errori e il processo di compilazione viene interrotto (non viene compilato alcun file di output).</span><span class="sxs-lookup"><span data-stu-id="884f7-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="884f7-107">Per impostazione predefinita, l'opzione **-warnaserror-** è attiva e fa in modo che gli avvisi non impediscano la generazione di un file di output.</span><span class="sxs-lookup"><span data-stu-id="884f7-107">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="884f7-108">**-warnaserror**, che equivale a **-warnaserror+** , fa in modo che gli avvisi vengano considerati errori.</span><span class="sxs-lookup"><span data-stu-id="884f7-108">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="884f7-109">Facoltativamente, se si vuole che solo determinati avvisi vengano considerati errori, è possibile specificare un elenco delimitato da virgole di numeri di avvisi da considerare errori.</span><span class="sxs-lookup"><span data-stu-id="884f7-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
 <span data-ttu-id="884f7-110">Usare [-warn](./warn-compiler-option.md) per specificare il livello degli avvisi da visualizzare nel compilatore.</span><span class="sxs-lookup"><span data-stu-id="884f7-110">Use [-warn](./warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="884f7-111">Usare [-nowarn](./nowarn-compiler-option.md) per disabilitare avvisi specifici.</span><span class="sxs-lookup"><span data-stu-id="884f7-111">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="884f7-112">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="884f7-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="884f7-113">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="884f7-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="884f7-114">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="884f7-114">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="884f7-115">Modificare la proprietà **Considera gli avvisi come errori**.</span><span class="sxs-lookup"><span data-stu-id="884f7-115">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="884f7-116">Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span><span class="sxs-lookup"><span data-stu-id="884f7-116">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="884f7-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="884f7-117">Example</span></span>  
 <span data-ttu-id="884f7-118">Compilare `in.cs` e fare in modo che il compilatore non visualizzi gli avvisi:</span><span class="sxs-lookup"><span data-stu-id="884f7-118">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="884f7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="884f7-119">See also</span></span>

- [<span data-ttu-id="884f7-120">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="884f7-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="884f7-121">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="884f7-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
