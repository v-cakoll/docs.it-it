---
title: -warn (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 65a6348bb0364d79ed0e69daf3a31ea7aa1bf8ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218871"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="5ed3a-102">-warn (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="5ed3a-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="5ed3a-103">L'opzione **-warn** specifica il livello di avviso da visualizzare nel compilatore.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ed3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ed3a-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="5ed3a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5ed3a-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="5ed3a-106">Livello di avviso da visualizzare per la compilazione: i numeri più bassi mostrano solo gli avvisi con un livello di gravità elevato, i valori più alti mostrano altri avvisi.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="5ed3a-107">I valori validi sono 0-4:</span><span class="sxs-lookup"><span data-stu-id="5ed3a-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="5ed3a-108">Livello avvisi</span><span class="sxs-lookup"><span data-stu-id="5ed3a-108">Warning level</span></span>|<span data-ttu-id="5ed3a-109">Significato</span><span class="sxs-lookup"><span data-stu-id="5ed3a-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="5ed3a-110">0</span><span class="sxs-lookup"><span data-stu-id="5ed3a-110">0</span></span>|<span data-ttu-id="5ed3a-111">Disattiva l'emissione di tutti i messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="5ed3a-112">1</span><span class="sxs-lookup"><span data-stu-id="5ed3a-112">1</span></span>|<span data-ttu-id="5ed3a-113">Visualizza i messaggi di avviso gravi.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="5ed3a-114">2</span><span class="sxs-lookup"><span data-stu-id="5ed3a-114">2</span></span>|<span data-ttu-id="5ed3a-115">Visualizza gli avvisi di livello 1 oltre ad alcuni avvisi meno gravi, ad esempio gli avvisi relativi ai membri di classi nascosti.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="5ed3a-116">3</span><span class="sxs-lookup"><span data-stu-id="5ed3a-116">3</span></span>|<span data-ttu-id="5ed3a-117">Visualizza gli avvisi di livello 2 oltre ad alcuni avvisi meno gravi, ad esempio gli avvisi relativi alle espressioni che restituiscono sempre `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="5ed3a-118">4 (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="5ed3a-118">4 (the default)</span></span>|<span data-ttu-id="5ed3a-119">Visualizza tutti gli avvisi di livello 3 oltre ad avvisi informativi.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ed3a-120">Note</span><span class="sxs-lookup"><span data-stu-id="5ed3a-120">Remarks</span></span>  
 <span data-ttu-id="5ed3a-121">Per ottenere informazioni su un errore o un avviso, è possibile cercare il codice di errore nell'indice della Guida.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="5ed3a-122">Per altri modi per ottenere informazioni su un errore o un avviso, vedere [Errori del compilatore C#](../../../csharp/language-reference/compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="5ed3a-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="5ed3a-123">Usare [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) per considerare tutti gli avvisi come errori.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-123">Use [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="5ed3a-124">Usare [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) per disabilitare avvisi specifici.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-124">Use [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="5ed3a-125">**-w** è la versione abbreviata di **-warn**.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5ed3a-126">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5ed3a-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="5ed3a-127">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-127">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="5ed3a-128">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-128">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="5ed3a-129">Modificare la proprietà **Livello avvisi**.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="5ed3a-130">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ed3a-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ed3a-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ed3a-131">Example</span></span>  
 <span data-ttu-id="5ed3a-132">Compilare `in.cs` e fare in modo che il compilatore visualizzi solo gli avvisi di livello 1:</span><span class="sxs-lookup"><span data-stu-id="5ed3a-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ed3a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ed3a-133">See Also</span></span>  
 [<span data-ttu-id="5ed3a-134">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="5ed3a-134">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="5ed3a-135">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="5ed3a-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
