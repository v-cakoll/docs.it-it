---
title: Variabile &#39; &lt;variablename&gt; &#39; viene utilizzato prima che sia stato assegnato un valore
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: d314f952bd6e11adaac642ba63ed292f48cda805
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596919"
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="5d3e0-102">Variabile &#39; &lt;variablename&gt; &#39; viene utilizzato prima che sia stato assegnato un valore</span><span class="sxs-lookup"><span data-stu-id="5d3e0-102">Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value</span></span>
<span data-ttu-id="5d3e0-103">Variabile '\<variablename >' viene utilizzato prima che sia stato assegnato un valore.</span><span class="sxs-lookup"><span data-stu-id="5d3e0-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="5d3e0-104">È possibile che in fase di esecuzione venga restituita un'eccezione dovuta a un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="5d3e0-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="5d3e0-105">Un'applicazione dispone di almeno un possibile percorso all'interno del codice che legge una variabile prima che venga assegnato qualsiasi valore.</span><span class="sxs-lookup"><span data-stu-id="5d3e0-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="5d3e0-106">Se a una variabile non è mai stato assegnato alcun valore, questa manterrà il valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="5d3e0-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="5d3e0-107">Per un tipo di dati di riferimento, il valore predefinito è [nulla](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="5d3e0-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="5d3e0-108">La lettura di una variabile di riferimento con un valore `Nothing` può causare un'eccezione <xref:System.NullReferenceException> in alcune circostanze.</span><span class="sxs-lookup"><span data-stu-id="5d3e0-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="5d3e0-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="5d3e0-109">By default, this message is a warning.</span></span> <span data-ttu-id="5d3e0-110">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5d3e0-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="5d3e0-111">**ID errore:** BC42104</span><span class="sxs-lookup"><span data-stu-id="5d3e0-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5d3e0-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5d3e0-112">To correct this error</span></span>  
  
-   <span data-ttu-id="5d3e0-113">Controllare la logica del flusso di controllo e verificare che la variabile ha un valore valido prima che il controllo passa a qualsiasi istruzione che lo legge.</span><span class="sxs-lookup"><span data-stu-id="5d3e0-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="5d3e0-114">Un modo per garantire che la variabile ha sempre un valore valido è inizializzare come parte della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="5d3e0-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="5d3e0-115">Vedere "Inizializzazione" in [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5d3e0-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d3e0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d3e0-116">See Also</span></span>  
 [<span data-ttu-id="5d3e0-117">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="5d3e0-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="5d3e0-118">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="5d3e0-118">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="5d3e0-119">Risoluzione dei problemi relativi alle variabili</span><span class="sxs-lookup"><span data-stu-id="5d3e0-119">Troubleshooting Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
