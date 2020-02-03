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
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743681"
---
# <a name="operator-overloads"></a><span data-ttu-id="d0962-102">Overload dell'operatore</span><span class="sxs-lookup"><span data-stu-id="d0962-102">Operator Overloads</span></span>
<span data-ttu-id="d0962-103">Gli overload degli operatori consentono la visualizzazione di tipi di Framework come se fossero primitive di linguaggio incorporati.</span><span class="sxs-lookup"><span data-stu-id="d0962-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>

 <span data-ttu-id="d0962-104">Sebbene sia consentito e utile in alcune situazioni, gli overload degli operatori devono essere usati con cautela.</span><span class="sxs-lookup"><span data-stu-id="d0962-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="d0962-105">In molti casi l'overload degli operatori è stato abusato, ad esempio quando le finestre di progettazione del Framework hanno iniziato a usare gli operatori per le operazioni che devono essere metodi semplici.</span><span class="sxs-lookup"><span data-stu-id="d0962-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="d0962-106">Le linee guida seguenti consentono di decidere quando e come usare l'overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="d0962-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>

 <span data-ttu-id="d0962-107">❌ evitare di definire overload di operatori, ad eccezione dei tipi che dovrebbero essere simili ai tipi primitivi (incorporati).</span><span class="sxs-lookup"><span data-stu-id="d0962-107">❌ AVOID defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>

 <span data-ttu-id="d0962-108">✔️ CONSIDERARE la definizione di overload degli operatori in un tipo che dovrebbe essere simile a un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="d0962-108">✔️ CONSIDER defining operator overloads in a type that should feel like a primitive type.</span></span>

 <span data-ttu-id="d0962-109">Ad esempio, <xref:System.String?displayProperty=nameWithType> dispone di `operator==` e `operator!=` definito.</span><span class="sxs-lookup"><span data-stu-id="d0962-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>

 <span data-ttu-id="d0962-110">✔️ definiscono gli overload degli operatori negli struct che rappresentano i numeri, ad esempio <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d0962-110">✔️ DO define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="d0962-111">❌ non sono carinissimi quando si definiscono gli overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="d0962-111">❌ DO NOT be cute when defining operator overloads.</span></span>

 <span data-ttu-id="d0962-112">L'overload degli operatori è utile nei casi in cui è immediatamente evidente quale sarà il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d0962-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="d0962-113">È ad esempio opportuno poter sottrarre una <xref:System.DateTime> da un'altra `DateTime` e ottenere un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="d0962-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="d0962-114">Tuttavia, non è consigliabile usare l'operatore di unione logica per unire due query di database o per usare l'operatore Shift per scrivere in un flusso.</span><span class="sxs-lookup"><span data-stu-id="d0962-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>

 <span data-ttu-id="d0962-115">❌ non forniscono overload degli operatori a meno che almeno uno degli operandi sia del tipo che definisce l'overload.</span><span class="sxs-lookup"><span data-stu-id="d0962-115">❌ DO NOT provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>

 <span data-ttu-id="d0962-116">✔️ gli operatori di overload in modo simmetrico.</span><span class="sxs-lookup"><span data-stu-id="d0962-116">✔️ DO overload operators in a symmetric fashion.</span></span>

 <span data-ttu-id="d0962-117">Se, ad esempio, si esegue l'overload del `operator==`, è necessario eseguire l'overload anche del `operator!=`.</span><span class="sxs-lookup"><span data-stu-id="d0962-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="d0962-118">Analogamente, se si esegue l'overload del `operator<`, è necessario eseguire l'overload anche della `operator>`e così via.</span><span class="sxs-lookup"><span data-stu-id="d0962-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>

 <span data-ttu-id="d0962-119">✔️ considerare la possibilità di fornire metodi con nomi descrittivi che corrispondono a ogni operatore di overload.</span><span class="sxs-lookup"><span data-stu-id="d0962-119">✔️ CONSIDER providing methods with friendly names that correspond to each overloaded operator.</span></span>

 <span data-ttu-id="d0962-120">Molti linguaggi non supportano l'overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="d0962-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="d0962-121">Per questo motivo, è consigliabile che i tipi che gli operatori di overload includano un metodo secondario con un nome appropriato specifico del dominio che fornisca funzionalità equivalenti.</span><span class="sxs-lookup"><span data-stu-id="d0962-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>

 <span data-ttu-id="d0962-122">La tabella seguente contiene un elenco di operatori e i nomi di metodo descrittivi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="d0962-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>

