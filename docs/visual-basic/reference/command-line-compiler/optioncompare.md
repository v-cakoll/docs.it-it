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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1906710ef10634187782f9355146dfa7ccb7748
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653403"
---
# <a name="-optioncompare"></a><span data-ttu-id="38f82-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="38f82-102">-optioncompare</span></span>
<span data-ttu-id="38f82-103">Specifica la modalità con cui vengono confrontate le stringhe.</span><span class="sxs-lookup"><span data-stu-id="38f82-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38f82-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38f82-104">Syntax</span></span>  
  
```  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="38f82-105">Note</span><span class="sxs-lookup"><span data-stu-id="38f82-105">Remarks</span></span>  
 <span data-ttu-id="38f82-106">È possibile specificare `-optioncompare` in uno dei due formati: `-optioncompare:binary` per utilizzare confronti tra stringhe binarie e `-optioncompare:text` per utilizzare confronti tra stringhe di testo.</span><span class="sxs-lookup"><span data-stu-id="38f82-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="38f82-107">Per impostazione predefinita, il compilatore utilizza `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="38f82-107">By default, the compiler uses `-optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="38f82-108">In Microsoft Windows, la tabella codici corrente determina l'ordinamento binario.</span><span class="sxs-lookup"><span data-stu-id="38f82-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="38f82-109">Un tipico ordinamento binario è il seguente:</span><span class="sxs-lookup"><span data-stu-id="38f82-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="38f82-110">Confronti tra stringhe basati su testo sono in base all'ordinamento senza distinzione tra maiuscole determinato dalle impostazioni locali del sistema.</span><span class="sxs-lookup"><span data-stu-id="38f82-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="38f82-111">Un ordinamento testo tipico è la seguente:</span><span class="sxs-lookup"><span data-stu-id="38f82-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="38f82-112">Per impostare - optioncompare nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="38f82-112">To set -optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="38f82-113">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="38f82-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="38f82-114">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="38f82-114">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="38f82-115">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="38f82-115">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="38f82-116">Modificare il valore di **Option Compare** casella.</span><span class="sxs-lookup"><span data-stu-id="38f82-116">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="38f82-117">Per impostare a livello di programmazione - optioncompare</span><span class="sxs-lookup"><span data-stu-id="38f82-117">To set -optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="38f82-118">Vedere [Option Compare (istruzione)](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="38f82-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38f82-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="38f82-119">Example</span></span>  
 <span data-ttu-id="38f82-120">Il codice seguente Compila `ProjFile.vb` e confronti tra stringhe binarie.</span><span class="sxs-lookup"><span data-stu-id="38f82-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="38f82-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38f82-121">See Also</span></span>  
 [<span data-ttu-id="38f82-122">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="38f82-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="38f82-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="38f82-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="38f82-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="38f82-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="38f82-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="38f82-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="38f82-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="38f82-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="38f82-127">Istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="38f82-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="38f82-128">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="38f82-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
