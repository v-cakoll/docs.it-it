---
title: Analisi di altre stringhe in .NET
description: Analisi di altre stringhe in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 67670b10-3df4-45ea-8908-5ba3f056887c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: db80cc5f37e814f224ff76b14a906bb4d41064fb
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="e300f-104">Analisi di altre stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="e300f-104">Parsing other strings in .NET</span></span>

<span data-ttu-id="e300f-105">Oltre alle stringhe numeriche e [DateTime](xref:System.DateTime) è possibile analizzare le stringhe che rappresentano i tipi [Char](xref:System.Char), [Boolean](xref:System.Boolean) ed [Enum](xref:System.Enum) in tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="e300f-105">In addition to numeric and [DateTime](xref:System.DateTime) strings, you can also parse strings that represent the types [Char](xref:System.Char), [Boolean](xref:System.Boolean), and [Enum](xref:System.Enum) into data types.</span></span>

## <a name="char"></a><span data-ttu-id="e300f-106">Char</span><span class="sxs-lookup"><span data-stu-id="e300f-106">Char</span></span>

<span data-ttu-id="e300f-107">Il metodo di analisi statico associato al tipo di dati [Char](xref:System.Char) è utile per la conversione di una stringa contenente un solo carattere nel valore Unicode corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e300f-107">The static parse method associated with the [Char](xref:System.Char) data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="e300f-108">Nell'esempio seguente viene analizzata una stringa in un carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="e300f-108">The following code example parses a string into a Unicode character.</span></span>

```csharp
string MyString1 = "A";
char MyChar = Char.Parse(MyString1);
// MyChar now contains a Unicode "A" character.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="boolean"></a><span data-ttu-id="e300f-109">Booleano</span><span class="sxs-lookup"><span data-stu-id="e300f-109">Boolean</span></span>

<span data-ttu-id="e300f-110">Il tipo di dati [Boolean](xref:System.Boolean) contiene un metodo [Parse](xref:System.Boolean.Parse(System.String)) che può essere usato per convertire una stringa che rappresenta un valore `Boolean` in un vero e proprio tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="e300f-110">The [Boolean](xref:System.Boolean) data type contains a [Parse](xref:System.Boolean.Parse(System.String)) method that you can use to convert a string that represents a `Boolean` value into an actual `Boolean` type.</span></span> <span data-ttu-id="e300f-111">Questo metodo non fa distinzione tra maiuscole e minuscole e consente di analizzare correttamente una stringa contenente "True" o "False".</span><span class="sxs-lookup"><span data-stu-id="e300f-111">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="e300f-112">Il metodo `Parse` associato al tipo `Boolean` consente anche di analizzare stringhe precedute e seguite da spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="e300f-112">The `Parse` method associated with the `Boolean` type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="e300f-113">Se viene passata qualsiasi altra stringa, viene generata un'eccezione [FormatException](xref:System.FormatException).</span><span class="sxs-lookup"><span data-stu-id="e300f-113">If any other string is passed, a [FormatException](xref:System.FormatException) is thrown.</span></span>

<span data-ttu-id="e300f-114">Nell'esempio di codice seguente viene usato il metodo `Parse` per convertire una stringa in un valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="e300f-114">The following code example uses the `Parse` method to convert a string into a `Boolean` value.</span></span>

```csharp
string MyString2 = "True";
bool MyBool = bool.Parse(MyString2);
// MyBool now contains a True Boolean value.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="enumeration"></a><span data-ttu-id="e300f-115">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="e300f-115">Enumeration</span></span>

<span data-ttu-id="e300f-116">È possibile usare il metodo statico [Parse](xref:System.Enum.Parse(System.Type,System.String)) per inizializzare un tipo di enumerazione per il valore di una stringa.</span><span class="sxs-lookup"><span data-stu-id="e300f-116">You can use the static [Parse](xref:System.Enum.Parse(System.Type,System.String)) method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="e300f-117">Questo metodo accetta il tipo di enumerazione che si sta analizzando, la stringa da analizzare un flag `Boolean` facoltativo che indica se l'analisi fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="e300f-117">This method accepts the enumeration type you are parsing, the string to parse, and an optional `Boolean` flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="e300f-118">La stringa da analizzare può contenere diversi valori separati da virgole, che possono essere preceduti o seguiti da uno o più spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="e300f-118">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="e300f-119">Quando la stringa contiene più valori, il valore dell'oggetto restituito è il valore di tutti i valori specificati combinati con un'operazione OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="e300f-119">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>

<span data-ttu-id="e300f-120">Nell'esempio seguente viene usato il metodo `Parse` per convertire una rappresentazione di stringa in un valore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="e300f-120">The following example uses the `Parse` method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="e300f-121">L'enumerazione [DayOfWeek](xref:System.DayOfWeek) viene inizializzata su Thursday da una stringa.</span><span class="sxs-lookup"><span data-stu-id="e300f-121">The [DayOfWeek](xref:System.DayOfWeek) enumeration is initialized to Thursday from a string.</span></span>

```csharp
string MyString3 = "Thursday";
DayOfWeek MyDays = (DayOfWeek)Enum.Parse(typeof(DayOfWeek), MyString3);
Console.WriteLine(MyDays);
// The result is Thursday.
```

```vb
Dim MyString3 As String = "Thursday"
Dim MyDays As DayOfWeek = CType([Enum].Parse(GetType(DayOfWeek), MyString3), DayOfWeek)
Console.WriteLine("{0:G}", MyDays)
' The result is Thursday.
```

## <a name="see-also"></a><span data-ttu-id="e300f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e300f-122">See Also</span></span>

[<span data-ttu-id="e300f-123">Analisi di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="e300f-123">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="e300f-124">Formattazione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="e300f-124">Formatting types in .NET</span></span>](formatting-types.md)

[<span data-ttu-id="e300f-125">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="e300f-125">Type conversion in .NET</span></span>](type-conversion.md)


