---
title: Overload degli operatori (F#)
description: Informazioni su come eseguire l'overload di operatori aritmetici in una classe o un tipo di record e a livello globale in F#.
ms.date: 05/16/2016
ms.openlocfilehash: 6232ebf215289e6a22b9d77fbd5fa67b82460486
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "44087299"
---
# <a name="operator-overloading"></a><span data-ttu-id="9ce2b-103">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="9ce2b-103">Operator Overloading</span></span>

<span data-ttu-id="9ce2b-104">In questo argomento viene descritto come eseguire l'overload di operatori aritmetici in una classe o un tipo di record e a livello globale.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>

## <a name="syntax"></a><span data-ttu-id="9ce2b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ce2b-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="9ce2b-106">Note</span><span class="sxs-lookup"><span data-stu-id="9ce2b-106">Remarks</span></span>

<span data-ttu-id="9ce2b-107">Nella sintassi precedente, il *operatore-symbol* è uno dei `+`, `-`, `*`, `/`, `=`e così via.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="9ce2b-108">Il *elenco di parametri* specifica gli operandi in ordine vengono visualizzati nella sintassi normale per tale operatore.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="9ce2b-109">Il *corpo del metodo* costruisca il valore risulta.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="9ce2b-110">Overload degli operatori per gli operatori devono essere statici.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="9ce2b-111">Operatore di overload per gli operatori unari, ad esempio `+` e `-`, deve usare un carattere tilde (`~`) nel *simbolo dell'operatore* per indicare che l'operatore è un operatore unario e non un operatore binario, come illustrato di dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="9ce2b-112">Nel codice seguente viene illustrata una classe di vettori con solo due operatori, uno per meno unario e uno per la moltiplicazione per un valore scalare.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="9ce2b-113">Nell'esempio, due overload per la moltiplicazione scalare sono necessarie perché l'operatore deve funzionare indipendentemente dall'ordine in cui vengono visualizzati il vettore e il valore scalare.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="9ce2b-114">Creazione di nuovi operatori</span><span class="sxs-lookup"><span data-stu-id="9ce2b-114">Creating New Operators</span></span>

<span data-ttu-id="9ce2b-115">È possibile eseguire l'overload di tutti gli operatori standard, ma è anche possibile creare nuovi operatori all'esterno di sequenze di caratteri specifici.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="9ce2b-116">Caratteri consentiti sono `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, e `~`.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="9ce2b-117">Il `~` carattere ha un significato speciale di creazione di un operatore unario e non fa parte della sequenza di caratteri dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="9ce2b-118">Non tutti gli operatori possono essere resi unario.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="9ce2b-119">A seconda la sequenza di caratteri esatta che è usare l'operatore avrà un determinato la precedenza e associatività degli operatori.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="9ce2b-120">Può essere da sinistra verso destra o da destra a sinistra e viene usato ogni volta che gli operatori allo stesso livello di precedenza visualizzati in sequenza senza parentesi associatività degli operatori.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="9ce2b-121">Il carattere di operatore `.` non influisce sulla precedenza, in modo che, ad esempio, se si desidera definire la propria versione di moltiplicazione che ha la stessa precedenza e associatività degli operatori di moltiplicazione ordinaria, è possibile creare operatori quali `.*`.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="9ce2b-122">Solo gli operatori `?` e `?<-` può iniziare con `?`.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="9ce2b-123">È disponibili una tabella che mostra la precedenza di tutti gli operatori in F# [riferimenti per simboli e operatore](symbol-and-operator-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="9ce2b-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](symbol-and-operator-reference/index.md).</span></span>

## <a name="overloaded-operator-names"></a><span data-ttu-id="9ce2b-124">Nomi degli operatori di overload</span><span class="sxs-lookup"><span data-stu-id="9ce2b-124">Overloaded Operator Names</span></span>

<span data-ttu-id="9ce2b-125">Quando il compilatore F# compila un'espressione di operatore, viene generato un metodo che presenta un nome generato dal compilatore per tale operatore.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="9ce2b-126">Si tratta del nome che viene visualizzato il codice Microsoft intermediate language (MSIL) per il metodo, nonché reflection e IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="9ce2b-127">In genere, non è necessario usare questi nomi nel codice F#.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="9ce2b-128">La tabella seguente illustra gli operatori standard e i relativi nomi generati.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-128">The following table shows the standard operators and their corresponding generated names.</span></span>

|<span data-ttu-id="9ce2b-129">Operatore</span><span class="sxs-lookup"><span data-stu-id="9ce2b-129">Operator</span></span>|<span data-ttu-id="9ce2b-130">Nome generato</span><span class="sxs-lookup"><span data-stu-id="9ce2b-130">Generated name</span></span>|
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

<span data-ttu-id="9ce2b-131">Altre combinazioni di caratteri dell'operatore che non sono elencati di seguito possono essere utilizzati come operatori e hanno nomi composti da concatenando i nomi per i singoli caratteri della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-131">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="9ce2b-132">Ad esempio +!</span><span class="sxs-lookup"><span data-stu-id="9ce2b-132">For example, +!</span></span> <span data-ttu-id="9ce2b-133">diventa `op_PlusBang`.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-133">becomes `op_PlusBang`.</span></span>

|<span data-ttu-id="9ce2b-134">Carattere dell'operatore</span><span class="sxs-lookup"><span data-stu-id="9ce2b-134">Operator character</span></span>|<span data-ttu-id="9ce2b-135">nome</span><span class="sxs-lookup"><span data-stu-id="9ce2b-135">Name</span></span>|
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

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="9ce2b-136">Prefisso e gli operatori infissi</span><span class="sxs-lookup"><span data-stu-id="9ce2b-136">Prefix and Infix Operators</span></span>

<span data-ttu-id="9ce2b-137">*Prefisso* gli operatori devono essere inseriti davanti a uno o più operandi, analogamente a una funzione.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-137">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="9ce2b-138">*Infisso* gli operatori devono essere racchiuse tra i due operandi.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-138">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="9ce2b-139">Solo determinati operatori possono essere utilizzati come operatori di prefisso.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-139">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="9ce2b-140">Alcuni operatori sono sempre gli operatori prefisso, altri possono essere infissi o il prefisso e il resto è sempre operatori infisso.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-140">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="9ce2b-141">Gli operatori che iniziano con `!`, tranne `!=`e l'operatore `~`, o ripetuti sequenze di`~`, sono sempre gli operatori prefisso.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-141">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="9ce2b-142">Gli operatori `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, e `%%` può essere operatori prefisso o operatori infissi.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-142">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="9ce2b-143">Si distingue la versione di questi operatori prefisso dalla versione di infissi aggiungendo un `~` all'inizio di un operatore prefisso quando viene definita.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-143">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="9ce2b-144">Il `~` non viene usato quando si usa l'operatore, solo quando è definito.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-144">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="9ce2b-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ce2b-145">Example</span></span>

<span data-ttu-id="9ce2b-146">Il codice seguente viene illustrato l'utilizzo dell'operatore di overload per implementare un tipo fraction.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-146">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="9ce2b-147">Una frazione è rappresentata da un numeratore e del denominatore.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-147">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="9ce2b-148">La funzione `hcf` viene usato per determinare il fattore comune più elevato, che consente di ridurre le frazioni.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-148">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="9ce2b-149">**Output:**</span><span class="sxs-lookup"><span data-stu-id="9ce2b-149">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="9ce2b-150">Operatori a livello globale</span><span class="sxs-lookup"><span data-stu-id="9ce2b-150">Operators at the Global Level</span></span>

<span data-ttu-id="9ce2b-151">È anche possibile definire operatori a livello globale.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-151">You can also define operators at the global level.</span></span> <span data-ttu-id="9ce2b-152">Il codice seguente definisce un operatore `+?`.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-152">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="9ce2b-153">L'output del codice sopra riportato è `12`.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-153">The output of the above code is `12`.</span></span>

<span data-ttu-id="9ce2b-154">È possibile ridefinire gli operatori aritmetici regolare in questo modo perché definiscono le regole di ambito per F# che appena definiti gli operatori hanno la precedenza sugli operatori incorporati.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-154">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="9ce2b-155">La parola chiave `inline` viene spesso usato con gli operatori globali, che spesso sono piccole funzioni che si integrano meglio nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-155">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="9ce2b-156">Making operatore funzioni inline anche consente loro di lavorare con i parametri di tipo risolti staticamente per generare codice generico risolto staticamente.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-156">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="9ce2b-157">Per altre informazioni, vedere [funzioni Inline](functions/inline-functions.md) e [staticamente parametri di tipo risolti](generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9ce2b-157">For more information, see [Inline Functions](functions/inline-functions.md) and [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9ce2b-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ce2b-158">See also</span></span>

- [<span data-ttu-id="9ce2b-159">Membri</span><span class="sxs-lookup"><span data-stu-id="9ce2b-159">Members</span></span>](members/index.md)
