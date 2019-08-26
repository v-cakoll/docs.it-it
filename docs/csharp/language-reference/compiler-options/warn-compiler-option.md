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
ms.openlocfilehash: 5b05e944a37e16fc1fcc422271be00c09a271a33
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602401"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="887ee-102">-warn (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="887ee-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="887ee-103">L'opzione **-warn** specifica il livello di avviso da visualizzare nel compilatore.</span><span class="sxs-lookup"><span data-stu-id="887ee-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="887ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="887ee-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="887ee-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="887ee-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="887ee-106">Livello di avviso da visualizzare per la compilazione: i valori più bassi visualizzano solo avvisi di gravità alta; i valori alti visualizzano più avvisi.</span><span class="sxs-lookup"><span data-stu-id="887ee-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="887ee-107">I valori validi sono 0-4:</span><span class="sxs-lookup"><span data-stu-id="887ee-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="887ee-108">Livello avvisi</span><span class="sxs-lookup"><span data-stu-id="887ee-108">Warning level</span></span>|<span data-ttu-id="887ee-109">Significato</span><span class="sxs-lookup"><span data-stu-id="887ee-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="887ee-110">0</span><span class="sxs-lookup"><span data-stu-id="887ee-110">0</span></span>|<span data-ttu-id="887ee-111">Disattiva l'emissione di tutti i messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="887ee-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="887ee-112">1</span><span class="sxs-lookup"><span data-stu-id="887ee-112">1</span></span>|<span data-ttu-id="887ee-113">Visualizza i messaggi di avviso gravi.</span><span class="sxs-lookup"><span data-stu-id="887ee-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="887ee-114">2</span><span class="sxs-lookup"><span data-stu-id="887ee-114">2</span></span>|<span data-ttu-id="887ee-115">Visualizza gli avvisi di livello 1 oltre ad alcuni avvisi meno gravi, ad esempio gli avvisi relativi ai membri di classi nascosti.</span><span class="sxs-lookup"><span data-stu-id="887ee-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="887ee-116">3</span><span class="sxs-lookup"><span data-stu-id="887ee-116">3</span></span>|<span data-ttu-id="887ee-117">Visualizza gli avvisi di livello 2 oltre ad alcuni avvisi meno gravi, ad esempio gli avvisi relativi alle espressioni che restituiscono sempre `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="887ee-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="887ee-118">4 (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="887ee-118">4 (the default)</span></span>|<span data-ttu-id="887ee-119">Visualizza tutti gli avvisi di livello 3 oltre ad avvisi informativi.</span><span class="sxs-lookup"><span data-stu-id="887ee-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="887ee-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="887ee-120">Remarks</span></span>  
 <span data-ttu-id="887ee-121">Per ottenere informazioni su un errore o un avviso, è possibile cercare il codice di errore nell'indice della Guida.</span><span class="sxs-lookup"><span data-stu-id="887ee-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="887ee-122">Per altri modi per ottenere informazioni su un errore o un avviso, vedere [Errori del compilatore C#](../compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="887ee-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="887ee-123">Usare [-warnaserror](./warnaserror-compiler-option.md) per considerare tutti gli avvisi come errori.</span><span class="sxs-lookup"><span data-stu-id="887ee-123">Use [-warnaserror](./warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="887ee-124">Usare [-nowarn](./nowarn-compiler-option.md) per disabilitare avvisi specifici.</span><span class="sxs-lookup"><span data-stu-id="887ee-124">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="887ee-125">**-w** è la versione abbreviata di **-warn**.</span><span class="sxs-lookup"><span data-stu-id="887ee-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="887ee-126">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="887ee-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="887ee-127">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="887ee-127">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="887ee-128">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="887ee-128">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="887ee-129">Modificare la proprietà **Livello avvisi**.</span><span class="sxs-lookup"><span data-stu-id="887ee-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="887ee-130">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="887ee-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="887ee-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="887ee-131">Example</span></span>  
 <span data-ttu-id="887ee-132">Compilare `in.cs` e fare in modo che il compilatore visualizzi solo gli avvisi di livello 1:</span><span class="sxs-lookup"><span data-stu-id="887ee-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="887ee-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="887ee-133">See also</span></span>

- [<span data-ttu-id="887ee-134">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="887ee-134">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="887ee-135">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="887ee-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
