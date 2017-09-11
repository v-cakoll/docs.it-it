---
title: /optionexplicit | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionexplicit
dev_langs:
- VB
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: 16
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
ms.openlocfilehash: 3d2622c08b863233c8e1088bad252b37b3b38b04
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="optionexplicit"></a><span data-ttu-id="a7ed1-102">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="a7ed1-102">/optionexplicit</span></span>
<span data-ttu-id="a7ed1-103">Indica al compilatore per segnalare gli errori se le variabili non vengono dichiarate prima che vengano utilizzati.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ed1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7ed1-104">Syntax</span></span>  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a7ed1-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a7ed1-105">Arguments</span></span>  
 <span data-ttu-id="a7ed1-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a7ed1-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="a7ed1-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-107">Optional.</span></span> <span data-ttu-id="a7ed1-108">Specificare `/optionexplicit+` per richiedere la dichiarazione esplicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-108">Specify `/optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="a7ed1-109">Il `/optionexplicit+` opzione è l'impostazione predefinita ed è identico `/optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-109">The `/optionexplicit+` option is the default and is the same as `/optionexplicit`.</span></span> <span data-ttu-id="a7ed1-110">Il `/optionexplicit-` opzione consente la dichiarazione implicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-110">The `/optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7ed1-111">Note</span><span class="sxs-lookup"><span data-stu-id="a7ed1-111">Remarks</span></span>  
 <span data-ttu-id="a7ed1-112">Se il file di codice di origine contiene un [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), l'istruzione esegue l'override di `/optionexplicit` impostazione del compilatore da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-112">If the source code file contains an [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `/optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="a7ed1-113">Per impostare /optionexplicit nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a7ed1-113">To set /optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="a7ed1-114">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a7ed1-115">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="a7ed1-116">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="a7ed1-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="a7ed1-117">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-117">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="a7ed1-118">Modificare il valore di **Option Explicit** casella.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-118">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7ed1-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7ed1-119">Example</span></span>  
 <span data-ttu-id="a7ed1-120">Il codice seguente viene compilato quando `/optionexplicit-` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-120">The following code compiles when `/optionexplicit-` is used.</span></span>  
  
 <span data-ttu-id="a7ed1-121">[!code-vb[VbVbalrCompiler n.&5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7ed1-121">[!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ed1-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7ed1-122">See Also</span></span>  
 <span data-ttu-id="a7ed1-123">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="a7ed1-123">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="a7ed1-124"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="a7ed1-124"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="a7ed1-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="a7ed1-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="a7ed1-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="a7ed1-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="a7ed1-127"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="a7ed1-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="a7ed1-128"> [Istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a7ed1-128"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="a7ed1-129"> [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="a7ed1-129"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
