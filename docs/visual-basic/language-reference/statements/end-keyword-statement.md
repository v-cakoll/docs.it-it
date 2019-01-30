---
title: Istruzione End <keyword> (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 96dc8ce6b0d3b7545f5caeef43358936e426f566
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273530"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="88660-102">Fine \<parola chiave > istruzione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88660-102">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="88660-103">Quando è seguito da una parola chiave aggiuntiva, termina la definizione del blocco di istruzione introdotta dalla parola chiave.</span><span class="sxs-lookup"><span data-stu-id="88660-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="88660-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="88660-104">Syntax</span></span>

```vb
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
  
## <a name="parts"></a><span data-ttu-id="88660-105">Parti</span><span class="sxs-lookup"><span data-stu-id="88660-105">Parts</span></span>

|<span data-ttu-id="88660-106">Parte</span><span class="sxs-lookup"><span data-stu-id="88660-106">Part</span></span>|<span data-ttu-id="88660-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88660-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="88660-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="88660-108">Required.</span></span> <span data-ttu-id="88660-109">Termina la definizione dell'elemento di programmazione.</span><span class="sxs-lookup"><span data-stu-id="88660-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="88660-110">Necessario per terminare un' `AddHandler` funzione di accesso iniziato da un oggetto corrispondente `AddHandler` istruzione in un oggetto personalizzato [istruzione Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="88660-111">Necessario per terminare una definizione di classe iniziata da un oggetto corrispondente [istruzione Class](class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="88660-112">Necessario per terminare una definizione di enumerazione iniziata da un oggetto corrispondente [istruzione Enum](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="88660-113">Necessario per terminare una `Custom` definizione di evento avviato da un oggetto corrispondente [istruzione Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="88660-114">Necessario per terminare una `Function` definizione della stored procedure iniziato da un oggetto corrispondente [istruzione Function](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="88660-115">Se l'esecuzione rileva un `End Function` istruzione, restituisce il controllo al codice chiama.</span><span class="sxs-lookup"><span data-stu-id="88660-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="88660-116">Necessario per terminare una `Property` definizione della stored procedure iniziato da un oggetto corrispondente [Get Statement](get-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="88660-117">Se l'esecuzione rileva un `End Get` istruzione, controllo viene restituito all'istruzione che richiede il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="88660-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="88660-118">Necessario per terminare un `If`... `Then`... `Else` iniziata da un oggetto corrispondente `If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="88660-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="88660-119">Vedere [se... Quindi... Istruzione else](if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="88660-120">Necessario per terminare una definizione di interfaccia iniziata da un oggetto corrispondente [Interface (istruzione)](interface-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="88660-121">Necessario per terminare una definizione di modulo iniziata da un oggetto corrispondente [Module Statement](module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="88660-122">Necessario per terminare una definizione dello spazio dei nomi iniziata da un oggetto corrispondente [istruzione Namespace](namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="88660-123">Necessario per terminare una definizione di operatore iniziata da un oggetto corrispondente [Operator Statement](operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="88660-124">Necessario per terminare una definizione di proprietà iniziata da un oggetto corrispondente [Property Statement](property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="88660-125">Necessario per terminare una `RaiseEvent` funzione di accesso iniziato da un oggetto corrispondente `RaiseEvent` istruzione in un oggetto personalizzato [istruzione Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="88660-126">Necessario per terminare una `RemoveHandler` funzione di accesso iniziato da un oggetto corrispondente `RemoveHandler` istruzione in un oggetto personalizzato [istruzione Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="88660-127">Necessario per terminare un `Select`... `Case` iniziata da un oggetto corrispondente `Select` istruzione.</span><span class="sxs-lookup"><span data-stu-id="88660-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="88660-128">Vedere [Seleziona... Istruzione case](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="88660-129">Necessario per terminare una `Property` definizione della stored procedure iniziato da un oggetto corrispondente [istruzione Set](set-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="88660-130">Se l'esecuzione rileva un `End Set` istruzione, controllo viene restituito all'istruzione che imposta il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="88660-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="88660-131">Necessario per terminare una definizione di struttura iniziata da un oggetto corrispondente [istruzione Structure](structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="88660-132">Necessario per terminare una `Sub` definizione della stored procedure iniziato da un oggetto corrispondente [istruzione Sub](sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="88660-133">Se l'esecuzione rileva un `End Sub` istruzione, restituisce il controllo al codice chiama.</span><span class="sxs-lookup"><span data-stu-id="88660-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="88660-134">Necessario per terminare una `SyncLock` iniziata da un oggetto corrispondente `SyncLock` istruzione.</span><span class="sxs-lookup"><span data-stu-id="88660-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="88660-135">Visualizzare [istruzione SyncLock](synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="88660-136">Necessario per terminare un `Try`... `Catch`... `Finally` iniziata da un oggetto corrispondente `Try` istruzione.</span><span class="sxs-lookup"><span data-stu-id="88660-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="88660-137">Vedere [Try... Catch... Istruzione finally](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="88660-138">Necessario per terminare una `While` iniziato da un oggetto corrispondente definizione del ciclo `While` istruzione.</span><span class="sxs-lookup"><span data-stu-id="88660-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="88660-139">Vedere [mentre... End While (istruzione)](while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="88660-140">Necessario per terminare una `With` iniziata da un oggetto corrispondente `With` istruzione.</span><span class="sxs-lookup"><span data-stu-id="88660-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="88660-141">Vedere [con... Terminare con istruzione](with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88660-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="88660-142">Direttive</span><span class="sxs-lookup"><span data-stu-id="88660-142">Directives</span></span>

<span data-ttu-id="88660-143">Quando è preceduta da un simbolo di cancelletto (`#`), il `End` (parola chiave) termina un blocco di pre-elaborazione introdotto dall'istruzione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="88660-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="88660-144">Parte</span><span class="sxs-lookup"><span data-stu-id="88660-144">Part</span></span>|<span data-ttu-id="88660-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88660-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="88660-146">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="88660-146">Required.</span></span> <span data-ttu-id="88660-147">Termina la definizione del blocco di pre-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="88660-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="88660-148">Necessario per terminare un blocco di origine esterna iniziato da un oggetto corrispondente [#ExternalSource direttiva](../directives/externalsource-directive.md).</span><span class="sxs-lookup"><span data-stu-id="88660-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="88660-149">Necessario per terminare un blocco di compilazione condizionale iniziato da un oggetto corrispondente `#If` direttiva.</span><span class="sxs-lookup"><span data-stu-id="88660-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="88660-150">Vedere [#If... Then... #Else direttive](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="88660-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="88660-151">Necessario per terminare un blocco di area di origine iniziato da un oggetto corrispondente [#Region direttiva](../directives/region-directive.md).</span><span class="sxs-lookup"><span data-stu-id="88660-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="88660-152">Note</span><span class="sxs-lookup"><span data-stu-id="88660-152">Remarks</span></span>

<span data-ttu-id="88660-153">Il [istruzione End](end-statement.md), senza una parola chiave aggiuntiva, termina l'esecuzione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="88660-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="88660-154">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="88660-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="88660-155">Il `End` alcuna parola chiave aggiuntiva, l'istruzione non è supportato.</span><span class="sxs-lookup"><span data-stu-id="88660-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88660-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88660-156">See also</span></span>

- [<span data-ttu-id="88660-157">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="88660-157">End Statement</span></span>](end-statement.md)
