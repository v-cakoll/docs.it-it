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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400568"
---
# <a name="operator-overloads"></a><span data-ttu-id="81b86-102">Overload dell'operatore</span><span class="sxs-lookup"><span data-stu-id="81b86-102">Operator Overloads</span></span>
<span data-ttu-id="81b86-103">Gli overload degli operatori consentono ai tipi di framework di apparire come se fossero primitive di linguaggio incorporate.</span><span class="sxs-lookup"><span data-stu-id="81b86-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>

 <span data-ttu-id="81b86-104">Sebbene siano consentiti e utili in alcune situazioni, gli overload dell'operatore devono essere usati con cautela.</span><span class="sxs-lookup"><span data-stu-id="81b86-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="81b86-105">Esistono molti casi in cui l'overload degli operatori è stato abusato, ad esempio quando i progettisti del framework hanno iniziato a utilizzare gli operatori per le operazioni che devono essere metodi semplici.</span><span class="sxs-lookup"><span data-stu-id="81b86-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="81b86-106">Le linee guida seguenti dovrebbero aiutare a decidere quando e come usare l'overload dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="81b86-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>

 <span data-ttu-id="81b86-107">❌AVOID che definisce gli overload degli operatori, ad eccezione dei tipi che dovrebbero avere l'aspetto di tipi primitivi (incorporati).</span><span class="sxs-lookup"><span data-stu-id="81b86-107">❌ AVOID defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>

 <span data-ttu-id="81b86-108">✔️ CONSIDER che definisce gli overload dell'operatore in un tipo che dovrebbe sembrare un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="81b86-108">✔️ CONSIDER defining operator overloads in a type that should feel like a primitive type.</span></span>

 <span data-ttu-id="81b86-109">Ad <xref:System.String?displayProperty=nameWithType> esempio, `operator==` `operator!=` ha e definito.</span><span class="sxs-lookup"><span data-stu-id="81b86-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>

 <span data-ttu-id="81b86-110">✔️ dedefinire gli overload degli operatori in <xref:System.Decimal?displayProperty=nameWithType>struct che rappresentano numeri (ad esempio ).</span><span class="sxs-lookup"><span data-stu-id="81b86-110">✔️ DO define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="81b86-111">❌NON essere carino quando si definiscono gli overload dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="81b86-111">❌ DO NOT be cute when defining operator overloads.</span></span>

 <span data-ttu-id="81b86-112">L'overload dell'operatore è utile nei casi in cui è immediatamente evidente quale sarà il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="81b86-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="81b86-113">Ad esempio, ha senso essere in <xref:System.DateTime> grado `DateTime` di <xref:System.TimeSpan>sottrarre uno dall'altro e ottenere un .</span><span class="sxs-lookup"><span data-stu-id="81b86-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="81b86-114">Tuttavia, non è appropriato utilizzare l'operatore di unione logica per unionare due query di database o utilizzare l'operatore shift per scrivere in un flusso.</span><span class="sxs-lookup"><span data-stu-id="81b86-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>

 <span data-ttu-id="81b86-115">❌DO NOT fornire overload dell'operatore a meno che almeno uno degli operandi sia del tipo che definisce l'overload.</span><span class="sxs-lookup"><span data-stu-id="81b86-115">❌ DO NOT provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>

 <span data-ttu-id="81b86-116">✔️ gli operatori DO eseguono l'overload degli operatori in modo simmetrico.</span><span class="sxs-lookup"><span data-stu-id="81b86-116">✔️ DO overload operators in a symmetric fashion.</span></span>

 <span data-ttu-id="81b86-117">Ad esempio, se `operator==`si esegue l'overload di , è necessario eseguire anche l'overload di `operator!=`.</span><span class="sxs-lookup"><span data-stu-id="81b86-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="81b86-118">Analogamente, se `operator<`si esegue l'overload di , è necessario eseguire anche l'overload di `operator>`, e così via.</span><span class="sxs-lookup"><span data-stu-id="81b86-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>

 <span data-ttu-id="81b86-119">✔️ CONSIDER che forniscono metodi con nomi descrittivi che corrispondono a ogni operatore di overload.</span><span class="sxs-lookup"><span data-stu-id="81b86-119">✔️ CONSIDER providing methods with friendly names that correspond to each overloaded operator.</span></span>

 <span data-ttu-id="81b86-120">Molti linguaggi non supportano l'overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="81b86-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="81b86-121">Per questo motivo, è consigliabile che i tipi che eseguono l'overload degli operatori includano un metodo secondario con un nome specifico di dominio appropriato che fornisce funzionalità equivalenti.</span><span class="sxs-lookup"><span data-stu-id="81b86-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>

 <span data-ttu-id="81b86-122">La tabella seguente contiene un elenco di operatori e i nomi dei metodi descrittivi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="81b86-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>

