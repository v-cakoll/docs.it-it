---
title: /optionstrict
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f783cc5b20c4fe6d7812a05a66cbc4cdfc0b9395
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="optionstrict"></a><span data-ttu-id="15e89-102">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="15e89-102">/optionstrict</span></span>
<span data-ttu-id="15e89-103">Applica la semantica dei tipi rigorosa per limitare le conversioni implicite.</span><span class="sxs-lookup"><span data-stu-id="15e89-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15e89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15e89-104">Syntax</span></span>  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="15e89-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="15e89-105">Arguments</span></span>  
 <span data-ttu-id="15e89-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="15e89-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="15e89-107">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="15e89-107">Optional.</span></span> <span data-ttu-id="15e89-108">Il `/optionstrict+` limita l'opzione di conversione implicita del tipo.</span><span class="sxs-lookup"><span data-stu-id="15e89-108">The `/optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="15e89-109">Il valore predefinito per questa opzione è `/optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="15e89-109">The default for this option is `/optionstrict-`.</span></span> <span data-ttu-id="15e89-110">Il `/optionstrict+` opzione equivale `/optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="15e89-110">The `/optionstrict+` option is the same as `/optionstrict`.</span></span> <span data-ttu-id="15e89-111">È possibile utilizzare entrambe le opzioni per la semantica dei tipi permissiva.</span><span class="sxs-lookup"><span data-stu-id="15e89-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="15e89-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="15e89-112">Required.</span></span> <span data-ttu-id="15e89-113">Avvisa quando non viene rispettata la semantica del linguaggio rigorosa.</span><span class="sxs-lookup"><span data-stu-id="15e89-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15e89-114">Note</span><span class="sxs-lookup"><span data-stu-id="15e89-114">Remarks</span></span>  
 <span data-ttu-id="15e89-115">Quando `/optionstrict+` è in effetti, solo le conversioni di tipo widening possono essere eseguite in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="15e89-115">When `/optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="15e89-116">Conversioni di tipi, ad esempio l'assegnazione di narrowing implicite un `Decimal` tipo di oggetto a un oggetto di tipo integer, vengono segnalati come errori.</span><span class="sxs-lookup"><span data-stu-id="15e89-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="15e89-117">Per generare avvisi per conversioni implicite verso un tipo, utilizzare `/optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="15e89-117">To generate warnings for implicit narrowing type conversions, use `/optionstrict:custom`.</span></span> <span data-ttu-id="15e89-118">Utilizzare `/nowarn:numberlist` per ignorare determinati avvisi e `/warnaserror:numberlist` per considerare determinati avvisi come errori.</span><span class="sxs-lookup"><span data-stu-id="15e89-118">Use `/nowarn:numberlist` to ignore particular warnings and `/warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="15e89-119">Per impostare /optionstrict nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="15e89-119">To set /optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="15e89-120">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="15e89-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="15e89-121">Nel **progetto** menu, fare clic su **proprietà.**</span><span class="sxs-lookup"><span data-stu-id="15e89-121">On the **Project** menu, click **Properties.**</span></span> <span data-ttu-id="15e89-122">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="15e89-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="15e89-123">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="15e89-123">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="15e89-124">Modificare il valore di **Option Strict** casella.</span><span class="sxs-lookup"><span data-stu-id="15e89-124">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set-optionstrict-programmatically"></a><span data-ttu-id="15e89-125">Per impostare /optionstrict a livello di codice</span><span class="sxs-lookup"><span data-stu-id="15e89-125">To set /optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="15e89-126">Vedere [Option Strict (istruzione)](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="15e89-126">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="15e89-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="15e89-127">Example</span></span>  
 <span data-ttu-id="15e89-128">Il codice seguente Compila `Test.vb` utilizzando la semantica dei tipi rigorosa.</span><span class="sxs-lookup"><span data-stu-id="15e89-128">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="15e89-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15e89-129">See Also</span></span>  
 [<span data-ttu-id="15e89-130">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15e89-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="15e89-131">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="15e89-131">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="15e89-132">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="15e89-132">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="15e89-133">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="15e89-133">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="15e89-134">/nowarn</span><span class="sxs-lookup"><span data-stu-id="15e89-134">/nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)  
 [<span data-ttu-id="15e89-135">/warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15e89-135">/warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)  
 [<span data-ttu-id="15e89-136">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="15e89-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="15e89-137">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="15e89-137">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="15e89-138">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="15e89-138">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
