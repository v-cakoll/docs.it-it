---
title: Overload degli operatori
description: Informazioni su come eseguire l'overload di operatori aritmetici in una classe o in un tipo di F#record e a livello globale in.
ms.date: 05/16/2016
ms.openlocfilehash: c656c1c47938e62386c8f063cf9a6caaaf69d0fe
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627396"
---
# <a name="operator-overloading"></a><span data-ttu-id="e6119-103">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="e6119-103">Operator Overloading</span></span>

<span data-ttu-id="e6119-104">In questo argomento viene descritto come eseguire l'overload di operatori aritmetici in una classe o in un tipo di record e a livello globale.</span><span class="sxs-lookup"><span data-stu-id="e6119-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6119-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6119-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="e6119-106">Note</span><span class="sxs-lookup"><span data-stu-id="e6119-106">Remarks</span></span>

<span data-ttu-id="e6119-107">Nella sintassi precedente il *simbolo operator* è uno tra `+`, `*` `-`,, `/`, `=`e così via.</span><span class="sxs-lookup"><span data-stu-id="e6119-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="e6119-108">*Parameter-list* specifica gli operandi nell'ordine in cui sono visualizzati nella sintassi consueta per l'operatore.</span><span class="sxs-lookup"><span data-stu-id="e6119-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="e6119-109">Il *corpo del metodo* costruisce il valore risultante.</span><span class="sxs-lookup"><span data-stu-id="e6119-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="e6119-110">Gli overload degli operatori per gli operatori devono essere statici.</span><span class="sxs-lookup"><span data-stu-id="e6119-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="e6119-111">Gli overload degli operatori per gli operatori unari, ad `+` esempio `-`e, devono usare una tilde`~`() nel *simbolo operator* per indicare che l'operatore è un operatore unario e non un operatore binario, come illustrato di seguito. Dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="e6119-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="e6119-112">Nel codice seguente viene illustrata una classe di vettori con solo due operatori, uno per meno unario e uno per la moltiplicazione per un valore scalare.</span><span class="sxs-lookup"><span data-stu-id="e6119-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="e6119-113">Nell'esempio sono necessari due overload per la moltiplicazione scalare perché l'operatore deve funzionare indipendentemente dall'ordine in cui vengono visualizzati il vettore e il valore scalare.</span><span class="sxs-lookup"><span data-stu-id="e6119-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="e6119-114">Creazione di nuovi operatori</span><span class="sxs-lookup"><span data-stu-id="e6119-114">Creating New Operators</span></span>

<span data-ttu-id="e6119-115">È possibile eseguire l'overload di tutti gli operatori standard, ma è anche possibile creare nuovi operatori dalle sequenze di determinati caratteri.</span><span class="sxs-lookup"><span data-stu-id="e6119-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="e6119-116">I caratteri di operatore `!`consentiti `*`sono `+` `&`, `%`, `.`, `/`,, `-`,,, `<`, ,`=`, `>` `?` ,`@`, ,`^` e`~`. `|`</span><span class="sxs-lookup"><span data-stu-id="e6119-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="e6119-117">Il `~` carattere ha il significato speciale di rendere unaria un operatore e non fa parte della sequenza di caratteri dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="e6119-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="e6119-118">Non tutti gli operatori possono essere resi unari.</span><span class="sxs-lookup"><span data-stu-id="e6119-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="e6119-119">A seconda della sequenza di caratteri esatta utilizzata, l'operatore avrà una certa precedenza e associatività.</span><span class="sxs-lookup"><span data-stu-id="e6119-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="e6119-120">L'associatività può essere da sinistra a destra o da destra a sinistra e viene usata ogni volta che gli operatori con lo stesso livello di precedenza vengono visualizzati in sequenza senza parentesi.</span><span class="sxs-lookup"><span data-stu-id="e6119-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="e6119-121">Il carattere `.` dell'operatore non influisce sulla precedenza, quindi, ad esempio, se si desidera definire una versione personalizzata della moltiplicazione con la stessa precedenza e associatività della moltiplicazione ordinaria, è possibile creare operatori come `.*`.</span><span class="sxs-lookup"><span data-stu-id="e6119-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="e6119-122">Solo gli operatori `?` e `?<-` possono iniziare con `?`.</span><span class="sxs-lookup"><span data-stu-id="e6119-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="e6119-123">Una tabella che mostra la precedenza di tutti gli operatori F# in si trova in [riferimento a simboli e operatori](./symbol-and-operator-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="e6119-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](./symbol-and-operator-reference/index.md).</span></span>

## <a name="overloaded-operator-names"></a><span data-ttu-id="e6119-124">Nomi degli operatori di overload</span><span class="sxs-lookup"><span data-stu-id="e6119-124">Overloaded Operator Names</span></span>

<span data-ttu-id="e6119-125">Quando il F# compilatore compila un'espressione di operatore, genera un metodo con un nome generato dal compilatore per l'operatore.</span><span class="sxs-lookup"><span data-stu-id="e6119-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="e6119-126">Si tratta del nome che viene visualizzato nel linguaggio MSIL (Microsoft Intermediate Language) per il metodo e anche in Reflection e IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e6119-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="e6119-127">Non è in genere necessario usare questi nomi nel F# codice.</span><span class="sxs-lookup"><span data-stu-id="e6119-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="e6119-128">Nella tabella seguente vengono illustrati gli operatori standard e i corrispondenti nomi generati.</span><span class="sxs-lookup"><span data-stu-id="e6119-128">The following table shows the standard operators and their corresponding generated names.</span></span>

