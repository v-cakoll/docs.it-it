---
title: -optionexplicit
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39ad78c82303d3655d5dda9e2286df0a55b8bf3e
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-optionexplicit"></a><span data-ttu-id="e4a14-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="e4a14-102">-optionexplicit</span></span>
<span data-ttu-id="e4a14-103">Determina la segnalazione degli errori se le variabili non vengono dichiarate prima che vengano utilizzate.</span><span class="sxs-lookup"><span data-stu-id="e4a14-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4a14-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4a14-104">Syntax</span></span>  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e4a14-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e4a14-105">Arguments</span></span>  
 <span data-ttu-id="e4a14-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e4a14-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="e4a14-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e4a14-107">Optional.</span></span> <span data-ttu-id="e4a14-108">Specificare `-optionexplicit+` per richiedere la dichiarazione esplicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="e4a14-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="e4a14-109">Il `-optionexplicit+` opzione è l'impostazione predefinita ed è lo stesso come `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="e4a14-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="e4a14-110">Il `-optionexplicit-` opzione consente la dichiarazione implicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="e4a14-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4a14-111">Note</span><span class="sxs-lookup"><span data-stu-id="e4a14-111">Remarks</span></span>  
 <span data-ttu-id="e4a14-112">Se il file di codice sorgente contiene un [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), l'istruzione esegue l'override di `-optionexplicit` impostazione del compilatore da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e4a14-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="e4a14-113">Per impostare - optionexplicit nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e4a14-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="e4a14-114">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="e4a14-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e4a14-115">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="e4a14-115">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="e4a14-116">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="e4a14-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="e4a14-117">Modificare il valore di **Option Explicit** casella.</span><span class="sxs-lookup"><span data-stu-id="e4a14-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4a14-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="e4a14-118">Example</span></span>  
 <span data-ttu-id="e4a14-119">Il codice seguente viene compilato quando `-optionexplicit-` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e4a14-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e4a14-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4a14-120">See Also</span></span>  
 [<span data-ttu-id="e4a14-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4a14-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e4a14-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="e4a14-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="e4a14-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="e4a14-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="e4a14-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="e4a14-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="e4a14-125">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="e4a14-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="e4a14-126">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="e4a14-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="e4a14-127">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="e4a14-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
