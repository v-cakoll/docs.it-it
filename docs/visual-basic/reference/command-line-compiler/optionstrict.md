---
title: /optionstrict | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionstrict
dev_langs:
- VB
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c22445cb53ca4f5621cf7aa69ab840b26f8e08c9
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="optionstrict"></a><span data-ttu-id="fa88b-102">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="fa88b-102">/optionstrict</span></span>
<span data-ttu-id="fa88b-103">Impone la semantica dei tipi rigida per limitare le conversioni implicite.</span><span class="sxs-lookup"><span data-stu-id="fa88b-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa88b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa88b-104">Syntax</span></span>  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fa88b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fa88b-105">Arguments</span></span>  
 <span data-ttu-id="fa88b-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="fa88b-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="fa88b-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fa88b-107">Optional.</span></span> <span data-ttu-id="fa88b-108">Il `/optionstrict+` opzione limita la conversione implicita dei tipi.</span><span class="sxs-lookup"><span data-stu-id="fa88b-108">The `/optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="fa88b-109">Il valore predefinito per questa opzione è `/optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="fa88b-109">The default for this option is `/optionstrict-`.</span></span> <span data-ttu-id="fa88b-110">Il `/optionstrict+` opzione corrisponde al `/optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="fa88b-110">The `/optionstrict+` option is the same as `/optionstrict`.</span></span> <span data-ttu-id="fa88b-111">È possibile utilizzare sia per la semantica permissiva.</span><span class="sxs-lookup"><span data-stu-id="fa88b-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="fa88b-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fa88b-112">Required.</span></span> <span data-ttu-id="fa88b-113">Avvisa quando la semantica della lingua ridotta non viene rispettata.</span><span class="sxs-lookup"><span data-stu-id="fa88b-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa88b-114">Note</span><span class="sxs-lookup"><span data-stu-id="fa88b-114">Remarks</span></span>  
 <span data-ttu-id="fa88b-115">Quando `/optionstrict+` è in effetti, solo le conversioni di tipo possono essere apportate in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="fa88b-115">When `/optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="fa88b-116">Conversioni di tipi, ad esempio l'assegnazione di narrowing implicite un `Decimal` tipo di oggetto a un oggetto di tipo integer, vengono segnalati come errori.</span><span class="sxs-lookup"><span data-stu-id="fa88b-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="fa88b-117">Per generare avvisi per conversioni di tipo narrowing, utilizzare `/optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="fa88b-117">To generate warnings for implicit narrowing type conversions, use `/optionstrict:custom`.</span></span> <span data-ttu-id="fa88b-118">Utilizzare `/nowarn:numberlist` per ignorare determinati avvisi e `/warnaserror:numberlist` per considerare determinati avvisi come errori.</span><span class="sxs-lookup"><span data-stu-id="fa88b-118">Use `/nowarn:numberlist` to ignore particular warnings and `/warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="fa88b-119">Per impostare /optionstrict nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa88b-119">To set /optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="fa88b-120">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="fa88b-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fa88b-121">Nel **progetto** menu, fare clic su **proprietà.**</span><span class="sxs-lookup"><span data-stu-id="fa88b-121">On the **Project** menu, click **Properties.**</span></span> <span data-ttu-id="fa88b-122">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="fa88b-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="fa88b-123">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="fa88b-123">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="fa88b-124">Modificare il valore di **Option Strict** casella.</span><span class="sxs-lookup"><span data-stu-id="fa88b-124">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set-optionstrict-programmatically"></a><span data-ttu-id="fa88b-125">Per impostare /optionstrict a livello di codice</span><span class="sxs-lookup"><span data-stu-id="fa88b-125">To set /optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="fa88b-126">Vedere [Option Strict (istruzione)](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fa88b-126">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa88b-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa88b-127">Example</span></span>  
 <span data-ttu-id="fa88b-128">Il codice seguente Compila `Test.vb` mediante la semantica di tipo strict.</span><span class="sxs-lookup"><span data-stu-id="fa88b-128">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa88b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa88b-129">See Also</span></span>  
 <span data-ttu-id="fa88b-130">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa88b-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="fa88b-131"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="fa88b-131"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="fa88b-132"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="fa88b-132"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="fa88b-133"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="fa88b-133"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="fa88b-134"> [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) </span><span class="sxs-lookup"><span data-stu-id="fa88b-134"> [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) </span></span>  
<span data-ttu-id="fa88b-135"> [/warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md) </span><span class="sxs-lookup"><span data-stu-id="fa88b-135"> [/warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md) </span></span>  
<span data-ttu-id="fa88b-136"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="fa88b-136"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="fa88b-137"> [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="fa88b-137"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="fa88b-138"> [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="fa88b-138"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
