---
title: string (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- string
- string_CSharpKeyword
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8899eb75b1b7c556a1e92f173a4d0ca4135014c8
ms.sourcegitcommit: 1c0b0f082b3f300e54b4d069b317ac724c88ddc3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2018
---
# <a name="string-c-reference"></a><span data-ttu-id="c0426-102">string (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c0426-102">string (C# Reference)</span></span>
<span data-ttu-id="c0426-103">Il tipo `string` rappresenta una sequenza di zero o più caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="c0426-103">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="c0426-104">`string` è un alias per <xref:System.String> in .NET.</span><span class="sxs-lookup"><span data-stu-id="c0426-104">`string` is an alias for <xref:System.String> in .NET.</span></span>  
  
 <span data-ttu-id="c0426-105">Sebbene `string` sia un tipo riferimento, gli operatori di uguaglianza (`==` e `!=`) vengono definiti per confrontare i valori degli oggetti `string` e non dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="c0426-105">Although `string` is a reference type, the equality operators (`==` and `!=`) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="c0426-106">In questo modo il test di uguaglianza delle stringhe è più intuitivo.</span><span class="sxs-lookup"><span data-stu-id="c0426-106">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="c0426-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c0426-107">For example:</span></span>  
  
```csharp  
string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 <span data-ttu-id="c0426-108">Viene visualizzato "True" e quindi "False" perché il contenuto delle stringhe è equivalente, ma `a` e `b` non fanno riferimento alla stessa istanza della stringa.</span><span class="sxs-lookup"><span data-stu-id="c0426-108">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>  
  
 <span data-ttu-id="c0426-109">L'operatore + concatena le stringhe:</span><span class="sxs-lookup"><span data-stu-id="c0426-109">The + operator concatenates strings:</span></span>  
  
```csharp  
string a = "good " + "morning";  
```  
  
 <span data-ttu-id="c0426-110">Questo crea un oggetto stringa contenente "good morning".</span><span class="sxs-lookup"><span data-stu-id="c0426-110">This creates a string object that contains "good morning".</span></span>  
  
 <span data-ttu-id="c0426-111">Le stringhe sono *immutabili*: non è possibile modificare il contenuto di un oggetto stringa dopo la creazione dell'oggetto, sebbene la sintassi sembri indicare che è possibile apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="c0426-111">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="c0426-112">Ad esempio, quando si scrive il codice, il compilatore crea un nuovo oggetto stringa per archiviare la nuova sequenza di caratteri e il nuovo oggetto viene assegnato a b.</span><span class="sxs-lookup"><span data-stu-id="c0426-112">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to b.</span></span> <span data-ttu-id="c0426-113">La stringa "h" è quindi idonea per Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c0426-113">The string "h" is then eligible for garbage collection.</span></span>  
  
```csharp
string b = "h";  
b += "ello";  
```  
  
 <span data-ttu-id="c0426-114">L'operatore [] può essere usato per accedere in lettura ai singoli caratteri di un `string`:</span><span class="sxs-lookup"><span data-stu-id="c0426-114">The [] operator can be used for readonly access to individual characters of a `string`:</span></span>  
  
```csharp  
string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 <span data-ttu-id="c0426-115">I valori letterali della stringa sono di tipo `string` e possono essere scritti in due formati, tra virgolette e @-quoted.</span><span class="sxs-lookup"><span data-stu-id="c0426-115">String literals are of type `string` and can be written in two forms, quoted and @-quoted.</span></span> <span data-ttu-id="c0426-116">I valori letterali della stringa tra virgolette sono racchiusi in virgolette doppie ("):</span><span class="sxs-lookup"><span data-stu-id="c0426-116">Quoted string literals are enclosed in double quotation marks ("):</span></span>  
  
```csharp  
"good morning"  // a string literal  
```  
  
 <span data-ttu-id="c0426-117">I valori letterali della stringa possono contenere qualsiasi carattere letterale.</span><span class="sxs-lookup"><span data-stu-id="c0426-117">String literals can contain any character literal.</span></span> <span data-ttu-id="c0426-118">Sono incluse le sequenze di escape.</span><span class="sxs-lookup"><span data-stu-id="c0426-118">Escape sequences are included.</span></span> <span data-ttu-id="c0426-119">L'esempio seguente usa una sequenza di escape `\\` per la barra rovesciata, `\u0066` per la lettera f e `\n` per la nuova riga.</span><span class="sxs-lookup"><span data-stu-id="c0426-119">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>  
  
```  
string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  <span data-ttu-id="c0426-120">Il codice di escape `\udddd` (dove `dddd` è un numero a quattro cifre) rappresenta il carattere Unicode U+`dddd`.</span><span class="sxs-lookup"><span data-stu-id="c0426-120">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="c0426-121">Vengono riconosciuti anche i codici di escape Unicode a otto cifre: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="c0426-121">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>  
  
 <span data-ttu-id="c0426-122">I valori letterali della stringa verbatim iniziano con `@` e sono anche racchiusi tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="c0426-122">Verbatim string literals start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="c0426-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c0426-123">For example:</span></span>  
  
```csharp  
@"good morning"  // a string literal  
```  
  
 <span data-ttu-id="c0426-124">Il vantaggio delle stringhe verbatim è che le sequenze di escape *non* sono elaborate, e quindi rendono più semplice scrivere, ad esempio, un nome completo del file:</span><span class="sxs-lookup"><span data-stu-id="c0426-124">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified file name:</span></span>  
  
```csharp  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 <span data-ttu-id="c0426-125">Per includere le virgolette doppie in una stringa @-quoted, duplicarla:</span><span class="sxs-lookup"><span data-stu-id="c0426-125">To include a double quotation mark in an @-quoted string, double it:</span></span>  
  
```csharp  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 <span data-ttu-id="c0426-126">Per altri usi del carattere speciale `@`, vedere [@ - identificatore verbatim](../tokens/verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="c0426-126">For other uses of the `@` special character, see [@ -- verbatim identifier](../tokens/verbatim.md).</span></span>  
  
 <span data-ttu-id="c0426-127">Per altre informazioni sulle stringhe in C#, vedere [Stringhe](../../../csharp/programming-guide/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0426-127">For more information about strings in C#, see [Strings](../../../csharp/programming-guide/strings/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0426-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0426-128">Example</span></span>  
 [!code-csharp[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="c0426-129">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c0426-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c0426-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0426-130">See Also</span></span>  
 [<span data-ttu-id="c0426-131">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c0426-131">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c0426-132">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c0426-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c0426-133">Procedure consigliate per l'uso delle stringhe</span><span class="sxs-lookup"><span data-stu-id="c0426-133">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)  
 [<span data-ttu-id="c0426-134">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="c0426-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c0426-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c0426-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c0426-136">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="c0426-136">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="c0426-137">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="c0426-137">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="c0426-138">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="c0426-138">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)  
 [<span data-ttu-id="c0426-139">Creazione di nuove stringhe</span><span class="sxs-lookup"><span data-stu-id="c0426-139">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="c0426-140">Tabella di formattazione dei risultati numerici</span><span class="sxs-lookup"><span data-stu-id="c0426-140">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)