|<span data-ttu-id="81b86-123">Simbolo dell'operatore di C</span><span class="sxs-lookup"><span data-stu-id="81b86-123">C# Operator Symbol</span></span>|<span data-ttu-id="81b86-124">Nome metadati</span><span class="sxs-lookup"><span data-stu-id="81b86-124">Metadata Name</span></span>|<span data-ttu-id="81b86-125">Nome descrittivo</span><span class="sxs-lookup"><span data-stu-id="81b86-125">Friendly Name</span></span>|
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

### <a name="overloading-operator-"></a><span data-ttu-id="81b86-126">Operatore di Overloading</span><span class="sxs-lookup"><span data-stu-id="81b86-126">Overloading Operator ==</span></span>
 <span data-ttu-id="81b86-127">Sovraccaricare `operator ==` è piuttosto complicato.</span><span class="sxs-lookup"><span data-stu-id="81b86-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="81b86-128">La semantica dell'operatore deve essere compatibile con <xref:System.Object.Equals%2A?displayProperty=nameWithType>diversi altri membri, ad esempio .</span><span class="sxs-lookup"><span data-stu-id="81b86-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>

### <a name="conversion-operators"></a><span data-ttu-id="81b86-129">Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="81b86-129">Conversion Operators</span></span>
 <span data-ttu-id="81b86-130">Gli operatori di conversione sono operatori unari che consentono la conversione da un tipo a un altro.</span><span class="sxs-lookup"><span data-stu-id="81b86-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="81b86-131">Gli operatori devono essere definiti come membri statici nell'operando o nel tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="81b86-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="81b86-132">Esistono due tipi di operatori di conversione: implicito ed esplicito.</span><span class="sxs-lookup"><span data-stu-id="81b86-132">There are two types of conversion operators: implicit and explicit.</span></span>

 <span data-ttu-id="81b86-133">❌NON fornire un operatore di conversione se tale conversione non è chiaramente prevista dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="81b86-133">❌ DO NOT provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>

 <span data-ttu-id="81b86-134">❌NON definire operatori di conversione all'esterno del dominio di un tipo.</span><span class="sxs-lookup"><span data-stu-id="81b86-134">❌ DO NOT define conversion operators outside of a type’s domain.</span></span>

 <span data-ttu-id="81b86-135">Ad <xref:System.Int32>esempio, <xref:System.Double>, <xref:System.Decimal> e sono tutti <xref:System.DateTime> tipi numerici, mentre non lo è.</span><span class="sxs-lookup"><span data-stu-id="81b86-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="81b86-136">Pertanto, non deve essere presente `Double(long)` alcun `DateTime`operatore di conversione per convertire un oggetto in un oggetto .</span><span class="sxs-lookup"><span data-stu-id="81b86-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="81b86-137">In tal caso, è preferibile utilizzare un costruttore.</span><span class="sxs-lookup"><span data-stu-id="81b86-137">A constructor is preferred in such a case.</span></span>

 <span data-ttu-id="81b86-138">❌NON fornire un operatore di conversione implicito se la conversione è potenzialmente lossy.</span><span class="sxs-lookup"><span data-stu-id="81b86-138">❌ DO NOT provide an implicit conversion operator if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="81b86-139">Ad esempio, non deve essere `Double` presente `Int32` `Double` una conversione `Int32`implicita da a perché ha un intervallo più ampio di .</span><span class="sxs-lookup"><span data-stu-id="81b86-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="81b86-140">Un operatore di conversione esplicito può essere fornito anche se la conversione è potenzialmente lossy.</span><span class="sxs-lookup"><span data-stu-id="81b86-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="81b86-141">❌DO NOT generare eccezioni da cast impliciti.</span><span class="sxs-lookup"><span data-stu-id="81b86-141">❌ DO NOT throw exceptions from implicit casts.</span></span>

 <span data-ttu-id="81b86-142">È molto difficile per gli utenti finali capire cosa sta succedendo, perché potrebbero non essere consapevoli che è in corso una conversione.</span><span class="sxs-lookup"><span data-stu-id="81b86-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>

 <span data-ttu-id="81b86-143">✔️ DO <xref:System.InvalidCastException?displayProperty=nameWithType> throw se una chiamata a un operatore cast genera una conversione lossy e il contratto dell'operatore non consente conversioni con perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="81b86-143">✔️ DO throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>

 <span data-ttu-id="81b86-144">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="81b86-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="81b86-145">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="81b86-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="81b86-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81b86-146">See also</span></span>

- [<span data-ttu-id="81b86-147">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="81b86-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="81b86-148">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="81b86-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
