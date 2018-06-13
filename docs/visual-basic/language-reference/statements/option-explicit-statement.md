---
title: Istruzione Option Explicit (Visual Basic)
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
ms.openlocfilehash: 3a2d81b1441052c132e4739dfe6045f8c3a026d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604601"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="78f7a-102">Istruzione Option Explicit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78f7a-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="78f7a-103">Forza la dichiarazione esplicita di tutte le variabili in un file o consente dichiarazioni implicite delle variabili.</span><span class="sxs-lookup"><span data-stu-id="78f7a-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78f7a-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="78f7a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="78f7a-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="78f7a-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="78f7a-106">Optional.</span></span> <span data-ttu-id="78f7a-107">Abilita `Option Explicit` il controllo.</span><span class="sxs-lookup"><span data-stu-id="78f7a-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="78f7a-108">Se `On` o `Off` non viene specificato, il valore predefinito è `On`.</span><span class="sxs-lookup"><span data-stu-id="78f7a-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="78f7a-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="78f7a-109">Optional.</span></span> <span data-ttu-id="78f7a-110">Disabilita `Option Explicit` il controllo.</span><span class="sxs-lookup"><span data-stu-id="78f7a-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78f7a-111">Note</span><span class="sxs-lookup"><span data-stu-id="78f7a-111">Remarks</span></span>  
 <span data-ttu-id="78f7a-112">Quando `Option Explicit On` o `Option Explicit` viene visualizzato in un file, è necessario dichiarare in modo esplicito tutte le variabili utilizzando la `Dim` o `ReDim` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="78f7a-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="78f7a-113">Se si tenta di utilizzare un nome di variabile non dichiarato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="78f7a-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="78f7a-114">Il `Option Explicit Off` istruzione consente la dichiarazione implicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="78f7a-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="78f7a-115">Se usato, è necessario includere l'istruzione `Option Explicit` in un file prima di tutte le altre istruzioni del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="78f7a-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78f7a-116">Impostazione `Option Explicit` per `Off` non è in genere consigliabile.</span><span class="sxs-lookup"><span data-stu-id="78f7a-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="78f7a-117">È possibile digitare un nome di variabile in modo errato in una o più posizioni e ciò può causare risultati imprevisti quando viene eseguito il programma.</span><span class="sxs-lookup"><span data-stu-id="78f7a-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="78f7a-118">Quando non è presente un'istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="78f7a-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="78f7a-119">Se il codice sorgente non contiene un `Option Explicit` istruzione, il **Option Explicit** impostazione di [pagina Compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="78f7a-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="78f7a-120">Se viene utilizzato il compilatore della riga di comando, il [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) viene utilizzata l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="78f7a-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="78f7a-121">Per impostare Option Explicit nell'IDE</span><span class="sxs-lookup"><span data-stu-id="78f7a-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="78f7a-122">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="78f7a-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="78f7a-123">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="78f7a-123">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="78f7a-124">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="78f7a-124">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="78f7a-125">Impostare il valore di **Option Explicit** casella.</span><span class="sxs-lookup"><span data-stu-id="78f7a-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="78f7a-126">Quando si crea un nuovo progetto, il **Option Explicit** impostazione il **compilare** scheda è impostata sul **Option Explicit** impostazione nel **VB predefinite**la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="78f7a-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="78f7a-127">Per accedere al **VB per impostazione predefinita** della finestra di dialogo di **strumenti** menu, fare clic su **opzioni**.</span><span class="sxs-lookup"><span data-stu-id="78f7a-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="78f7a-128">Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="78f7a-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="78f7a-129">L'impostazione predefinita iniziale in **impostazioni predefinite di Visual Basic** è `On`.</span><span class="sxs-lookup"><span data-stu-id="78f7a-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="78f7a-130">Per impostare Option Explicit nella riga di comando</span><span class="sxs-lookup"><span data-stu-id="78f7a-130">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="78f7a-131">Includere il [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) opzione del compilatore nella **vbc** comando.</span><span class="sxs-lookup"><span data-stu-id="78f7a-131">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78f7a-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="78f7a-132">Example</span></span>  
 <span data-ttu-id="78f7a-133">L'esempio seguente usa il `Option Explicit` istruzione per imporre la dichiarazione esplicita di tutte le variabili.</span><span class="sxs-lookup"><span data-stu-id="78f7a-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="78f7a-134">Il tentativo di utilizzare una variabile dichiarata causa un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="78f7a-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="78f7a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78f7a-135">See Also</span></span>  
 [<span data-ttu-id="78f7a-136">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="78f7a-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="78f7a-137">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="78f7a-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="78f7a-138">Istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="78f7a-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="78f7a-139">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="78f7a-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="78f7a-140">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="78f7a-140">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="78f7a-141">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="78f7a-141">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="78f7a-142">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="78f7a-142">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="78f7a-143">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="78f7a-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
