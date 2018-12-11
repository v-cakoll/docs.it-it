---
title: Overload dell'operatore
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
author: KrzysztofCwalina
ms.openlocfilehash: d1b9d8bc1f5f6f83a50dbd798894f94937320d2b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152136"
---
# <a name="operator-overloads"></a><span data-ttu-id="bafba-102">Overload dell'operatore</span><span class="sxs-lookup"><span data-stu-id="bafba-102">Operator Overloads</span></span>
<span data-ttu-id="bafba-103">Overload degli operatori consentono tipi di framework venga visualizzato come se fossero primitive di linguaggio predefinito.</span><span class="sxs-lookup"><span data-stu-id="bafba-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>  
  
 <span data-ttu-id="bafba-104">Sebbene sia consentita e utili in alcuni casi, gli overload degli operatori deve essere utilizzata con cautela.</span><span class="sxs-lookup"><span data-stu-id="bafba-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="bafba-105">Ci sono molti i casi in cui operatore l'overload è stato fatto un uso improprio, ad esempio quando le finestre di progettazione di framework iniziato a usare gli operatori per le operazioni che devono essere metodi semplici.</span><span class="sxs-lookup"><span data-stu-id="bafba-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="bafba-106">Le linee guida seguenti consentono di decidere quando e come usare l'overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="bafba-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>  
  
 <span data-ttu-id="bafba-107">**X AVOID** definizione overload degli operatori, tranne nei tipi che dovrebbero risultare come tipi primitivi (predefiniti).</span><span class="sxs-lookup"><span data-stu-id="bafba-107">**X AVOID** defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>  
  
 <span data-ttu-id="bafba-108">**✓ CONSIDER** definizione overload degli operatori in un tipo che deve essere, ad esempio un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="bafba-108">**✓ CONSIDER** defining operator overloads in a type that should feel like a primitive type.</span></span>  
  
 <span data-ttu-id="bafba-109">Ad esempio, <xref:System.String?displayProperty=nameWithType> ha `operator==` e `operator!=` definito.</span><span class="sxs-lookup"><span data-stu-id="bafba-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>  
  
 <span data-ttu-id="bafba-110">**✓ DO** definire gli overload degli operatori in strutture che rappresentano numeri (ad esempio <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="bafba-110">**✓ DO** define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="bafba-111">**X DO NOT** essere mentre quando si definiscono gli overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="bafba-111">**X DO NOT** be cute when defining operator overloads.</span></span>  
  
 <span data-ttu-id="bafba-112">L'overload degli operatori è utile nei casi in cui è immediatamente ovvio quale sarà il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="bafba-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="bafba-113">Ad esempio, è opportuno essere in grado di sottrarre uno <xref:System.DateTime> da un altro `DateTime` e ottenere un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="bafba-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="bafba-114">Non è tuttavia appropriata per utilizzare l'operatore union logico per le query di unione due database o usare l'operatore di spostamento per scrivere in un flusso.</span><span class="sxs-lookup"><span data-stu-id="bafba-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>  
  
 <span data-ttu-id="bafba-115">**X DO NOT** forniscono gli overload di operatori, a meno che almeno uno degli operandi è di tipo che definisce l'overload.</span><span class="sxs-lookup"><span data-stu-id="bafba-115">**X DO NOT** provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>  
  
 <span data-ttu-id="bafba-116">**✓ DO** overload degli operatori in modo simmetrico.</span><span class="sxs-lookup"><span data-stu-id="bafba-116">**✓ DO** overload operators in a symmetric fashion.</span></span>  
  
 <span data-ttu-id="bafba-117">Ad esempio, se si esegue l'overload di `operator==`, è anche necessario eseguire l'overload di `operator!=`.</span><span class="sxs-lookup"><span data-stu-id="bafba-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="bafba-118">In modo analogo, se si esegue l'overload di `operator<`, è anche necessario eseguire l'overload di `operator>`e così via.</span><span class="sxs-lookup"><span data-stu-id="bafba-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>  
  
 <span data-ttu-id="bafba-119">**✓ CONSIDER** fornendo i metodi con nomi descrittivi che corrispondono a ogni operatore di overload.</span><span class="sxs-lookup"><span data-stu-id="bafba-119">**✓ CONSIDER** providing methods with friendly names that correspond to each overloaded operator.</span></span>  
  
 <span data-ttu-id="bafba-120">Molti linguaggi non supportano l'overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="bafba-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="bafba-121">Per questo motivo, è consigliabile che i tipi che eseguono l'overload degli operatori includono un metodo secondario con un nome specifico di dominio appropriato che fornisce una funzionalità equivalente.</span><span class="sxs-lookup"><span data-stu-id="bafba-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>  
  
 <span data-ttu-id="bafba-122">Nella tabella seguente contiene un elenco di operatori e i nomi di metodo descrittivo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bafba-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>  
  
|<span data-ttu-id="bafba-123">Simbolo operatore c#</span><span class="sxs-lookup"><span data-stu-id="bafba-123">C# Operator Symbol</span></span>|<span data-ttu-id="bafba-124">Nome dei metadati</span><span class="sxs-lookup"><span data-stu-id="bafba-124">Metadata Name</span></span>|<span data-ttu-id="bafba-125">Nome descrittivo</span><span class="sxs-lookup"><span data-stu-id="bafba-125">Friendly Name</span></span>|  
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
  
### <a name="overloading-operator-"></a><span data-ttu-id="bafba-126">Overload dell'operatore = =</span><span class="sxs-lookup"><span data-stu-id="bafba-126">Overloading Operator ==</span></span>  
 <span data-ttu-id="bafba-127">L'overload `operator ==` è piuttosto complicata.</span><span class="sxs-lookup"><span data-stu-id="bafba-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="bafba-128">La semantica dell'operatore desidera essere compatibili con molti altri membri, ad esempio <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bafba-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="conversion-operators"></a><span data-ttu-id="bafba-129">Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="bafba-129">Conversion Operators</span></span>  
 <span data-ttu-id="bafba-130">Gli operatori di conversione sono gli operatori unari che consentono la conversione da un tipo a altro.</span><span class="sxs-lookup"><span data-stu-id="bafba-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="bafba-131">Gli operatori devono essere definiti come membri statici su operando o il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="bafba-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="bafba-132">Esistono due tipi di operatori di conversione: implicite ed esplicite.</span><span class="sxs-lookup"><span data-stu-id="bafba-132">There are two types of conversion operators: implicit and explicit.</span></span>  
  
 <span data-ttu-id="bafba-133">**X DO NOT** forniscono un operatore di conversione se tale conversione non è previsto chiaramente dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="bafba-133">**X DO NOT** provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>  
  
 <span data-ttu-id="bafba-134">**X DO NOT** definire operatori di conversione di fuori di dominio del tipo.</span><span class="sxs-lookup"><span data-stu-id="bafba-134">**X DO NOT** define conversion operators outside of a type’s domain.</span></span>  
  
 <span data-ttu-id="bafba-135">Ad esempio, <xref:System.Int32>, <xref:System.Double>, e <xref:System.Decimal> sono tutti i tipi numerici, mentre <xref:System.DateTime> non.</span><span class="sxs-lookup"><span data-stu-id="bafba-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="bafba-136">Pertanto, non vi sarà alcun operatore di conversione per convertire un `Double(long)` a un `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="bafba-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="bafba-137">In tal caso è preferibile utilizzare un costruttore.</span><span class="sxs-lookup"><span data-stu-id="bafba-137">A constructor is preferred in such a case.</span></span>  
  
 <span data-ttu-id="bafba-138">**X DO NOT** forniscono un operatore di conversione implicita, se la conversione è potenzialmente perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="bafba-138">**X DO NOT** provide an implicit conversion operator if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="bafba-139">Ad esempio, deve essere presente una conversione implicita da `Double` al `Int32` poiché `Double` dispone di una gamma più ampia rispetto a `Int32`.</span><span class="sxs-lookup"><span data-stu-id="bafba-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="bafba-140">Anche se la conversione è potenzialmente con perdita di dati, è possibile specificare un operatore di conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="bafba-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="bafba-141">**X DO NOT** generare eccezioni da cast impliciti.</span><span class="sxs-lookup"><span data-stu-id="bafba-141">**X DO NOT** throw exceptions from implicit casts.</span></span>  
  
 <span data-ttu-id="bafba-142">È molto difficile per gli utenti finali a comprendere ciò che avviene, in quanto potrebbero non essere consapevoli che una conversione ha luogo.</span><span class="sxs-lookup"><span data-stu-id="bafba-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>  
  
 <span data-ttu-id="bafba-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> se una chiamata a un operatore cast comporta una perdita di dati conversione e il contratto dell'operatore non consente conversioni perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="bafba-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>  
  
 <span data-ttu-id="bafba-144">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="bafba-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bafba-145">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="bafba-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafba-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bafba-146">See also</span></span>

- [<span data-ttu-id="bafba-147">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="bafba-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="bafba-148">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="bafba-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
