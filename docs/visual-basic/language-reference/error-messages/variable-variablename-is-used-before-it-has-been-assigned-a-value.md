---
title: Variabile &quot;&lt;NomeVariabile&gt;&quot; viene utilizzato prima che sia stato assegnato un valore | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
dev_langs:
- VB
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
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
ms.openlocfilehash: dfc924ebbebb8b20654156b8871684dcfad6848a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="35e9a-102">Variabile '&lt;NomeVariabile&gt;' viene utilizzato prima che sia stato assegnato un valore</span><span class="sxs-lookup"><span data-stu-id="35e9a-102">Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value</span></span>
<span data-ttu-id="35e9a-103">Variabile '\<nomevariabile >' viene utilizzato prima che sia stato assegnato un valore.</span><span class="sxs-lookup"><span data-stu-id="35e9a-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="35e9a-104">È possibile che in fase di esecuzione venga restituita un'eccezione dovuta a un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="35e9a-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="35e9a-105">Un'applicazione dispone di almeno un percorso possibile tramite il codice che legge una variabile prima che venga assegnato qualsiasi valore.</span><span class="sxs-lookup"><span data-stu-id="35e9a-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="35e9a-106">Se a una variabile non è mai stato assegnato alcun valore, questa manterrà il valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="35e9a-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="35e9a-107">Per un tipo di dati di riferimento, il valore predefinito è [nulla](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="35e9a-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="35e9a-108">Lettura di una variabile di riferimento con un valore di `Nothing` può causare un <xref:System.NullReferenceException>in alcune circostanze.</xref:System.NullReferenceException></span><span class="sxs-lookup"><span data-stu-id="35e9a-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="35e9a-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="35e9a-109">By default, this message is a warning.</span></span> <span data-ttu-id="35e9a-110">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="35e9a-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="35e9a-111">**ID errore:** BC42104</span><span class="sxs-lookup"><span data-stu-id="35e9a-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="35e9a-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="35e9a-112">To correct this error</span></span>  
  
-   <span data-ttu-id="35e9a-113">Controllare la logica del flusso di controllo e assicurarsi che la variabile ha un valore valido prima che il controllo passa all'istruzione che legge.</span><span class="sxs-lookup"><span data-stu-id="35e9a-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="35e9a-114">Un modo per garantire che la variabile ha sempre un valore valido consiste nell'inizializzare come parte della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="35e9a-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="35e9a-115">Vedere "Inizializzazione" in [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="35e9a-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e9a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35e9a-116">See Also</span></span>  
 <span data-ttu-id="35e9a-117">[Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="35e9a-117">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="35e9a-118"> [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="35e9a-118"> [Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="35e9a-119"> [Risoluzione dei problemi relativi alle variabili](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)</span><span class="sxs-lookup"><span data-stu-id="35e9a-119"> [Troubleshooting Variables](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)</span></span>
