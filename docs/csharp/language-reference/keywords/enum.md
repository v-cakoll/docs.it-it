---
title: enum (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- enum
- enum_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
caps.latest.revision: 36
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cf12724ec9e450a2bc237db614f235d7f03a4a7e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="enum-c-reference"></a><span data-ttu-id="48e02-102">enum (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="48e02-102">enum (C# Reference)</span></span>
<span data-ttu-id="48e02-103">La parola chiave `enum` viene usata per dichiarare un'enumerazione, un tipo distinto costituito da un set di costanti denominate definite elenco degli enumeratori.</span><span class="sxs-lookup"><span data-stu-id="48e02-103">The `enum` keyword is used to declare an enumeration, a distinct type that consists of a set of named constants called the enumerator list.</span></span>  
  
 <span data-ttu-id="48e02-104">In genere è preferibile definire un'enumerazione direttamente all'interno di uno spazio dei nomi in modo che tutte le classi nello spazio dei nomi possano accedervi con la stessa facilità.</span><span class="sxs-lookup"><span data-stu-id="48e02-104">Usually it is best to define an enum directly within a namespace so that all classes in the namespace can access it with equal convenience.</span></span> <span data-ttu-id="48e02-105">Tuttavia, un'enumerazione può anche essere annidata all'interno di una classe o di uno struct.</span><span class="sxs-lookup"><span data-stu-id="48e02-105">However, an enum can also be nested within a class or struct.</span></span>  
  
 <span data-ttu-id="48e02-106">Per impostazione predefinita, il primo enumeratore ha un valore 0 e il valore di ogni enumeratore successivo viene incrementato di 1.</span><span class="sxs-lookup"><span data-stu-id="48e02-106">By default, the first enumerator has the value 0, and the value of each successive enumerator is increased by 1.</span></span> <span data-ttu-id="48e02-107">Ad esempio, nell'enumerazione seguente `Sat` è `0`, `Sun` è `1`, `Mon` è `2`e così via.</span><span class="sxs-lookup"><span data-stu-id="48e02-107">For example, in the following enumeration, `Sat` is `0`, `Sun` is `1`, `Mon` is `2`, and so forth.</span></span>  
  
```  
enum Days {Sat, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="48e02-108">Gli enumeratori possono usare gli inizializzatori per sostituire i valori predefiniti, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="48e02-108">Enumerators can use initializers to override the default values, as shown in the following example.</span></span>  
  
```  
enum Days {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="48e02-109">In questa enumerazione la sequenza di elementi viene forzata a iniziare da `1` anziché da `0`.</span><span class="sxs-lookup"><span data-stu-id="48e02-109">In this enumeration, the sequence of elements is forced to start from `1` instead of `0`.</span></span> <span data-ttu-id="48e02-110">Tuttavia, si consiglia di includere una costante con valore pari a 0.</span><span class="sxs-lookup"><span data-stu-id="48e02-110">However, including a constant that has the value of 0 is recommended.</span></span> <span data-ttu-id="48e02-111">Per altre informazioni, vedere [Tipi di enumerazione](../../../csharp/programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="48e02-111">For more information, see [Enumeration Types](../../../csharp/programming-guide/enumeration-types.md).</span></span>  
  
 <span data-ttu-id="48e02-112">Ogni tipo di enumerazione ha un tipo sottostante, che può essere qualsiasi tipo integrale eccetto [char](../../../csharp/language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="48e02-112">Every enumeration type has an underlying type, which can be any integral type except [char](../../../csharp/language-reference/keywords/char.md).</span></span> <span data-ttu-id="48e02-113">Il tipo sottostante predefinito degli elementi dell'enumerazione è [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="48e02-113">The default underlying type of enumeration elements is [int](../../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="48e02-114">Per dichiarare un'enumerazione di un altro tipo integrale, ad esempio [byte](../../../csharp/language-reference/keywords/byte.md), usare i due punti dopo l'identificatore seguiti dal tipo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="48e02-114">To declare an enum of another integral type, such as [byte](../../../csharp/language-reference/keywords/byte.md), use a colon after the identifier followed by the type, as shown in the following example.</span></span>  
  
```  
enum Days : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="48e02-115">I tipi approvati per un'enumerazione sono `byte`, [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md)o [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="48e02-115">The approved types for an enum are `byte`, [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="48e02-116">A una variabile di tipo `Days` può essere assegnato qualsiasi valore compreso nell'intervallo del tipo sottostante. I valori non sono limitati alle costanti denominate.</span><span class="sxs-lookup"><span data-stu-id="48e02-116">A variable of type `Days` can be assigned any value in the range of the underlying type; the values are not limited to the named constants.</span></span>  
  
 <span data-ttu-id="48e02-117">Il valore predefinito di un `enum E` è il valore prodotto dall'espressione `(E)0`.</span><span class="sxs-lookup"><span data-stu-id="48e02-117">The default value of an `enum E` is the value produced by the expression `(E)0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48e02-118">Un enumeratore non può contenere spazi vuoti nel nome.</span><span class="sxs-lookup"><span data-stu-id="48e02-118">An enumerator cannot contain white space in its name.</span></span>  
  
 <span data-ttu-id="48e02-119">Il tipo sottostante specifica la quantità di spazio di archiviazione allocata per ogni enumeratore.</span><span class="sxs-lookup"><span data-stu-id="48e02-119">The underlying type specifies how much storage is allocated for each enumerator.</span></span> <span data-ttu-id="48e02-120">Tuttavia, è necessario un cast esplicito per eseguire la conversione da un tipo `enum` a un tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="48e02-120">However, an explicit cast is necessary to convert from `enum` type to an integral type.</span></span> <span data-ttu-id="48e02-121">Ad esempio, l'istruzione seguente assegna l'enumeratore `Sun` a una variabile di tipo [int](../../../csharp/language-reference/keywords/int.md) usando un cast per convertire `enum` in `int`.</span><span class="sxs-lookup"><span data-stu-id="48e02-121">For example, the following statement assigns the enumerator `Sun` to a variable of the type [int](../../../csharp/language-reference/keywords/int.md) by using a cast to convert from `enum` to `int`.</span></span>  
  
```  
int x = (int)Days.Sun;  
```  
  
 <span data-ttu-id="48e02-122">Quando si applica <xref:System.FlagsAttribute?displayProperty=fullName> a un'enumerazione che contiene elementi che possono essere combinati con un'operazione `OR` bit per bit, l'attributo influisce sul comportamento di `enum` quando viene usato con alcuni strumenti.</span><span class="sxs-lookup"><span data-stu-id="48e02-122">When you apply <xref:System.FlagsAttribute?displayProperty=fullName> to an enumeration that contains elements that can be combined with a bitwise `OR` operation, the attribute affects the behavior of the `enum` when it is used with some tools.</span></span> <span data-ttu-id="48e02-123">È possibile notare queste modifiche quando si usano strumenti come i metodi della classe <xref:System.Console> e l'analizzatore di espressioni.</span><span class="sxs-lookup"><span data-stu-id="48e02-123">You can notice these changes when you use tools such as the <xref:System.Console> class methods and the Expression Evaluator.</span></span> <span data-ttu-id="48e02-124">Vedere il terzo esempio.</span><span class="sxs-lookup"><span data-stu-id="48e02-124">(See the third example.)</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="48e02-125">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="48e02-125">Robust Programming</span></span>  
 <span data-ttu-id="48e02-126">Come per le altre costanti, tutti i riferimenti ai singoli valori di un'enumerazione vengono convertiti in valori letterali numerici in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="48e02-126">Just as with any constant, all references to the individual values of an enum are converted to numeric literals at compile time.</span></span> <span data-ttu-id="48e02-127">Questo può creare potenziali problemi relativi al controllo delle versioni come descritto in [Costanti](../../../csharp/programming-guide/classes-and-structs/constants.md).</span><span class="sxs-lookup"><span data-stu-id="48e02-127">This can create potential versioning issues as described in [Constants](../../../csharp/programming-guide/classes-and-structs/constants.md).</span></span>  
  
 <span data-ttu-id="48e02-128">L'assegnazione di valori aggiuntivi alle nuove versioni delle enumerazioni o la modifica dei valori dei membri enum in una nuova versione può causare problemi per il codice sorgente dipendente.</span><span class="sxs-lookup"><span data-stu-id="48e02-128">Assigning additional values to new versions of enums, or changing the values of the enum members in a new version, can cause problems for dependent source code.</span></span> <span data-ttu-id="48e02-129">I valori enum spesso vengono usati nelle istruzioni [switch](../../../csharp/language-reference/keywords/switch.md) .</span><span class="sxs-lookup"><span data-stu-id="48e02-129">Enum values often are used in [switch](../../../csharp/language-reference/keywords/switch.md) statements.</span></span> <span data-ttu-id="48e02-130">Se sono stati aggiunti altri elementi al tipo `enum` , la sezione predefinita dell'istruzione switch può essere selezionata in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="48e02-130">If additional elements have been added to the `enum` type, the default section of the switch statement can be selected unexpectedly.</span></span>  
  
 <span data-ttu-id="48e02-131">Se altri sviluppatori usano il codice, è opportuno fornire indicazioni su come dovrebbe rispondere il loro codice quando vengono aggiunti nuovi elementi a qualsiasi tipo `enum` .</span><span class="sxs-lookup"><span data-stu-id="48e02-131">If other developers use your code, you should provide guidelines about how their code should react if new elements are added to any `enum` types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48e02-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="48e02-132">Example</span></span>  
 <span data-ttu-id="48e02-133">Nell'esempio seguente viene dichiarata un'enumerazione `Days`.</span><span class="sxs-lookup"><span data-stu-id="48e02-133">In the following example, an enumeration, `Days`, is declared.</span></span> <span data-ttu-id="48e02-134">Due enumeratori vengono convertiti esplicitamente in un valore integer e assegnati a variabili integer.</span><span class="sxs-lookup"><span data-stu-id="48e02-134">Two enumerators are explicitly converted to integer and assigned to integer variables.</span></span>  
  
 <span data-ttu-id="48e02-135">[!code-cs[csrefKeywordsTypes#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="48e02-135">[!code-cs[csrefKeywordsTypes#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="48e02-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="48e02-136">Example</span></span>  
 <span data-ttu-id="48e02-137">Nell'esempio seguente l'opzione del tipo di base viene usata per dichiarare un `enum` i cui membri sono di tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="48e02-137">In the following example, the base-type option is used to declare an `enum` whose members are of type `long`.</span></span> <span data-ttu-id="48e02-138">Si noti che, anche se il tipo sottostante dell'enumerazione è `long`, i membri dell'enumerazione non sono ancora stati convertiti esplicitamente nel tipo `long` con un cast.</span><span class="sxs-lookup"><span data-stu-id="48e02-138">Notice that even though the underlying type of the enumeration is `long`, the enumeration members still must be explicitly converted to type `long` by using a cast.</span></span>  
  
 <span data-ttu-id="48e02-139">[!code-cs[csrefKeywordsTypes#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="48e02-139">[!code-cs[csrefKeywordsTypes#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="48e02-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="48e02-140">Example</span></span>  
 <span data-ttu-id="48e02-141">L'esempio di codice seguente illustra l'utilizzo e gli effetti dell'attributo <xref:System.FlagsAttribute?displayProperty=fullName> su una dichiarazione `enum` .</span><span class="sxs-lookup"><span data-stu-id="48e02-141">The following code example illustrates the use and effect of the <xref:System.FlagsAttribute?displayProperty=fullName> attribute on an `enum` declaration.</span></span>  
  
 <span data-ttu-id="48e02-142">[!code-cs[csrefKeywordsTypes#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="48e02-142">[!code-cs[csrefKeywordsTypes#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_3.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="48e02-143">Commenti</span><span class="sxs-lookup"><span data-stu-id="48e02-143">Comments</span></span>  
 <span data-ttu-id="48e02-144">Se si rimuove `Flags`, l'esempio visualizza i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="48e02-144">If you remove `Flags`, the example displays the following values:</span></span>  
  
 `5`  
  
 `5`  
  
## <a name="c-language-specification"></a><span data-ttu-id="48e02-145">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="48e02-145">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="48e02-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48e02-146">See Also</span></span>  
 <span data-ttu-id="48e02-147">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="48e02-147">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="48e02-148">[Tipi di enumerazione](../../../csharp/programming-guide/enumeration-types.md) </span><span class="sxs-lookup"><span data-stu-id="48e02-148">[Enumeration Types](../../../csharp/programming-guide/enumeration-types.md) </span></span>  
 <span data-ttu-id="48e02-149">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="48e02-149">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="48e02-150">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="48e02-150">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="48e02-151">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="48e02-151">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="48e02-152">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="48e02-152">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="48e02-153">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="48e02-153">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

