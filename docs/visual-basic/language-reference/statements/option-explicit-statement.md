---
title: Option Explicit Statement (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
dev_langs:
- VB
helpviewer_keywords:
- declaring variables, explicit
- forced variable declaration in Option Explicit statement
- Explicit keyword
- explicit variable declaration
- Option Explicit statement
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
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
ms.openlocfilehash: 4283599d9ed2ad9075ab0b2f404f1a12a31437ec
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="cc864-102">Istruzione Option Explicit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc864-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="cc864-103">Forza la dichiarazione esplicita di tutte le variabili in un file o consente dichiarazioni implicite delle variabili.</span><span class="sxs-lookup"><span data-stu-id="cc864-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc864-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc864-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="cc864-105">Parti</span><span class="sxs-lookup"><span data-stu-id="cc864-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="cc864-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cc864-106">Optional.</span></span> <span data-ttu-id="cc864-107">Consente di `Option Explicit` il controllo.</span><span class="sxs-lookup"><span data-stu-id="cc864-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="cc864-108">Se `On` o `Off` non è specificato, il valore predefinito è `On`.</span><span class="sxs-lookup"><span data-stu-id="cc864-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="cc864-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cc864-109">Optional.</span></span> <span data-ttu-id="cc864-110">Disabilita `Option Explicit` il controllo.</span><span class="sxs-lookup"><span data-stu-id="cc864-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc864-111">Note</span><span class="sxs-lookup"><span data-stu-id="cc864-111">Remarks</span></span>  
 <span data-ttu-id="cc864-112">Quando `Option Explicit On` o `Option Explicit` viene visualizzato in un file, è necessario dichiarare tutte le variabili in modo esplicito tramite il `Dim` o `ReDim` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="cc864-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="cc864-113">Se si tenta di utilizzare un nome di variabile non dichiarato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cc864-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="cc864-114">Il `Option Explicit Off` istruzione consente la dichiarazione implicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="cc864-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="cc864-115">Se usato, è necessario includere l'istruzione `Option Explicit` in un file prima di tutte le altre istruzioni del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="cc864-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc864-116">L'impostazione `Option Explicit` a `Off` non è in genere consigliabile.</span><span class="sxs-lookup"><span data-stu-id="cc864-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="cc864-117">Impossibile digitato un nome di variabile in uno o più percorsi, che potrebbe provocare risultati imprevisti quando viene eseguito il programma.</span><span class="sxs-lookup"><span data-stu-id="cc864-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="cc864-118">Quando non è presente un'istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="cc864-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="cc864-119">Se il codice sorgente non contiene un `Option Explicit` istruzione, il **Option Explicit** impostazione per il [pagina Compila, Progettazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="cc864-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="cc864-120">Se viene utilizzato il compilatore della riga di comando, il [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) viene utilizzata l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="cc864-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="cc864-121">Per impostare Option Explicit nell'IDE</span><span class="sxs-lookup"><span data-stu-id="cc864-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="cc864-122">In **Esplora**, selezionare un progetto.</span><span class="sxs-lookup"><span data-stu-id="cc864-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="cc864-123">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cc864-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="cc864-124">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="cc864-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="cc864-125">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="cc864-125">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="cc864-126">Impostare il valore di **Option Explicit** casella.</span><span class="sxs-lookup"><span data-stu-id="cc864-126">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="cc864-127">Quando si crea un nuovo progetto, il **Option Explicit** impostazione per il **compilare** scheda è impostata sul **Option Explicit** impostazione nel **impostazioni predefinite di Visual Basic** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cc864-127">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="cc864-128">Per accedere al **VB per impostazione predefinita** della finestra di dialogo di **strumenti** menu, fare clic su **opzioni**.</span><span class="sxs-lookup"><span data-stu-id="cc864-128">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="cc864-129">Nel **opzioni** finestra di dialogo espandere **progetti e soluzioni**, quindi fare clic su **impostazioni predefinite di Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="cc864-129">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="cc864-130">L'impostazione predefinita iniziale in **impostazioni predefinite di Visual Basic** è `On`.</span><span class="sxs-lookup"><span data-stu-id="cc864-130">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="cc864-131">Per impostare Option Explicit nella riga di comando</span><span class="sxs-lookup"><span data-stu-id="cc864-131">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="cc864-132">Includere il [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) opzione del compilatore di **vbc** comando.</span><span class="sxs-lookup"><span data-stu-id="cc864-132">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc864-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc864-133">Example</span></span>  
 <span data-ttu-id="cc864-134">Nell'esempio seguente viene utilizzata la `Option Explicit` istruzione per imporre la dichiarazione esplicita di tutte le variabili.</span><span class="sxs-lookup"><span data-stu-id="cc864-134">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="cc864-135">Tentativo di utilizzare una variabile non dichiarata provoca un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cc864-135">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 <span data-ttu-id="cc864-136">[!code-vb[VbVbalrStatements&#47;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cc864-136">[!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="cc864-137">[!code-vb[VbVbalrStatements n.&48;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cc864-137">[!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc864-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc864-138">See Also</span></span>  
 <span data-ttu-id="cc864-139">[Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="cc864-139">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="cc864-140"> [ReDim (istruzione)](../../../visual-basic/language-reference/statements/redim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="cc864-140"> [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) </span></span>  
<span data-ttu-id="cc864-141"> [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="cc864-141"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="cc864-142"> [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="cc864-142"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="cc864-143"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="cc864-143"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="cc864-144"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="cc864-144"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="cc864-145"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="cc864-145"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="cc864-146"> [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="cc864-146"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
