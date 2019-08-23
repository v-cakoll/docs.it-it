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
ms.openlocfilehash: c027964d185d7f69c0a56a4386bedc2d8f9d2eac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912342"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="7be4e-102">Istruzione Option Explicit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7be4e-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="7be4e-103">Impone la dichiarazione esplicita di tutte le variabili in un file o consente dichiarazioni implicite delle variabili.</span><span class="sxs-lookup"><span data-stu-id="7be4e-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7be4e-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="7be4e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7be4e-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="7be4e-106">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7be4e-106">Optional.</span></span> <span data-ttu-id="7be4e-107">Consente `Option Explicit` il controllo.</span><span class="sxs-lookup"><span data-stu-id="7be4e-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="7be4e-108">Se `On` `On`o `Off` non è specificato, il valore predefinito è.</span><span class="sxs-lookup"><span data-stu-id="7be4e-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="7be4e-109">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7be4e-109">Optional.</span></span> <span data-ttu-id="7be4e-110">Disabilita `Option Explicit` il controllo.</span><span class="sxs-lookup"><span data-stu-id="7be4e-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7be4e-111">Note</span><span class="sxs-lookup"><span data-stu-id="7be4e-111">Remarks</span></span>  
 <span data-ttu-id="7be4e-112">Quando `Option Explicit On` `Dim` `ReDim` o `Option Explicit` viene visualizzato in un file, è necessario dichiarare in modo esplicito tutte le variabili usando le istruzioni o.</span><span class="sxs-lookup"><span data-stu-id="7be4e-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="7be4e-113">Se si tenta di utilizzare un nome di variabile non dichiarato, si verificherà un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7be4e-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="7be4e-114">L' `Option Explicit Off` istruzione consente la dichiarazione implicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="7be4e-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="7be4e-115">Se usato, è necessario includere l'istruzione `Option Explicit` in un file prima di tutte le altre istruzioni del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="7be4e-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7be4e-116">Non `Option Explicit` è `Off` in genere consigliabile impostare su.</span><span class="sxs-lookup"><span data-stu-id="7be4e-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="7be4e-117">È possibile digitare un nome di variabile in modo errato in una o più posizioni e ciò può causare risultati imprevisti quando viene eseguito il programma.</span><span class="sxs-lookup"><span data-stu-id="7be4e-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="7be4e-118">Quando non è presente un'istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="7be4e-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="7be4e-119">Se il codice sorgente non contiene un' `Option Explicit` istruzione, viene utilizzata l'impostazione **Option Explicit** nella [pagina compilazione, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) .</span><span class="sxs-lookup"><span data-stu-id="7be4e-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="7be4e-120">Se viene usato il compilatore da riga di comando, viene usata l'opzione del compilatore [/OptionExplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) .</span><span class="sxs-lookup"><span data-stu-id="7be4e-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="7be4e-121">Per impostare l'opzione Explicit nell'IDE</span><span class="sxs-lookup"><span data-stu-id="7be4e-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="7be4e-122">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="7be4e-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="7be4e-123">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="7be4e-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="7be4e-124">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="7be4e-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="7be4e-125">Impostare il valore nella casella **Option Explicit** .</span><span class="sxs-lookup"><span data-stu-id="7be4e-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="7be4e-126">Quando si crea un nuovo progetto, l'impostazione **Option Explicit** nella scheda **Compila** viene impostata sull'impostazione **Option Explicit** nella finestra di dialogo **impostazioni predefinite di Visual Basic** .</span><span class="sxs-lookup"><span data-stu-id="7be4e-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="7be4e-127">Per accedere alla finestra di dialogo **impostazioni predefinite di Visual Basic** , scegliere **Opzioni**dal menu **strumenti** .</span><span class="sxs-lookup"><span data-stu-id="7be4e-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="7be4e-128">Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="7be4e-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="7be4e-129">L'impostazione predefinita iniziale in impostazioni **predefinite di Visual Basic** è `On`.</span><span class="sxs-lookup"><span data-stu-id="7be4e-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="7be4e-130">Per impostare Option Explicit nella riga di comando</span><span class="sxs-lookup"><span data-stu-id="7be4e-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="7be4e-131">Includere l'opzione del compilatore [/OptionExplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) nel comando **vbc** .</span><span class="sxs-lookup"><span data-stu-id="7be4e-131">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7be4e-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="7be4e-132">Example</span></span>  
 <span data-ttu-id="7be4e-133">Nell'esempio seguente viene utilizzata `Option Explicit` l'istruzione per forzare la dichiarazione esplicita di tutte le variabili.</span><span class="sxs-lookup"><span data-stu-id="7be4e-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="7be4e-134">Il tentativo di utilizzare una variabile non dichiarata genera un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7be4e-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="7be4e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7be4e-135">See also</span></span>

- [<span data-ttu-id="7be4e-136">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="7be4e-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="7be4e-137">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="7be4e-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="7be4e-138">Istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="7be4e-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="7be4e-139">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="7be4e-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="7be4e-140">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="7be4e-140">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="7be4e-141">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="7be4e-141">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="7be4e-142">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="7be4e-142">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="7be4e-143">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="7be4e-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
