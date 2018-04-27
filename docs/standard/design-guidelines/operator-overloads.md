---
title: Overload dell'operatore
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 42a28f34dda77ecff47f0765335fc29e4418529e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="operator-overloads"></a><span data-ttu-id="35b48-102">Overload dell'operatore</span><span class="sxs-lookup"><span data-stu-id="35b48-102">Operator Overloads</span></span>
<span data-ttu-id="35b48-103">Overload degli operatori consente ai tipi di framework di vengono visualizzati come se fossero primitive di linguaggio predefinito.</span><span class="sxs-lookup"><span data-stu-id="35b48-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>  
  
 <span data-ttu-id="35b48-104">Anche se è consentito e utili in alcuni casi, gli overload degli operatori deve essere utilizzata con cautela.</span><span class="sxs-lookup"><span data-stu-id="35b48-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="35b48-105">Esistono molti casi, in operatore che l'overload è stato eccessivo, ad esempio l'avvio di finestre di progettazione framework come utilizzare gli operatori per le operazioni che devono essere metodi semplici.</span><span class="sxs-lookup"><span data-stu-id="35b48-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="35b48-106">Le linee guida seguenti consentono di decidere quando e come utilizzare l'overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="35b48-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>  
  
 <span data-ttu-id="35b48-107">**X evitare** definizione overload degli operatori, tranne nei tipi che dovrebbero risultare come tipi primitivi (predefiniti).</span><span class="sxs-lookup"><span data-stu-id="35b48-107">**X AVOID** defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>  
  
 <span data-ttu-id="35b48-108">**✓ Provare a** definizione overload degli operatori in un tipo che deve essere, ad esempio un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="35b48-108">**✓ CONSIDER** defining operator overloads in a type that should feel like a primitive type.</span></span>  
  
 <span data-ttu-id="35b48-109">Ad esempio, <xref:System.String?displayProperty=nameWithType> è `operator==` e `operator!=` definito.</span><span class="sxs-lookup"><span data-stu-id="35b48-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>  
  
 <span data-ttu-id="35b48-110">**✓ SI** definire gli overload degli operatori in strutture che rappresentano numeri (ad esempio <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="35b48-110">**✓ DO** define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="35b48-111">**X non** essere mentre quando si definiscono gli overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="35b48-111">**X DO NOT** be cute when defining operator overloads.</span></span>  
  
 <span data-ttu-id="35b48-112">Overload dell'operatore è utile nei casi in cui è immediatamente ovvio il risultato dell'operazione sarà.</span><span class="sxs-lookup"><span data-stu-id="35b48-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="35b48-113">Ad esempio, è opportuno essere in grado di sottrarre uno <xref:System.DateTime> da un altro `DateTime` e ottenere un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="35b48-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="35b48-114">Tuttavia, non è appropriata per utilizzare l'operatore union logico per le query di unione due database, o utilizzare l'operatore di spostamento per scrivere in un flusso.</span><span class="sxs-lookup"><span data-stu-id="35b48-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>  
  
 <span data-ttu-id="35b48-115">**X non** forniscono gli overload di operatori, a meno che almeno uno degli operandi è di tipo che definisce l'overload.</span><span class="sxs-lookup"><span data-stu-id="35b48-115">**X DO NOT** provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>  
  
 <span data-ttu-id="35b48-116">**✓ SI** overload degli operatori in modo simmetrico.</span><span class="sxs-lookup"><span data-stu-id="35b48-116">**✓ DO** overload operators in a symmetric fashion.</span></span>  
  
 <span data-ttu-id="35b48-117">Ad esempio, se si esegue l'overload di `operator==`, inoltre, è necessario eseguire l'overload di `operator!=`.</span><span class="sxs-lookup"><span data-stu-id="35b48-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="35b48-118">Analogamente, se esegue l'overload di `operator<`, è inoltre necessario eseguire l'overload di `operator>`e così via.</span><span class="sxs-lookup"><span data-stu-id="35b48-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>  
  
 <span data-ttu-id="35b48-119">**✓ Provare a** fornendo i metodi con nomi descrittivi che corrispondono a ogni operatore di overload.</span><span class="sxs-lookup"><span data-stu-id="35b48-119">**✓ CONSIDER** providing methods with friendly names that correspond to each overloaded operator.</span></span>  
  
 <span data-ttu-id="35b48-120">Molti linguaggi non supportano l'overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="35b48-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="35b48-121">Per questo motivo, è consigliabile che i tipi di overload degli operatori includono un metodo secondario con un nome specifico di dominio appropriato che fornisce una funzionalità equivalente.</span><span class="sxs-lookup"><span data-stu-id="35b48-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>  
  
 <span data-ttu-id="35b48-122">Nella tabella seguente contiene un elenco di operatori e i nomi di metodo descrittivo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="35b48-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>  
  
|<span data-ttu-id="35b48-123">Simbolo dell'operatore c#</span><span class="sxs-lookup"><span data-stu-id="35b48-123">C# Operator Symbol</span></span>|<span data-ttu-id="35b48-124">Nome dei metadati</span><span class="sxs-lookup"><span data-stu-id="35b48-124">Metadata Name</span></span>|<span data-ttu-id="35b48-125">Nome descrittivo</span><span class="sxs-lookup"><span data-stu-id="35b48-125">Friendly Name</span></span>|  
|-------------------------|-------------------|-------------------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|  
|`=`|`op_Assign`|`Assign`|  
|`<<`|`op_LeftShift`|`LeftShift`|  
|`>>`|`op_RightShift`|`RightShift`|  
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|  
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|  
|`==`|`op_Equality`|`Equals`|  
|`!=`|`op_Inequality`|`Equals`|  
|`>`|`op_GreaterThan`|`CompareTo`|  
|`<`|`op_LessThan`|`CompareTo`|  
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|  
|`<=`|`op_LessThanOrEqual`|`CompareTo`|  
|`*=`|`op_MultiplicationAssignment`|`Multiply`|  
|`-=`|`op_SubtractionAssignment`|`Subtract`|  
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|  
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|  
|`%=`|`op_ModulusAssignment`|`Mod`|  
|`+=`|`op_AdditionAssignment`|`Add`|  
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|  
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### <a name="overloading-operator-"></a><span data-ttu-id="35b48-126">Overload dell'operatore = =</span><span class="sxs-lookup"><span data-stu-id="35b48-126">Overloading Operator ==</span></span>  
 <span data-ttu-id="35b48-127">L'overload `operator ==` è piuttosto complessi.</span><span class="sxs-lookup"><span data-stu-id="35b48-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="35b48-128">La semantica dell'operatore desidera essere compatibili con molti altri membri, ad esempio <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="35b48-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="conversion-operators"></a><span data-ttu-id="35b48-129">Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="35b48-129">Conversion Operators</span></span>  
 <span data-ttu-id="35b48-130">Gli operatori di conversione sono gli operatori unari che consentono la conversione da un tipo a un altro.</span><span class="sxs-lookup"><span data-stu-id="35b48-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="35b48-131">Gli operatori devono essere definiti come membri statici in cui l'operando o il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="35b48-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="35b48-132">Esistono due tipi di operatori di conversione: implicite ed esplicite.</span><span class="sxs-lookup"><span data-stu-id="35b48-132">There are two types of conversion operators: implicit and explicit.</span></span>  
  
 <span data-ttu-id="35b48-133">**X non** forniscono un operatore di conversione se tale conversione non è previsto chiaramente dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="35b48-133">**X DO NOT** provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>  
  
 <span data-ttu-id="35b48-134">**X non** definire operatori di conversione di fuori di dominio del tipo.</span><span class="sxs-lookup"><span data-stu-id="35b48-134">**X DO NOT** define conversion operators outside of a type’s domain.</span></span>  
  
 <span data-ttu-id="35b48-135">Ad esempio, <xref:System.Int32>, <xref:System.Double>, e <xref:System.Decimal> sono tutti i tipi numerici, mentre <xref:System.DateTime> non.</span><span class="sxs-lookup"><span data-stu-id="35b48-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="35b48-136">Pertanto, non deve essere presente nessun operatore di conversione per convertire un `Double(long)` per un `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="35b48-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="35b48-137">In questo caso è preferibile utilizzare un costruttore.</span><span class="sxs-lookup"><span data-stu-id="35b48-137">A constructor is preferred in such a case.</span></span>  
  
 <span data-ttu-id="35b48-138">**X non** forniscono un operatore di conversione implicita, se la conversione è potenzialmente perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="35b48-138">**X DO NOT** provide an implicit conversion operator if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="35b48-139">Ad esempio, deve essere presente una conversione implicita da `Double` a `Int32` perché `Double` ha una gamma più ampia rispetto a `Int32`.</span><span class="sxs-lookup"><span data-stu-id="35b48-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="35b48-140">Anche se la conversione è potenzialmente perdita di dati, è possibile specificare un operatore di conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="35b48-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="35b48-141">**X non** generare eccezioni da cast impliciti.</span><span class="sxs-lookup"><span data-stu-id="35b48-141">**X DO NOT** throw exceptions from implicit casts.</span></span>  
  
 <span data-ttu-id="35b48-142">È molto difficile per gli utenti finali a comprendere ciò che accade, poiché potrebbero non essere consapevoli che una conversione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="35b48-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>  
  
 <span data-ttu-id="35b48-143">**✓ SI** throw <xref:System.InvalidCastException?displayProperty=nameWithType> se una chiamata a un operatore cast comporta una perdita di dati conversione e il contratto dell'operatore non consente conversioni perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="35b48-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>  
  
 <span data-ttu-id="35b48-144">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="35b48-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="35b48-145">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="35b48-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b48-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35b48-146">See Also</span></span>  
 [<span data-ttu-id="35b48-147">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="35b48-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="35b48-148">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="35b48-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
