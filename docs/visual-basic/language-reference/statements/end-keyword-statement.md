---
title: Istruzione End <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 87f4724cc036e6e0bdf0b558854a4034f45b9ab5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343743"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="add44-102">End \<parola chiave > Statement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="add44-102">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="add44-103">Quando seguito da una parola chiave aggiuntiva, termina la definizione del blocco di istruzioni introdotto da tale parola chiave.</span><span class="sxs-lookup"><span data-stu-id="add44-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="add44-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="add44-104">Syntax</span></span>

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
  
## <a name="parts"></a><span data-ttu-id="add44-105">Parti</span><span class="sxs-lookup"><span data-stu-id="add44-105">Parts</span></span>

|<span data-ttu-id="add44-106">Parte</span><span class="sxs-lookup"><span data-stu-id="add44-106">Part</span></span>|<span data-ttu-id="add44-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="add44-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="add44-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="add44-108">Required.</span></span> <span data-ttu-id="add44-109">Termina la definizione dell'elemento di programmazione.</span><span class="sxs-lookup"><span data-stu-id="add44-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="add44-110">Obbligatorio per terminare una funzione di accesso `AddHandler` iniziata da un'istruzione `AddHandler` corrispondente in un' [istruzione di evento](event-statement.md)personalizzata.</span><span class="sxs-lookup"><span data-stu-id="add44-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="add44-111">Obbligatorio per terminare una definizione di classe iniziata da un' [istruzione di classe](class-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="add44-112">Obbligatorio per terminare una definizione di enumerazione iniziata da un' [istruzione enum](enum-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="add44-113">Obbligatorio per terminare una definizione di evento `Custom` iniziata da un' [istruzione di evento](event-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="add44-114">Obbligatorio per terminare una definizione di routine `Function` iniziata da un' [istruzione Function](function-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="add44-115">Se l'esecuzione rileva un'istruzione `End Function`, il controllo viene restituito al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="add44-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="add44-116">Obbligatorio per terminare una definizione di routine `Property` iniziata da un' [istruzione Get](get-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="add44-117">Se l'esecuzione rileva un'istruzione `End Get`, il controllo torna all'istruzione che richiede il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="add44-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="add44-118">Obbligatorio per terminare una definizione del blocco `If`...`Then`...`Else` iniziata da un'istruzione `If` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="add44-119">Vedere [if... Quindi... Else (istruzione](if-then-else-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="add44-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="add44-120">Obbligatorio per terminare una definizione di interfaccia iniziata da un' [istruzione di interfaccia](interface-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="add44-121">Obbligatorio per terminare la definizione di un modulo iniziata da un' [istruzione del modulo](module-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="add44-122">Obbligatorio per terminare una definizione dello spazio dei nomi iniziata da un' [istruzione dello spazio dei nomi](namespace-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="add44-123">Obbligatorio per terminare la definizione di un operatore iniziata da un' [istruzione di operatore](operator-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="add44-124">Obbligatorio per terminare una definizione di proprietà iniziata da un' [istruzione Property](property-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="add44-125">Obbligatorio per terminare una funzione di accesso `RaiseEvent` iniziata da un'istruzione `RaiseEvent` corrispondente in un' [istruzione di evento](event-statement.md)personalizzata.</span><span class="sxs-lookup"><span data-stu-id="add44-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="add44-126">Obbligatorio per terminare una funzione di accesso `RemoveHandler` iniziata da un'istruzione `RemoveHandler` corrispondente in un' [istruzione di evento](event-statement.md)personalizzata.</span><span class="sxs-lookup"><span data-stu-id="add44-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="add44-127">Obbligatorio per terminare un `Select`...`Case` definizione del blocco iniziata da un'istruzione `Select` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="add44-128">Vedere [Select... Istruzione case](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="add44-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="add44-129">Obbligatorio per terminare una definizione di routine `Property` iniziata da un' [istruzione set](set-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="add44-130">Se l'esecuzione rileva un'istruzione `End Set`, il controllo torna all'istruzione impostando il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="add44-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="add44-131">Obbligatorio per terminare una definizione di struttura iniziata da un' [istruzione di struttura](structure-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="add44-132">Obbligatorio per terminare una definizione di routine `Sub` iniziata da un' [istruzione secondaria](sub-statement.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="add44-133">Se l'esecuzione rileva un'istruzione `End Sub`, il controllo viene restituito al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="add44-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="add44-134">Obbligatorio per terminare una definizione di blocco `SyncLock` iniziata da un'istruzione `SyncLock` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="add44-135">Vedere l' [istruzione SyncLock](synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="add44-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="add44-136">Obbligatorio per terminare una definizione del blocco `Try`...`Catch`...`Finally` iniziata da un'istruzione `Try` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="add44-137">Vedere [try... Rileva... Istruzione finally](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="add44-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="add44-138">Obbligatorio per terminare una definizione del ciclo `While` iniziata da un'istruzione `While` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="add44-139">Vedi [while... End While (istruzione](while-end-while-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="add44-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="add44-140">Obbligatorio per terminare una definizione di blocco `With` iniziata da un'istruzione `With` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="add44-141">Vedi [con... Termina con l'istruzione](with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="add44-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="add44-142">Direttive</span><span class="sxs-lookup"><span data-stu-id="add44-142">Directives</span></span>

<span data-ttu-id="add44-143">Quando è preceduto da un simbolo di cancelletto (`#`), la parola chiave `End` termina un blocco di pre-elaborazione introdotto dalla direttiva corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="add44-144">Parte</span><span class="sxs-lookup"><span data-stu-id="add44-144">Part</span></span>|<span data-ttu-id="add44-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="add44-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="add44-146">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="add44-146">Required.</span></span> <span data-ttu-id="add44-147">Termina la definizione del blocco di pre-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="add44-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="add44-148">Obbligatorio per terminare un blocco di origine esterno iniziato da una [direttiva #ExternalSource](../directives/externalsource-directive.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="add44-149">Obbligatorio per terminare un blocco di compilazione condizionale iniziato da una direttiva `#If` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="add44-150">Vedere [#If... Quindi... #Else direttive](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="add44-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="add44-151">Obbligatorio per terminare un blocco di area di origine iniziato da una [direttiva #Region](../directives/region-directive.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="add44-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="add44-152">Note</span><span class="sxs-lookup"><span data-stu-id="add44-152">Remarks</span></span>

<span data-ttu-id="add44-153">L' [istruzione End](end-statement.md), senza una parola chiave aggiuntiva, termina immediatamente l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="add44-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="add44-154">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="add44-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="add44-155">L'istruzione `End`, senza una parola chiave aggiuntiva, non è supportata.</span><span class="sxs-lookup"><span data-stu-id="add44-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="add44-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="add44-156">See also</span></span>

- [<span data-ttu-id="add44-157">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="add44-157">End Statement</span></span>](end-statement.md)
