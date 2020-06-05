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
ms.openlocfilehash: a352df0323cfeca1ea0e206ae45c3f85a2cd7da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404369"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="ca54a-102">Istruzione Option Explicit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca54a-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="ca54a-103">Impone la dichiarazione esplicita di tutte le variabili in un file o consente dichiarazioni implicite delle variabili.</span><span class="sxs-lookup"><span data-stu-id="ca54a-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca54a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca54a-104">Syntax</span></span>  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="ca54a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ca54a-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="ca54a-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ca54a-106">Optional.</span></span> <span data-ttu-id="ca54a-107">Consente `Option Explicit` il controllo.</span><span class="sxs-lookup"><span data-stu-id="ca54a-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="ca54a-108">Se `On` o `Off` non è specificato, il valore predefinito è `On` .</span><span class="sxs-lookup"><span data-stu-id="ca54a-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="ca54a-109">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ca54a-109">Optional.</span></span> <span data-ttu-id="ca54a-110">Disabilita `Option Explicit` il controllo.</span><span class="sxs-lookup"><span data-stu-id="ca54a-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca54a-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="ca54a-111">Remarks</span></span>  
 <span data-ttu-id="ca54a-112">Quando `Option Explicit On` o `Option Explicit` viene visualizzato in un file, è necessario dichiarare in modo esplicito tutte le variabili usando le `Dim` `ReDim` istruzioni o.</span><span class="sxs-lookup"><span data-stu-id="ca54a-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="ca54a-113">Se si tenta di utilizzare un nome di variabile non dichiarato, si verificherà un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ca54a-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="ca54a-114">L' `Option Explicit Off` istruzione consente la dichiarazione implicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="ca54a-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="ca54a-115">Se usato, è necessario includere l'istruzione `Option Explicit` in un file prima di tutte le altre istruzioni del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="ca54a-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca54a-116">`Option Explicit` `Off` Non è in genere consigliabile impostare su.</span><span class="sxs-lookup"><span data-stu-id="ca54a-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="ca54a-117">È possibile digitare un nome di variabile in modo errato in una o più posizioni e ciò può causare risultati imprevisti quando viene eseguito il programma.</span><span class="sxs-lookup"><span data-stu-id="ca54a-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="ca54a-118">Quando non è presente un'istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="ca54a-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="ca54a-119">Se il codice sorgente non contiene un' `Option Explicit` istruzione, viene utilizzata l'impostazione **Option Explicit** nella [pagina compilazione, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) .</span><span class="sxs-lookup"><span data-stu-id="ca54a-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="ca54a-120">Se viene usato il compilatore da riga di comando, viene usata l'opzione del compilatore [-OptionExplicit (](../../reference/command-line-compiler/optionexplicit.md) .</span><span class="sxs-lookup"><span data-stu-id="ca54a-120">If the command-line compiler is used, the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="ca54a-121">Per impostare l'opzione Explicit nell'IDE</span><span class="sxs-lookup"><span data-stu-id="ca54a-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="ca54a-122">In **Esplora soluzioni**selezionare un progetto.</span><span class="sxs-lookup"><span data-stu-id="ca54a-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="ca54a-123">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="ca54a-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="ca54a-124">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="ca54a-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="ca54a-125">Impostare il valore nella casella **Option Explicit** .</span><span class="sxs-lookup"><span data-stu-id="ca54a-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="ca54a-126">Quando si crea un nuovo progetto, l'impostazione **Option Explicit** nella scheda **Compila** viene impostata sull'impostazione **Option Explicit** nella finestra di dialogo **impostazioni predefinite di Visual Basic** .</span><span class="sxs-lookup"><span data-stu-id="ca54a-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="ca54a-127">Per accedere alla finestra di dialogo **impostazioni predefinite di Visual Basic** , scegliere **Opzioni**dal menu **strumenti** .</span><span class="sxs-lookup"><span data-stu-id="ca54a-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="ca54a-128">Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="ca54a-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="ca54a-129">L'impostazione predefinita iniziale in impostazioni **predefinite di Visual Basic** è `On` .</span><span class="sxs-lookup"><span data-stu-id="ca54a-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="ca54a-130">Per impostare Option Explicit nella riga di comando</span><span class="sxs-lookup"><span data-stu-id="ca54a-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="ca54a-131">Includere l'opzione del compilatore [-OptionExplicit (](../../reference/command-line-compiler/optionexplicit.md) nel comando **vbc** .</span><span class="sxs-lookup"><span data-stu-id="ca54a-131">Include the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca54a-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca54a-132">Example</span></span>  
 <span data-ttu-id="ca54a-133">Nell'esempio seguente viene utilizzata l' `Option Explicit` istruzione per forzare la dichiarazione esplicita di tutte le variabili.</span><span class="sxs-lookup"><span data-stu-id="ca54a-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="ca54a-134">Il tentativo di utilizzare una variabile non dichiarata genera un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ca54a-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="ca54a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca54a-135">See also</span></span>

- [<span data-ttu-id="ca54a-136">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="ca54a-136">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="ca54a-137">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="ca54a-137">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="ca54a-138">Istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="ca54a-138">Option Compare Statement</span></span>](option-compare-statement.md)
- [<span data-ttu-id="ca54a-139">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="ca54a-139">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="ca54a-140">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="ca54a-140">-optioncompare</span></span>](../../reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="ca54a-141">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="ca54a-141">-optionexplicit</span></span>](../../reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="ca54a-142">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="ca54a-142">-optionstrict</span></span>](../../reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="ca54a-143">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="ca54a-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
