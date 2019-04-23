---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 54d438541e8840e4394b24b20b4f394ff8cdb820
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332391"
---
# <a name="-optionexplicit"></a><span data-ttu-id="82d6a-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="82d6a-102">-optionexplicit</span></span>
<span data-ttu-id="82d6a-103">Indica al compilatore di segnalare errori se le variabili non vengono dichiarate prima che vengano utilizzate.</span><span class="sxs-lookup"><span data-stu-id="82d6a-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82d6a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82d6a-104">Syntax</span></span>  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="82d6a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="82d6a-105">Arguments</span></span>  
 <span data-ttu-id="82d6a-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="82d6a-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="82d6a-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="82d6a-107">Optional.</span></span> <span data-ttu-id="82d6a-108">Specificare `-optionexplicit+` per richiedere la dichiarazione esplicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="82d6a-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="82d6a-109">Il `-optionexplicit+` opzione è l'impostazione predefinita ed equivale a `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="82d6a-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="82d6a-110">Il `-optionexplicit-` opzione consente la dichiarazione implicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="82d6a-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82d6a-111">Note</span><span class="sxs-lookup"><span data-stu-id="82d6a-111">Remarks</span></span>  
 <span data-ttu-id="82d6a-112">Se il file di codice sorgente contiene un' [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), l'istruzione esegue l'override di `-optionexplicit` impostazione da riga di comando del compilatore.</span><span class="sxs-lookup"><span data-stu-id="82d6a-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="82d6a-113">Per impostare - optionexplicit nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="82d6a-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="82d6a-114">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="82d6a-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="82d6a-115">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="82d6a-115">On the **Project** menu, click **Properties**.</span></span>   
  
2. <span data-ttu-id="82d6a-116">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="82d6a-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="82d6a-117">Modificare il valore di **Option Explicit** casella.</span><span class="sxs-lookup"><span data-stu-id="82d6a-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82d6a-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="82d6a-118">Example</span></span>  
 <span data-ttu-id="82d6a-119">Il codice seguente viene compilato quando `-optionexplicit-` viene usato.</span><span class="sxs-lookup"><span data-stu-id="82d6a-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="82d6a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82d6a-120">See also</span></span>

- [<span data-ttu-id="82d6a-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82d6a-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="82d6a-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="82d6a-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="82d6a-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="82d6a-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="82d6a-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="82d6a-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="82d6a-125">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="82d6a-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="82d6a-126">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="82d6a-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="82d6a-127">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="82d6a-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