|<span data-ttu-id="e6119-129">Operator</span><span class="sxs-lookup"><span data-stu-id="e6119-129">Operator</span></span>|<span data-ttu-id="e6119-130">Nome generato</span><span class="sxs-lookup"><span data-stu-id="e6119-130">Generated name</span></span>|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|

<span data-ttu-id="e6119-131">Altre combinazioni di caratteri operatore che non sono elencate di seguito possono essere usate come operatori e hanno nomi costituiti dalla concatenazione di nomi per i singoli caratteri della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e6119-131">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="e6119-132">Ad esempio, +!</span><span class="sxs-lookup"><span data-stu-id="e6119-132">For example, +!</span></span> <span data-ttu-id="e6119-133">diventa `op_PlusBang`.</span><span class="sxs-lookup"><span data-stu-id="e6119-133">becomes `op_PlusBang`.</span></span>

|<span data-ttu-id="e6119-134">Carattere operatore</span><span class="sxs-lookup"><span data-stu-id="e6119-134">Operator character</span></span>|<span data-ttu-id="e6119-135">Name</span><span class="sxs-lookup"><span data-stu-id="e6119-135">Name</span></span>|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="e6119-136">Operatori prefix e infissi</span><span class="sxs-lookup"><span data-stu-id="e6119-136">Prefix and Infix Operators</span></span>

<span data-ttu-id="e6119-137">Si prevede che gli operatori di *prefisso* siano posizionati davanti a un operando o a operandi, molto simile a una funzione.</span><span class="sxs-lookup"><span data-stu-id="e6119-137">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="e6119-138">Si prevede che gli operatori infissi siano posizionati tra i due operandi.</span><span class="sxs-lookup"><span data-stu-id="e6119-138">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="e6119-139">Solo determinati operatori possono essere utilizzati come operatori di prefisso.</span><span class="sxs-lookup"><span data-stu-id="e6119-139">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="e6119-140">Alcuni operatori sono sempre operatori di prefisso, altri possono essere infissi o prefissi e i restanti sono sempre operatori infissi.</span><span class="sxs-lookup"><span data-stu-id="e6119-140">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="e6119-141">Gli operatori che iniziano `!`con, `!=`ad eccezione di e `~`l'operatore, o sequenze ripetute di, sono sempre operatori di`~`prefisso.</span><span class="sxs-lookup"><span data-stu-id="e6119-141">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="e6119-142">Gli operatori `+` `-` ,`&` ,,`%%` ,,, e possono essere operatori di prefisso o infissi. `+.` `-.` `&&` `%`</span><span class="sxs-lookup"><span data-stu-id="e6119-142">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="e6119-143">È possibile distinguere la versione del prefisso di questi operatori dalla versione infissi aggiungendo `~` un oggetto all'inizio di un operatore di prefisso quando viene definito.</span><span class="sxs-lookup"><span data-stu-id="e6119-143">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="e6119-144">L' `~` oggetto non viene utilizzato quando si utilizza l'operatore, solo quando è definito.</span><span class="sxs-lookup"><span data-stu-id="e6119-144">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="e6119-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6119-145">Example</span></span>

<span data-ttu-id="e6119-146">Il codice seguente illustra l'uso dell'overload degli operatori per implementare un tipo di frazione.</span><span class="sxs-lookup"><span data-stu-id="e6119-146">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="e6119-147">Una frazione viene rappresentata da un numeratore e da un denominatore.</span><span class="sxs-lookup"><span data-stu-id="e6119-147">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="e6119-148">La funzione `hcf` viene usata per determinare il fattore comune più elevato, che viene usato per ridurre le frazioni.</span><span class="sxs-lookup"><span data-stu-id="e6119-148">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="e6119-149">**Output:**</span><span class="sxs-lookup"><span data-stu-id="e6119-149">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="e6119-150">Operatori a livello globale</span><span class="sxs-lookup"><span data-stu-id="e6119-150">Operators at the Global Level</span></span>

<span data-ttu-id="e6119-151">È anche possibile definire gli operatori a livello globale.</span><span class="sxs-lookup"><span data-stu-id="e6119-151">You can also define operators at the global level.</span></span> <span data-ttu-id="e6119-152">Il codice seguente definisce un operatore `+?`.</span><span class="sxs-lookup"><span data-stu-id="e6119-152">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="e6119-153">L'output del codice precedente è `12`.</span><span class="sxs-lookup"><span data-stu-id="e6119-153">The output of the above code is `12`.</span></span>

<span data-ttu-id="e6119-154">È possibile ridefinire gli operatori aritmetici regolari in questo modo perché le regole F# di ambito per stabiliscono che gli operatori appena definiti hanno la precedenza sugli operatori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e6119-154">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="e6119-155">La parola `inline` chiave viene spesso usata con gli operatori globali, che sono spesso piccole funzioni più integrate nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="e6119-155">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="e6119-156">La creazione di funzioni operatore inline consente inoltre di utilizzare parametri di tipo risolti staticamente per produrre codice generico risolto in modo statico.</span><span class="sxs-lookup"><span data-stu-id="e6119-156">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="e6119-157">Per altre informazioni, vedere [funzioni inline](./functions/inline-functions.md) e [parametri di tipo risolti staticamente](./generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="e6119-157">For more information, see [Inline Functions](./functions/inline-functions.md) and [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6119-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6119-158">See also</span></span>

- [<span data-ttu-id="e6119-159">Membri</span><span class="sxs-lookup"><span data-stu-id="e6119-159">Members</span></span>](./members/index.md)
