---
title: Fine &lt;parola chiave&gt; istruzione (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf0ac1221f8a85a8a43599d9c5ec210884205e5e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a><span data-ttu-id="d0926-102">Fine &lt;parola chiave&gt; istruzione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0926-102">End &lt;keyword&gt; Statement (Visual Basic)</span></span>
<span data-ttu-id="d0926-103">Quando è seguito da una parola chiave aggiuntiva, termina la definizione del blocco di istruzioni introdotto dalla parola chiave.</span><span class="sxs-lookup"><span data-stu-id="d0926-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0926-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0926-104">Syntax</span></span>  
  
```  
End AddHandler  
End Class   
End Enum   
End Event   
End Function   
End Get   
End If   
End Interface   
End Module   
End Namespace   
End Operator   
End Property   
End RaiseEvent  
End RemoveHandler  
End Select   
End Set   
End Structure   
End Sub   
End SyncLock   
End Try   
End While   
End With  
```  
  
## <a name="parts"></a><span data-ttu-id="d0926-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d0926-105">Parts</span></span>  
 `End`  
 <span data-ttu-id="d0926-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d0926-106">Required.</span></span> <span data-ttu-id="d0926-107">Termina la definizione dell'elemento di programmazione.</span><span class="sxs-lookup"><span data-stu-id="d0926-107">Terminates the definition of the programming element.</span></span>  
  
 `AddHandler`  
 <span data-ttu-id="d0926-108">Necessaria per terminare un `AddHandler` funzione di accesso iniziata da un oggetto corrispondente `AddHandler` istruzione in un oggetto personalizzato [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-108">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Class`  
 <span data-ttu-id="d0926-109">È necessario terminare una definizione di classe iniziata da un oggetto corrispondente [istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-109">Required to terminate a class definition begun by a matching [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
 `Enum`  
 <span data-ttu-id="d0926-110">È necessario terminare una definizione di enumerazione iniziata da un oggetto corrispondente [istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-110">Required to terminate an enumeration definition begun by a matching [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 `Event`  
 <span data-ttu-id="d0926-111">Necessaria per terminare un `Custom` definizione di evento iniziata da un oggetto corrispondente [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-111">Required to terminate a `Custom` event definition begun by a matching [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Function`  
 <span data-ttu-id="d0926-112">Necessaria per terminare un `Function` iniziato mediante una corrispondente definizione della stored procedure [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-112">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="d0926-113">Se l'esecuzione incontra un `End``Function` istruzione, controllo viene restituito il codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="d0926-113">If execution encounters an `End``Function` statement, control returns to the calling code.</span></span>  
  
 `Get`  
 <span data-ttu-id="d0926-114">Necessaria per terminare un `Property` iniziato mediante una corrispondente definizione della stored procedure [l'istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-114">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md).</span></span> <span data-ttu-id="d0926-115">Se l'esecuzione incontra un `End``Get` istruzione, controllo viene restituito all'istruzione che richiede il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0926-115">If execution encounters an `End``Get` statement, control returns to the statement requesting the property's value.</span></span>  
  
 `If`  
 <span data-ttu-id="d0926-116">Necessaria per terminare un `If`... `Then`... `Else` iniziata da un oggetto corrispondente `If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0926-116">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="d0926-117">Vedere [se... Quindi... Istruzione else](../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-117">See [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span>  
  
 `Interface`  
 <span data-ttu-id="d0926-118">È necessario terminare una definizione di interfaccia iniziata da un oggetto corrispondente [istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-118">Required to terminate an interface definition begun by a matching [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md).</span></span>  
  
 `Module`  
 <span data-ttu-id="d0926-119">È necessario terminare una definizione di modulo iniziata da un oggetto corrispondente [istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-119">Required to terminate a module definition begun by a matching [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
 `Namespace`  
 <span data-ttu-id="d0926-120">È necessario terminare una definizione di spazio dei nomi iniziata da un oggetto corrispondente [istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-120">Required to terminate a namespace definition begun by a matching [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span>  
  
 `Operator`  
 <span data-ttu-id="d0926-121">È necessario terminare una definizione di operatore iniziata da un oggetto corrispondente [Operator (istruzione)](../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-121">Required to terminate an operator definition begun by a matching [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 `Property`  
 <span data-ttu-id="d0926-122">È necessario terminare una definizione di proprietà iniziata da un oggetto corrispondente [istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-122">Required to terminate a property definition begun by a matching [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
 `RaiseEvent`  
 <span data-ttu-id="d0926-123">Necessaria per terminare un `RaiseEvent` funzione di accesso iniziata da un oggetto corrispondente `RaiseEvent` istruzione in un oggetto personalizzato [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-123">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `RemoveHandler`  
 <span data-ttu-id="d0926-124">Necessaria per terminare un `RemoveHandler` funzione di accesso iniziata da un oggetto corrispondente `RemoveHandler` istruzione in un oggetto personalizzato [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-124">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Select`  
 <span data-ttu-id="d0926-125">Necessaria per terminare un `Select`... `Case` iniziata da un oggetto corrispondente `Select` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0926-125">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="d0926-126">Vedere [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-126">See [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
 `Set`  
 <span data-ttu-id="d0926-127">Necessaria per terminare un `Property` iniziato mediante una corrispondente definizione della stored procedure [istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-127">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md).</span></span> <span data-ttu-id="d0926-128">Se l'esecuzione incontra un `End``Set` istruzione, controllo viene restituito all'istruzione che imposta il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0926-128">If execution encounters an `End``Set` statement, control returns to the statement setting the property's value.</span></span>  
  
 `Structure`  
 <span data-ttu-id="d0926-129">È necessario terminare una definizione di struttura iniziata da un oggetto corrispondente [istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-129">Required to terminate a structure definition begun by a matching [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
 `Sub`  
 <span data-ttu-id="d0926-130">Necessaria per terminare un `Sub` iniziato mediante una corrispondente definizione della stored procedure [istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-130">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span> <span data-ttu-id="d0926-131">Se l'esecuzione incontra un `End``Sub` istruzione, controllo viene restituito il codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="d0926-131">If execution encounters an `End``Sub` statement, control returns to the calling code.</span></span>  
  
 `SyncLock`  
 <span data-ttu-id="d0926-132">Necessaria per terminare un `SyncLock` iniziata da un oggetto corrispondente `SyncLock` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0926-132">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="d0926-133">Vedere [istruzione SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-133">See [SyncLock Statement](../../../visual-basic/language-reference/statements/synclock-statement.md).</span></span>  
  
 `Try`  
 <span data-ttu-id="d0926-134">Necessaria per terminare un `Try`... `Catch`... `Finally` iniziata da un oggetto corrispondente `Try` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0926-134">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="d0926-135">Vedere [provare... Catch... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-135">See [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 `While`  
 <span data-ttu-id="d0926-136">Necessaria per terminare un `While` ciclo iniziata da un oggetto corrispondente `While` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0926-136">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="d0926-137">Vedere [mentre... End While (istruzione)](../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-137">See [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
 `With`  
 <span data-ttu-id="d0926-138">Necessaria per terminare un `With` iniziata da un oggetto corrispondente `With` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0926-138">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="d0926-139">Vedere [con... Terminare con l'istruzione](../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-139">See [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0926-140">Note</span><span class="sxs-lookup"><span data-stu-id="d0926-140">Remarks</span></span>  
 <span data-ttu-id="d0926-141">Il [istruzione End](../../../visual-basic/language-reference/statements/end-statement.md), senza una parola chiave aggiuntiva, termina immediatamente l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d0926-141">The [End Statement](../../../visual-basic/language-reference/statements/end-statement.md), without an additional keyword, terminates execution immediately.</span></span>  
  
 <span data-ttu-id="d0926-142">Quando è preceduta da un simbolo di cancelletto (`#`), il `End` (parola chiave) termina un blocco di pre-elaborazione introdotto dalla direttiva corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d0926-142">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  
  
 `#End`  
 <span data-ttu-id="d0926-143">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d0926-143">Required.</span></span> <span data-ttu-id="d0926-144">Termina la definizione del blocco di pre-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d0926-144">Terminates the definition of the preprocessing block.</span></span>  
  
 `#ExternalSource`  
 <span data-ttu-id="d0926-145">È necessario terminare un blocco di codice sorgente esterno iniziato da un oggetto corrispondente [#ExternalSource direttiva](../../../visual-basic/language-reference/directives/externalsource-directive.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-145">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md).</span></span>  
  
 `#If`  
 <span data-ttu-id="d0926-146">È necessario terminare un blocco di compilazione condizionale iniziato da un oggetto corrispondente `#If` direttiva.</span><span class="sxs-lookup"><span data-stu-id="d0926-146">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="d0926-147">Vedere [#If... Then... #Else direttive](../../../visual-basic/language-reference/directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-147">See [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md).</span></span>  
  
 `#Region`  
 <span data-ttu-id="d0926-148">È necessario terminare un blocco di area di origine iniziato da un oggetto corrispondente [#Region direttiva](../../../visual-basic/language-reference/directives/region-directive.md).</span><span class="sxs-lookup"><span data-stu-id="d0926-148">Required to terminate a source region block begun by a matching [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md).</span></span>  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="d0926-149">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="d0926-149">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="d0926-150">Il `End` istruzione, senza la parola chiave aggiuntiva, non è supportata.</span><span class="sxs-lookup"><span data-stu-id="d0926-150">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0926-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0926-151">See Also</span></span>  
 [<span data-ttu-id="d0926-152">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="d0926-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
