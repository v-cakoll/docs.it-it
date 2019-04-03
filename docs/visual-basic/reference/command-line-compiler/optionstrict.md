---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: 5479c312ae7eb7a166803a6e1238806aae9bd656
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835661"
---
# <a name="-optionstrict"></a><span data-ttu-id="6f47d-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="6f47d-102">-optionstrict</span></span>
<span data-ttu-id="6f47d-103">Applica una semantica dei tipi rigorosa per limitare le conversioni implicite.</span><span class="sxs-lookup"><span data-stu-id="6f47d-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f47d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f47d-104">Syntax</span></span>  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6f47d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6f47d-105">Arguments</span></span>  
 <span data-ttu-id="6f47d-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="6f47d-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="6f47d-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6f47d-107">Optional.</span></span> <span data-ttu-id="6f47d-108">Il `-optionstrict+` limita l'opzione di conversione implicita del tipo.</span><span class="sxs-lookup"><span data-stu-id="6f47d-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="6f47d-109">Il valore predefinito per questa opzione è `-optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="6f47d-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="6f47d-110">Il `-optionstrict+` opzione è identico `-optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="6f47d-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="6f47d-111">È possibile utilizzare entrambi per la semantica di tipo permissivo.</span><span class="sxs-lookup"><span data-stu-id="6f47d-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="6f47d-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6f47d-112">Required.</span></span> <span data-ttu-id="6f47d-113">Avvisa quando non viene rispettata la semantica del linguaggio rigorosa.</span><span class="sxs-lookup"><span data-stu-id="6f47d-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f47d-114">Note</span><span class="sxs-lookup"><span data-stu-id="6f47d-114">Remarks</span></span>  
 <span data-ttu-id="6f47d-115">Quando si `-optionstrict+` è attiva, solo le conversioni di tipo widening possono essere eseguite in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="6f47d-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="6f47d-116">Conversioni di tipi, ad esempio l'assegnazione di narrowing implicite un `Decimal` tipo object per un oggetto di tipo integer, vengono segnalati come errori.</span><span class="sxs-lookup"><span data-stu-id="6f47d-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="6f47d-117">Per generare avvisi per conversioni di tipo narrowing, utilizzare `-optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="6f47d-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="6f47d-118">Uso `-nowarn:numberlist` per ignorare determinati avvisi e `-warnaserror:numberlist` particolare considerarli come errori.</span><span class="sxs-lookup"><span data-stu-id="6f47d-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="6f47d-119">Per impostare - optionstrict nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6f47d-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="6f47d-120">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="6f47d-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6f47d-121">Nel **Project** menu, fare clic su **proprietà.**</span><span class="sxs-lookup"><span data-stu-id="6f47d-121">On the **Project** menu, click **Properties.**</span></span>   
  
2.  <span data-ttu-id="6f47d-122">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="6f47d-122">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="6f47d-123">Modificare il valore di **Option Strict** casella.</span><span class="sxs-lookup"><span data-stu-id="6f47d-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="6f47d-124">Per impostare a livello di codice - optionstrict</span><span class="sxs-lookup"><span data-stu-id="6f47d-124">To set -optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="6f47d-125">Visualizzare [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6f47d-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f47d-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="6f47d-126">Example</span></span>  
 <span data-ttu-id="6f47d-127">Il codice seguente Compila `Test.vb` mediante la semantica di tipo strict.</span><span class="sxs-lookup"><span data-stu-id="6f47d-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f47d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f47d-128">See also</span></span>

- [<span data-ttu-id="6f47d-129">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6f47d-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6f47d-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="6f47d-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="6f47d-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="6f47d-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="6f47d-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="6f47d-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="6f47d-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="6f47d-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="6f47d-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f47d-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="6f47d-135">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="6f47d-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="6f47d-136">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="6f47d-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="6f47d-137">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="6f47d-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
