---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: d7209e431b84e52e487bccbf73bd633a346efde0
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775611"
---
# <a name="-optioninfer"></a><span data-ttu-id="b994d-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="b994d-102">-optioninfer</span></span>
<span data-ttu-id="b994d-103">Consente di usare l'inferenza del tipo di variabile locale nelle dichiarazioni di variabile.</span><span class="sxs-lookup"><span data-stu-id="b994d-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b994d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b994d-104">Syntax</span></span>  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b994d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b994d-105">Arguments</span></span>  
  
|<span data-ttu-id="b994d-106">Termine</span><span class="sxs-lookup"><span data-stu-id="b994d-106">Term</span></span>|<span data-ttu-id="b994d-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="b994d-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="b994d-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b994d-108">`+` &#124; `-`</span></span>|<span data-ttu-id="b994d-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b994d-109">Optional.</span></span> <span data-ttu-id="b994d-110">Specificare `-optioninfer+` per abilitare l'inferenza del tipo di variabile locale o `-optioninfer-` per bloccarla.</span><span class="sxs-lookup"><span data-stu-id="b994d-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="b994d-111">L'opzione `-optioninfer`, senza alcun valore specificato, equivale a `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="b994d-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="b994d-112">Il valore predefinito, quando l'opzione `-optioninfer` non è presente, è anche `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="b994d-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="b994d-113">Il valore predefinito viene impostato nel file di risposta Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="b994d-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="b994d-114">È possibile usare l'opzione `-noconfig` per mantenere le impostazioni predefinite interne del compilatore anziché quelle specificate in vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="b994d-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="b994d-115">Il valore predefinito del compilatore per questa opzione è `-optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="b994d-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b994d-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b994d-116">Remarks</span></span>  
 <span data-ttu-id="b994d-117">Se il file di codice sorgente contiene un' [istruzione Option deduce](../../../visual-basic/language-reference/statements/option-infer-statement.md), l'istruzione sostituisce `-optioninfer` l'impostazione del compilatore da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b994d-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="b994d-118">Per impostare-optioninfer (nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b994d-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="b994d-119">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="b994d-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="b994d-120">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="b994d-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="b994d-121">Nella scheda **Compila** , modificare il valore nella casella **Option dedurre** .</span><span class="sxs-lookup"><span data-stu-id="b994d-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b994d-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="b994d-122">Example</span></span>  
 <span data-ttu-id="b994d-123">Il codice seguente compila `test.vb` con l'inferenza del tipo locale abilitata.</span><span class="sxs-lookup"><span data-stu-id="b994d-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b994d-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b994d-124">See also</span></span>

- [<span data-ttu-id="b994d-125">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b994d-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b994d-126">-OptionCompare (</span><span class="sxs-lookup"><span data-stu-id="b994d-126">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="b994d-127">-OptionExplicit (</span><span class="sxs-lookup"><span data-stu-id="b994d-127">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="b994d-128">-OptionStrict (</span><span class="sxs-lookup"><span data-stu-id="b994d-128">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="b994d-129">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="b994d-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="b994d-130">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="b994d-130">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="b994d-131">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="b994d-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="b994d-132">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="b994d-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="b994d-133">Compilazione (pagina), Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b994d-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="b994d-134">-noconfig</span><span class="sxs-lookup"><span data-stu-id="b994d-134">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="b994d-135">Compilazione dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="b994d-135">Building from the Command Line</span></span>](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
