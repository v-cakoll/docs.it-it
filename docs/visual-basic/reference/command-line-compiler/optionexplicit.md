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
ms.openlocfilehash: b004acb0c1c7d145c59a1e3a88ef7f1d405a91c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400559"
---
# <a name="-optionexplicit"></a><span data-ttu-id="4c9ac-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="4c9ac-102">-optionexplicit</span></span>
<span data-ttu-id="4c9ac-103">Fa in modo che il compilatore segnali errori se le variabili non vengono dichiarate prima di essere utilizzate.</span><span class="sxs-lookup"><span data-stu-id="4c9ac-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c9ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c9ac-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4c9ac-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4c9ac-105">Arguments</span></span>  
 <span data-ttu-id="4c9ac-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="4c9ac-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="4c9ac-107">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="4c9ac-107">Optional.</span></span> <span data-ttu-id="4c9ac-108">Specificare `-optionexplicit+` per richiedere la dichiarazione esplicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="4c9ac-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="4c9ac-109">L' `-optionexplicit+` opzione è l'impostazione predefinita ed è uguale a `-optionexplicit` .</span><span class="sxs-lookup"><span data-stu-id="4c9ac-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="4c9ac-110">L' `-optionexplicit-` opzione consente la dichiarazione implicita delle variabili.</span><span class="sxs-lookup"><span data-stu-id="4c9ac-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c9ac-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="4c9ac-111">Remarks</span></span>  
 <span data-ttu-id="4c9ac-112">Se il file di codice sorgente contiene un' [istruzione Option Explicit](../../language-reference/statements/option-explicit-statement.md), l'istruzione sostituisce l' `-optionexplicit` impostazione del compilatore da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="4c9ac-112">If the source code file contains an [Option Explicit statement](../../language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="4c9ac-113">Per impostare-optionexplicit (nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4c9ac-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="4c9ac-114">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="4c9ac-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4c9ac-115">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="4c9ac-115">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="4c9ac-116">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="4c9ac-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="4c9ac-117">Modificare il valore nella casella **Option Explicit** .</span><span class="sxs-lookup"><span data-stu-id="4c9ac-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c9ac-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c9ac-118">Example</span></span>  
 <span data-ttu-id="4c9ac-119">Il codice seguente viene compilato quando `-optionexplicit-` si usa.</span><span class="sxs-lookup"><span data-stu-id="4c9ac-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="4c9ac-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c9ac-120">See also</span></span>

- [<span data-ttu-id="4c9ac-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c9ac-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="4c9ac-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="4c9ac-122">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="4c9ac-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="4c9ac-123">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="4c9ac-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="4c9ac-124">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="4c9ac-125">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="4c9ac-125">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="4c9ac-126">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="4c9ac-126">Option Explicit Statement</span></span>](../../language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="4c9ac-127">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="4c9ac-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