|<span data-ttu-id="d0962-123">C#Simbolo dell'operatore</span><span class="sxs-lookup"><span data-stu-id="d0962-123">C# Operator Symbol</span></span>|<span data-ttu-id="d0962-124">Nome dei metadati</span><span class="sxs-lookup"><span data-stu-id="d0962-124">Metadata Name</span></span>|<span data-ttu-id="d0962-125">Soprannome</span><span class="sxs-lookup"><span data-stu-id="d0962-125">Friendly Name</span></span>|
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

### <a name="overloading-operator-"></a><span data-ttu-id="d0962-126">Overload Operator = =</span><span class="sxs-lookup"><span data-stu-id="d0962-126">Overloading Operator ==</span></span>
 <span data-ttu-id="d0962-127">L'overload di `operator ==` è piuttosto complesso.</span><span class="sxs-lookup"><span data-stu-id="d0962-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="d0962-128">La semantica dell'operatore deve essere compatibile con diversi altri membri, ad esempio <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d0962-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>

### <a name="conversion-operators"></a><span data-ttu-id="d0962-129">Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="d0962-129">Conversion Operators</span></span>
 <span data-ttu-id="d0962-130">Gli operatori di conversione sono operatori unari che consentono la conversione da un tipo a un altro.</span><span class="sxs-lookup"><span data-stu-id="d0962-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="d0962-131">Gli operatori devono essere definiti come membri statici nell'operando o nel tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="d0962-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="d0962-132">Esistono due tipi di operatori di conversione: implicito ed esplicito.</span><span class="sxs-lookup"><span data-stu-id="d0962-132">There are two types of conversion operators: implicit and explicit.</span></span>

 <span data-ttu-id="d0962-133">❌ non forniscono un operatore di conversione se tale conversione non è chiaramente prevista dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="d0962-133">❌ DO NOT provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>

 <span data-ttu-id="d0962-134">❌ non definiscono operatori di conversione al di fuori del dominio di un tipo.</span><span class="sxs-lookup"><span data-stu-id="d0962-134">❌ DO NOT define conversion operators outside of a type’s domain.</span></span>

 <span data-ttu-id="d0962-135">Ad esempio, <xref:System.Int32>, <xref:System.Double>e <xref:System.Decimal> sono tutti tipi numerici, mentre <xref:System.DateTime> non lo è.</span><span class="sxs-lookup"><span data-stu-id="d0962-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="d0962-136">Pertanto, non deve essere presente alcun operatore di conversione per convertire un `Double(long)` in un `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="d0962-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="d0962-137">In tal caso, è preferibile un costruttore.</span><span class="sxs-lookup"><span data-stu-id="d0962-137">A constructor is preferred in such a case.</span></span>

 <span data-ttu-id="d0962-138">❌ non forniscono un operatore di conversione implicito se la conversione è potenzialmente dannosa.</span><span class="sxs-lookup"><span data-stu-id="d0962-138">❌ DO NOT provide an implicit conversion operator if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="d0962-139">Ad esempio, non deve essere presente una conversione implicita da `Double` a `Int32` perché `Double` ha un intervallo più ampio rispetto a `Int32`.</span><span class="sxs-lookup"><span data-stu-id="d0962-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="d0962-140">È possibile fornire un operatore di conversione esplicito anche se la conversione è potenzialmente perdita di perdite.</span><span class="sxs-lookup"><span data-stu-id="d0962-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="d0962-141">❌ non generano eccezioni da cast impliciti.</span><span class="sxs-lookup"><span data-stu-id="d0962-141">❌ DO NOT throw exceptions from implicit casts.</span></span>

 <span data-ttu-id="d0962-142">È molto difficile per gli utenti finali comprendere ciò che accade, perché potrebbero non essere consapevoli del fatto che è stata eseguita una conversione.</span><span class="sxs-lookup"><span data-stu-id="d0962-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>

 <span data-ttu-id="d0962-143">✔️ generano <xref:System.InvalidCastException?displayProperty=nameWithType> se una chiamata a un operatore cast comporta una conversione con perdita di dati e il contratto dell'operatore non consente le conversioni con perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="d0962-143">✔️ DO throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>

 <span data-ttu-id="d0962-144">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="d0962-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d0962-145">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d0962-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d0962-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0962-146">See also</span></span>

- [<span data-ttu-id="d0962-147">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="d0962-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="d0962-148">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="d0962-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
