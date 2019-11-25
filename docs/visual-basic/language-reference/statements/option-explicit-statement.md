---
title: Istruzione Option Explicit
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 3c70d958fdcbb1782af22c3a4715676abbeeac0c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353791"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="5bb34-102">Istruzione Option Explicit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5bb34-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="5bb34-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span><span class="sxs-lookup"><span data-stu-id="5bb34-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bb34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5bb34-104">Syntax</span></span>  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="5bb34-105">Parti</span><span class="sxs-lookup"><span data-stu-id="5bb34-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="5bb34-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5bb34-106">Optional.</span></span> <span data-ttu-id="5bb34-107">Enables `Option Explicit` checking.</span><span class="sxs-lookup"><span data-stu-id="5bb34-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="5bb34-108">If `On` or `Off` is not specified, the default is `On`.</span><span class="sxs-lookup"><span data-stu-id="5bb34-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="5bb34-109">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5bb34-109">Optional.</span></span> <span data-ttu-id="5bb34-110">Disables `Option Explicit` checking.</span><span class="sxs-lookup"><span data-stu-id="5bb34-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bb34-111">Note</span><span class="sxs-lookup"><span data-stu-id="5bb34-111">Remarks</span></span>  
 <span data-ttu-id="5bb34-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span><span class="sxs-lookup"><span data-stu-id="5bb34-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="5bb34-113">If you try to use an undeclared variable name, an error occurs at compile time.</span><span class="sxs-lookup"><span data-stu-id="5bb34-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="5bb34-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span><span class="sxs-lookup"><span data-stu-id="5bb34-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="5bb34-115">Se usato, è necessario includere l'istruzione `Option Explicit` in un file prima di tutte le altre istruzioni del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5bb34-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bb34-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span><span class="sxs-lookup"><span data-stu-id="5bb34-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="5bb34-117">È possibile digitare un nome di variabile in modo errato in una o più posizioni e ciò può causare risultati imprevisti quando viene eseguito il programma.</span><span class="sxs-lookup"><span data-stu-id="5bb34-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="5bb34-118">When an Option Explicit Statement Is Not Present</span><span class="sxs-lookup"><span data-stu-id="5bb34-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="5bb34-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span><span class="sxs-lookup"><span data-stu-id="5bb34-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="5bb34-120">If the command-line compiler is used, the [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span><span class="sxs-lookup"><span data-stu-id="5bb34-120">If the command-line compiler is used, the [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="5bb34-121">To set Option Explicit in the IDE</span><span class="sxs-lookup"><span data-stu-id="5bb34-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="5bb34-122">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="5bb34-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="5bb34-123">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="5bb34-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="5bb34-124">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="5bb34-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="5bb34-125">Set the value in the **Option Explicit** box.</span><span class="sxs-lookup"><span data-stu-id="5bb34-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="5bb34-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span><span class="sxs-lookup"><span data-stu-id="5bb34-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="5bb34-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span><span class="sxs-lookup"><span data-stu-id="5bb34-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="5bb34-128">Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="5bb34-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="5bb34-129">The initial default setting in **VB Defaults** is `On`.</span><span class="sxs-lookup"><span data-stu-id="5bb34-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="5bb34-130">To set Option Explicit on the command line</span><span class="sxs-lookup"><span data-stu-id="5bb34-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="5bb34-131">Include the [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span><span class="sxs-lookup"><span data-stu-id="5bb34-131">Include the [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bb34-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="5bb34-132">Example</span></span>  
 <span data-ttu-id="5bb34-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span><span class="sxs-lookup"><span data-stu-id="5bb34-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="5bb34-134">Attempting to use an undeclared variable causes an error at compile time.</span><span class="sxs-lookup"><span data-stu-id="5bb34-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="5bb34-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bb34-135">See also</span></span>

- [<span data-ttu-id="5bb34-136">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="5bb34-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="5bb34-137">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="5bb34-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="5bb34-138">Istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="5bb34-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="5bb34-139">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="5bb34-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="5bb34-140">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="5bb34-140">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="5bb34-141">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="5bb34-141">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="5bb34-142">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="5bb34-142">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="5bb34-143">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="5bb34-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
