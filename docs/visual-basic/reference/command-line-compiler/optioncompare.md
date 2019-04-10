---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: b88cba4d16c5a770a72b47868d11b16cbba6cae8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340438"
---
# <a name="-optioncompare"></a><span data-ttu-id="c970a-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="c970a-102">-optioncompare</span></span>
<span data-ttu-id="c970a-103">Specifica la modalità con cui vengono confrontate le stringhe.</span><span class="sxs-lookup"><span data-stu-id="c970a-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c970a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c970a-104">Syntax</span></span>  
  
```  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="c970a-105">Note</span><span class="sxs-lookup"><span data-stu-id="c970a-105">Remarks</span></span>  
 <span data-ttu-id="c970a-106">È possibile specificare `-optioncompare` in uno dei due formati: `-optioncompare:binary` usare confronti di stringhe binarie e `-optioncompare:text` usare confronti di stringhe di testo.</span><span class="sxs-lookup"><span data-stu-id="c970a-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="c970a-107">Per impostazione predefinita, il compilatore Usa `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="c970a-107">By default, the compiler uses `-optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="c970a-108">In Microsoft Windows, la tabella codici corrente determina l'ordinamento binario.</span><span class="sxs-lookup"><span data-stu-id="c970a-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="c970a-109">Come indicato di seguito è riportato un tipico ordinamento binario:</span><span class="sxs-lookup"><span data-stu-id="c970a-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="c970a-110">I confronti di stringhe basata su testo si basano su un ordinamento testo tra maiuscole e minuscole determinato dalle impostazioni locali del sistema.</span><span class="sxs-lookup"><span data-stu-id="c970a-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="c970a-111">Come indicato di seguito è riportato un ordinamento testo tipico:</span><span class="sxs-lookup"><span data-stu-id="c970a-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="c970a-112">Per impostare - optioncompare nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c970a-112">To set -optioncompare in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="c970a-113">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="c970a-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c970a-114">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="c970a-114">On the **Project** menu, click **Properties**.</span></span>   
  
2. <span data-ttu-id="c970a-115">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="c970a-115">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="c970a-116">Modificare il valore di **Option Compare** casella.</span><span class="sxs-lookup"><span data-stu-id="c970a-116">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="c970a-117">Per impostare a livello di codice - optioncompare</span><span class="sxs-lookup"><span data-stu-id="c970a-117">To set -optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="c970a-118">Visualizzare [istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c970a-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c970a-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="c970a-119">Example</span></span>  
 <span data-ttu-id="c970a-120">Il codice seguente Compila `ProjFile.vb` e confronti tra stringhe binarie.</span><span class="sxs-lookup"><span data-stu-id="c970a-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c970a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c970a-121">See also</span></span>

- [<span data-ttu-id="c970a-122">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c970a-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c970a-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="c970a-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="c970a-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="c970a-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="c970a-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="c970a-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="c970a-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="c970a-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="c970a-127">Istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="c970a-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="c970a-128">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="c970a-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
