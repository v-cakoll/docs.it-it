---
title: La proprietà '<propertyname>' non restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 21a1c4dbab6e26cd1cb848e270bbda9a544c2a67
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400422"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="70cba-102">La proprietà '\<propertyname>' non restituisce un valore in tutti i percorsi del codice</span><span class="sxs-lookup"><span data-stu-id="70cba-102">Property '\<propertyname>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="70cba-103">La proprietà' \<propertyname> ' non restituisce un valore per tutti i percorsi del codice.</span><span class="sxs-lookup"><span data-stu-id="70cba-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="70cba-104">In fase di esecuzione, quando viene usato il risultato, potrebbe verificarsi un'eccezione dovuta a un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="70cba-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="70cba-105">Una routine di proprietà `Get` ha almeno un possibile percorso nel codice che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="70cba-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="70cba-106">È possibile restituire un valore da una routine di proprietà `Get` in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="70cba-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="70cba-107">Assegnare il valore al nome della proprietà, quindi eseguire un' `Exit Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="70cba-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
- <span data-ttu-id="70cba-108">Assegnare il valore al nome della proprietà, quindi eseguire l' `End Get` istruzione.</span><span class="sxs-lookup"><span data-stu-id="70cba-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
- <span data-ttu-id="70cba-109">Includere il valore in un' [istruzione return](../statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="70cba-109">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="70cba-110">Se il controllo passa a `Exit Property` o `End Get` e non è stato assegnato alcun valore al nome della proprietà, la `Get` stored procedure restituisce il valore predefinito del tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="70cba-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="70cba-111">Per ulteriori informazioni, vedere "Behavior" nell' [istruzione Function](../statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="70cba-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="70cba-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="70cba-112">By default, this message is a warning.</span></span> <span data-ttu-id="70cba-113">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="70cba-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="70cba-114">**ID errore:** BC42107</span><span class="sxs-lookup"><span data-stu-id="70cba-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="70cba-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="70cba-115">To correct this error</span></span>  
  
- <span data-ttu-id="70cba-116">Controllare la logica del flusso di controllo e assicurarsi di assegnare un valore prima di ogni istruzione che causa la restituzione.</span><span class="sxs-lookup"><span data-stu-id="70cba-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="70cba-117">È più facile garantire che ogni ritorno dalla procedura restituisca un valore se si usa sempre l' `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="70cba-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="70cba-118">In tal caso, l'ultima istruzione prima `End Get` deve essere un' `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="70cba-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70cba-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70cba-119">See also</span></span>

- [<span data-ttu-id="70cba-120">Routine Property</span><span class="sxs-lookup"><span data-stu-id="70cba-120">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="70cba-121">Property Statement</span><span class="sxs-lookup"><span data-stu-id="70cba-121">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="70cba-122">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="70cba-122">Get Statement</span></span>](../statements/get-statement.md)
