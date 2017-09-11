---
title: /optioncompare | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioncompare
dev_langs:
- VB
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
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
ms.openlocfilehash: c9512427cda0b6a3bcb0c1fe338b47ff9f779d19
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="optioncompare"></a><span data-ttu-id="2e570-102">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="2e570-102">/optioncompare</span></span>
<span data-ttu-id="2e570-103">Specifica la modalità con cui vengono confrontate le stringhe.</span><span class="sxs-lookup"><span data-stu-id="2e570-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e570-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e570-104">Syntax</span></span>  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="2e570-105">Note</span><span class="sxs-lookup"><span data-stu-id="2e570-105">Remarks</span></span>  
 <span data-ttu-id="2e570-106">È possibile specificare `/optioncompare` in uno dei due formati: `/optioncompare:binary` per utilizzare confronti tra stringhe binarie e `/optioncompare:text` per utilizzare confronti tra stringhe di testo.</span><span class="sxs-lookup"><span data-stu-id="2e570-106">You can specify `/optioncompare` in one of two forms: `/optioncompare:binary` to use binary string comparisons, and `/optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="2e570-107">Per impostazione predefinita, il compilatore utilizza `/optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="2e570-107">By default, the compiler uses `/optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="2e570-108">In Microsoft Windows, la tabella codici utilizzata determina l'ordinamento binario.</span><span class="sxs-lookup"><span data-stu-id="2e570-108">In Microsoft Windows, the code page being used determines the binary sort order.</span></span> <span data-ttu-id="2e570-109">Un tipico ordinamento binario è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2e570-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="2e570-110">Confronti tra stringhe basati su testo sono in base all'ordinamento senza distinzione tra maiuscole determinato dalle impostazioni locali del sistema.</span><span class="sxs-lookup"><span data-stu-id="2e570-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="2e570-111">Un ordinamento testuale tipico è la seguente:</span><span class="sxs-lookup"><span data-stu-id="2e570-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="2e570-112">Per impostare /optioncompare nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e570-112">To set /optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="2e570-113">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="2e570-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2e570-114">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2e570-114">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="2e570-115">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="2e570-115">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="2e570-116">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="2e570-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="2e570-117">Modificare il valore di **Option Compare** casella.</span><span class="sxs-lookup"><span data-stu-id="2e570-117">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set-optioncompare-programmatically"></a><span data-ttu-id="2e570-118">Per impostare /optioncompare a livello di codice</span><span class="sxs-lookup"><span data-stu-id="2e570-118">To set /optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="2e570-119">Vedere [Option Compare (istruzione)](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2e570-119">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e570-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e570-120">Example</span></span>  
 <span data-ttu-id="2e570-121">Il codice seguente compila P`rojFile.vb` e confronti tra stringhe binarie.</span><span class="sxs-lookup"><span data-stu-id="2e570-121">The following code compiles P`rojFile.vb` and uses binary string comparisons.</span></span>  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e570-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e570-122">See Also</span></span>  
 <span data-ttu-id="2e570-123">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e570-123">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2e570-124"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="2e570-124"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="2e570-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="2e570-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="2e570-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="2e570-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="2e570-127"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="2e570-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="2e570-128"> [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2e570-128"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="2e570-129"> [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="2e570-129"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
