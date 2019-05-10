---
title: La proprietà '<propertyname>' non restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: a5cb28a024274e58da1755b437d6ba4ca6712610
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661710"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="2150a-102">Proprietà '\<NomeProprietà >' non restituisce un valore per tutti i percorsi del codice</span><span class="sxs-lookup"><span data-stu-id="2150a-102">Property '\<propertyname>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="2150a-103">Proprietà '\<NomeProprietà >' non restituisce un valore per tutti i percorsi del codice.</span><span class="sxs-lookup"><span data-stu-id="2150a-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="2150a-104">In fase di esecuzione, quando viene usato il risultato, potrebbe verificarsi un'eccezione dovuta a un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="2150a-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="2150a-105">Una proprietà `Get` procedure dispone di almeno un possibile percorso all'interno del codice che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="2150a-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="2150a-106">È possibile restituire un valore da una proprietà `Get` procedure in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2150a-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="2150a-107">Assegnare il valore per il nome della proprietà, quindi eseguire un `Exit Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2150a-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
- <span data-ttu-id="2150a-108">Assegnare il valore per il nome della proprietà, quindi eseguire il `End Get` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2150a-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
- <span data-ttu-id="2150a-109">Includere il valore in una [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2150a-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="2150a-110">Se il controllo passa al `Exit Property` oppure `End Get` e non è stato assegnato alcun valore per il nome della proprietà di `Get` procedure restituisce il valore predefinito della proprietà tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="2150a-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="2150a-111">Per altre informazioni, vedere "Comportamento di" nella [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2150a-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="2150a-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="2150a-112">By default, this message is a warning.</span></span> <span data-ttu-id="2150a-113">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2150a-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2150a-114">**ID errore:** BC42107</span><span class="sxs-lookup"><span data-stu-id="2150a-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2150a-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2150a-115">To correct this error</span></span>  
  
- <span data-ttu-id="2150a-116">Controllare la logica del flusso di controllo e assicurarsi che si assegna un valore prima di ogni istruzione che provoca un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="2150a-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="2150a-117">È più semplice garantire che ogni restituito dalla routine restituisce un valore se si usano sempre il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2150a-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="2150a-118">Se si esegue questa operazione, l'ultima istruzione che precede `End Get` deve essere un `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2150a-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2150a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2150a-119">See also</span></span>

- [<span data-ttu-id="2150a-120">Routine Property</span><span class="sxs-lookup"><span data-stu-id="2150a-120">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="2150a-121">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="2150a-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="2150a-122">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="2150a-122">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
