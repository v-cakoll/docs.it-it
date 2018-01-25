---
title: -nowarn (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nowarn
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2784e63b7c1e67b32fc448b4b112ad0252b1abd9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="-nowarn-c-compiler-options"></a><span data-ttu-id="41e2e-102">-nowarn (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="41e2e-102">-nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="41e2e-103">L'opzione **-nowarn** impedisce al compilatore di visualizzare uno o più avvisi.</span><span class="sxs-lookup"><span data-stu-id="41e2e-103">The **-nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="41e2e-104">Separare più numeri di avviso con una virgola.</span><span class="sxs-lookup"><span data-stu-id="41e2e-104">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e2e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41e2e-105">Syntax</span></span>  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="41e2e-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="41e2e-106">Arguments</span></span>  
 <span data-ttu-id="41e2e-107">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="41e2e-107">`number1`, `number2`</span></span>  
 <span data-ttu-id="41e2e-108">Il numero o i numeri degli avvisi che il compilatore non deve visualizzare.</span><span class="sxs-lookup"><span data-stu-id="41e2e-108">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41e2e-109">Note</span><span class="sxs-lookup"><span data-stu-id="41e2e-109">Remarks</span></span>  
 <span data-ttu-id="41e2e-110">Specificare solo la parte numerica dell'identificatore dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="41e2e-110">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="41e2e-111">Ad esempio, per eliminare l'avviso CS0028 è possibile specificare `-nowarn:28`.</span><span class="sxs-lookup"><span data-stu-id="41e2e-111">For example, if you want to suppress CS0028, you could specify `-nowarn:28`.</span></span>  
  
 <span data-ttu-id="41e2e-112">Il compilatore ignorerà automaticamente i numeri di avviso passati a `-nowarn` validi nelle versioni precedenti ma rimossi dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="41e2e-112">The compiler will silently ignore warning numbers passed to `-nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="41e2e-113">Ad esempio, CS0679 era valido nel compilatore in Visual Studio .NET 2002 ma è stato rimosso successivamente.</span><span class="sxs-lookup"><span data-stu-id="41e2e-113">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="41e2e-114">Gli avvisi seguenti non possono essere eliminati dall'opzione `-nowarn`:</span><span class="sxs-lookup"><span data-stu-id="41e2e-114">The following warnings cannot be suppressed by the `-nowarn` option:</span></span>  
  
-   <span data-ttu-id="41e2e-115">Avviso del compilatore (livello 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="41e2e-115">Compiler Warning (level 1) CS2002</span></span>  
  
-   <span data-ttu-id="41e2e-116">Avviso del compilatore (livello 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="41e2e-116">Compiler Warning (level 1) CS2023</span></span>  
  
-   <span data-ttu-id="41e2e-117">Avviso del compilatore (livello 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="41e2e-117">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="41e2e-118">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="41e2e-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="41e2e-119">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="41e2e-119">Open the **Properties** page for the project.</span></span> <span data-ttu-id="41e2e-120">Per informazioni dettagliate, vedere [Pagina Compilazione, Creazione progetti (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="41e2e-120">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="41e2e-121">Fare clic sulla pagina delle proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="41e2e-121">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="41e2e-122">Modificare la proprietà **Non visualizzare avvisi**.</span><span class="sxs-lookup"><span data-stu-id="41e2e-122">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="41e2e-123">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="41e2e-123">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e2e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41e2e-124">See Also</span></span>  
 [<span data-ttu-id="41e2e-125">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="41e2e-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="41e2e-126">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="41e2e-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="41e2e-127">Errori del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="41e2e-127">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
