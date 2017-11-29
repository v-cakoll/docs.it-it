---
title: "Proprietà &#39; &lt;propertyname&gt;&#39; &#39; t restituisce un valore in tutti i percorsi del codice"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords: BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c9ef5b2ac62412f5684cbc78ab6bebf6bc7b6752
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="c2cb9-102">Proprietà &#39; &lt;propertyname&gt;&#39; &#39; t restituisce un valore in tutti i percorsi del codice</span><span class="sxs-lookup"><span data-stu-id="c2cb9-102">Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="c2cb9-103">Proprietà '\<NomeProprietà >' non restituisce un valore per tutti i percorsi di codice.</span><span class="sxs-lookup"><span data-stu-id="c2cb9-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="c2cb9-104">In fase di esecuzione, quando viene usato il risultato, potrebbe verificarsi un'eccezione dovuta a un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="c2cb9-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="c2cb9-105">Una proprietà `Get` procedura contiene almeno un possibile percorso all'interno del codice che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="c2cb9-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="c2cb9-106">È possibile restituire un valore da una proprietà `Get` procedura in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2cb9-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="c2cb9-107">Assegnare il valore per il nome della proprietà, quindi eseguire un `Exit Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c2cb9-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="c2cb9-108">Assegnare il valore per il nome della proprietà, quindi eseguire il `End Get` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c2cb9-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="c2cb9-109">Includere il valore in un [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c2cb9-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="c2cb9-110">Se il controllo passa al `Exit Property` o `End Get` e non, è stato assegnato alcun valore per il nome della proprietà di `Get` procedura restituisce il valore predefinito del tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c2cb9-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="c2cb9-111">Per ulteriori informazioni, vedere "Comportamento" in [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c2cb9-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="c2cb9-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="c2cb9-112">By default, this message is a warning.</span></span> <span data-ttu-id="c2cb9-113">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c2cb9-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c2cb9-114">**ID errore:** BC42107</span><span class="sxs-lookup"><span data-stu-id="c2cb9-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c2cb9-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c2cb9-115">To correct this error</span></span>  
  
-   <span data-ttu-id="c2cb9-116">Controllare la logica del flusso di controllo e assicurarsi di assegnare un valore prima di ogni istruzione che causa la restituzione.</span><span class="sxs-lookup"><span data-stu-id="c2cb9-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="c2cb9-117">È più semplice garantire che ogni restituito dalla routine restituisce un valore se si utilizza sempre il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c2cb9-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="c2cb9-118">In questo caso, l'ultima istruzione prima `End Get` deve essere un `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c2cb9-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2cb9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2cb9-119">See Also</span></span>  
 [<span data-ttu-id="c2cb9-120">Routine Property</span><span class="sxs-lookup"><span data-stu-id="c2cb9-120">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="c2cb9-121">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="c2cb9-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="c2cb9-122">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="c2cb9-122">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
