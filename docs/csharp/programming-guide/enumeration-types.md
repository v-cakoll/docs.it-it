---
title: Tipi di enumerazione - Guida per programmatori C#
ms.custom: seodec18
ms.date: 09/10/2017
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
ms.openlocfilehash: 669357bbd6527324bbedbcf1f537bf570c63ce5b
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423664"
---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="ac5d4-102">Tipi di enumerazione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ac5d4-102">Enumeration types (C# Programming Guide)</span></span>

<span data-ttu-id="ac5d4-103">Un tipo di enumerazione (detto anche enumerazione o enum) rappresenta un modo efficiente per definire un set di costanti integrali denominate che possono essere assegnate a una variabile.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="ac5d4-104">Si supponga ad esempio di dover definire una variabile il cui valore rappresenterà un giorno della settimana.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="ac5d4-105">Ci sono solo sette valori significativi che la variabile potrà mai archiviare.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="ac5d4-106">Per definire tali valori, è possibile usare un tipo di enumerazione, dichiarato tramite la parola chiave [enum](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="ac5d4-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../../csharp/language-reference/keywords/enum.md) keyword.</span></span>

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

<span data-ttu-id="ac5d4-107">Per impostazione predefinita, il tipo sottostante di ogni elemento dell'enumerazione è [int](../../csharp/language-reference/builtin-types/integral-numeric-types.md). È possibile specificare un altro tipo numerico integrale usando i due punti, come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-107">By default the underlying type of each element in the enum is [int](../../csharp/language-reference/builtin-types/integral-numeric-types.md). You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="ac5d4-108">Per un elenco completo dei tipi possibili, vedere [enum (Riferimenti per C#)](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="ac5d4-108">For a full list of possible types, see [enum (C# Reference)](../../csharp/language-reference/keywords/enum.md).</span></span>

<span data-ttu-id="ac5d4-109">È possibile verificare i valori numerici sottostanti eseguendo il cast al tipo sottostante, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-109">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

<span data-ttu-id="ac5d4-110">I vantaggi dell'uso di enum anziché di un tipo numerico sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac5d4-110">The following are advantages of using an enum instead of a numeric type:</span></span>

- <span data-ttu-id="ac5d4-111">Si specifica in modo chiaro per il codice client quali sono i valori validi per la variabile.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-111">You clearly specify for client code which values are valid for the variable.</span></span>

- <span data-ttu-id="ac5d4-112">In Visual Studio IntelliSense elenca i valori definiti.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-112">In Visual Studio, IntelliSense lists the defined values.</span></span>

<span data-ttu-id="ac5d4-113">Quando non si specificano valori per gli elementi nell'elenco di enumeratori, i valori vengono incrementati automaticamente di 1.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-113">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="ac5d4-114">Nell'esempio precedente, `Day.Sunday` ha valore 0, `Day.Monday` ha valore 1 e così via.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-114">In the previous example, `Day.Sunday` has a value of 0, `Day.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="ac5d4-115">Quando si crea un nuovo oggetto `Day`, se a questo non si assegna un valore in modo esplicito, l'oggetto avrà il valore predefinito `Day.Sunday` (0).</span><span class="sxs-lookup"><span data-stu-id="ac5d4-115">When you create a new `Day` object, it will have a default value of `Day.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="ac5d4-116">Quando si crea un enum, selezionare il valore predefinito più logico e assegnare a questo un valore pari a zero.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-116">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="ac5d4-117">In tal modo tutti gli enum avranno quel valore predefinito, se non è stato loro assegnato un valore in modo esplicito al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-117">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>

<span data-ttu-id="ac5d4-118">Se la variabile `meetingDay` è di tipo `Day`, è possibile assegnare (senza un cast esplicito) solo uno dei valori definiti da `Day`.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-118">If the variable `meetingDay` is of type `Day`, then (without an explicit cast) you can only assign it one of the values defined by `Day`.</span></span> <span data-ttu-id="ac5d4-119">E se il giorno della riunione cambia, è possibile assegnare un nuovo valore da `Day` a `meetingDay`:</span><span class="sxs-lookup"><span data-stu-id="ac5d4-119">And if the meeting day changes, you can assign a new value from `Day` to `meetingDay`:</span></span>

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> <span data-ttu-id="ac5d4-120">È possibile assegnare a `meetingDay` qualsiasi valore intero arbitrario.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-120">It's possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="ac5d4-121">Ad esempio, questa riga di codice non genera un errore: `meetingDay = (Day) 42`.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-121">For example, this line of code does not produce an error: `meetingDay = (Day) 42`.</span></span> <span data-ttu-id="ac5d4-122">Questa impostazione, tuttavia, non è consigliabile perché l'aspettativa implicita è che una variabile enum contenga solo uno dei valori definiti dal tipo enum.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-122">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="ac5d4-123">L'assegnazione di un valore arbitrario a una variabile di tipo enum comporta un rischio elevato di errore.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-123">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>

<span data-ttu-id="ac5d4-124">È possibile assegnare qualsiasi valore agli elementi nell'elenco di enumeratori di un tipo di enumerazione ed è anche possibile usare valori calcolati:</span><span class="sxs-lookup"><span data-stu-id="ac5d4-124">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="ac5d4-125">Tipi di enumerazione come flag di bit</span><span class="sxs-lookup"><span data-stu-id="ac5d4-125">Enumeration types as bit flags</span></span>

<span data-ttu-id="ac5d4-126">È possibile usare un tipo di enumerazione per definire flag di bit, che consentono a un'istanza del tipo di enumerazione di archiviare qualsiasi combinazione dei valori definiti nell'elenco di enumeratori.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-126">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="ac5d4-127">Naturalmente alcune combinazioni potrebbero non essere significative o consentite nel codice del programma.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-127">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>

<span data-ttu-id="ac5d4-128">Un enum di flag di bit viene creato applicando l'attributo <xref:System.FlagsAttribute?displayProperty=nameWithType> e definendo in modo appropriato i valori in modo che sia possibile eseguirvi operazioni bit per bit `AND`, `OR`, `NOT` e `XOR`.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-128">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="ac5d4-129">In un enum di flag di bit, includere una costante denominata con valore zero, che indica che non sono impostati flag.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-129">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="ac5d4-130">Assegnare a un flag un valore pari a zero solo per indicare che non sono impostati flag.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-130">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>

<span data-ttu-id="ac5d4-131">Nell'esempio seguente viene definita un'altra versione dell'enum `Day` denominata `Days`.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-131">In the following example, another version of the `Day` enum, which is named `Days`, is defined.</span></span> <span data-ttu-id="ac5d4-132">`Days` dispone dell'attributo `Flags`. A ogni valore viene assegnata la successiva potenza di 2.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-132">`Days` has the `Flags` attribute, and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="ac5d4-133">In questo modo è possibile creare una variabile `Days` il cui valore è `Days.Tuesday | Days.Thursday`.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-133">This enables you to create a `Days` variable whose value is `Days.Tuesday | Days.Thursday`.</span></span>

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

<span data-ttu-id="ac5d4-134">Per impostare un flag su un enum, usare l'operatore `OR` bit per bit come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ac5d4-134">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

<span data-ttu-id="ac5d4-135">Per determinare se un flag specifico è impostato, usare l'operatore `AND` bit per bit come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ac5d4-135">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

<span data-ttu-id="ac5d4-136">Per altre informazioni sugli aspetti da considerare quando si definiscono tipi di enumerazione con l'attributo <xref:System.FlagsAttribute?displayProperty=nameWithType>, vedere <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-136">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="ac5d4-137">Uso dei metodi System.Enum per individuare e modificare valori enum</span><span class="sxs-lookup"><span data-stu-id="ac5d4-137">Using the System.Enum methods to discover and manipulate enum values</span></span>

<span data-ttu-id="ac5d4-138">Tutti gli enum sono istanze del tipo <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-138">All enums are instances of the <xref:System.Enum?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="ac5d4-139">Non è possibile derivare nuove classi da <xref:System.Enum?displayProperty=nameWithType>, ma è possibile usarne i metodi per individuare informazioni e modificare valori in un'istanza dell'enum.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-139">You cannot derive new classes from <xref:System.Enum?displayProperty=nameWithType>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

<span data-ttu-id="ac5d4-140">Per altre informazioni, vedere <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-140">For more information, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="ac5d4-141">È anche possibile creare un nuovo metodo per un enum tramite un metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="ac5d4-141">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="ac5d4-142">Per altre informazioni, vedere [Procedura: Creare un nuovo metodo per un'enumerazione](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ac5d4-142">For more information, see [How to: Create a New Method for an Enumeration](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ac5d4-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac5d4-143">See also</span></span>

- <xref:System.Enum?displayProperty=nameWithType>
- [<span data-ttu-id="ac5d4-144">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ac5d4-144">C# Programming Guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ac5d4-145">enum</span><span class="sxs-lookup"><span data-stu-id="ac5d4-145">enum</span></span>](../../csharp/language-reference/keywords/enum.md)
