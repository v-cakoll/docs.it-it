---
title: Stringhe interpolate (C#)
ms.date: 10/18/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b8a1fe0be82a0e09d61c66ed463199ff626c9faa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-c-reference"></a><span data-ttu-id="a280d-102">Stringhe interpolate (Riferimento per C#)</span><span class="sxs-lookup"><span data-stu-id="a280d-102">Interpolated Strings (C# Reference)</span></span>

<span data-ttu-id="a280d-103">Vengono usate per la costruzione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="a280d-103">Used to construct strings.</span></span>  <span data-ttu-id="a280d-104">Una stringa interpolata è simile a una stringa di modello che contiene *espressioni interpolate*.</span><span class="sxs-lookup"><span data-stu-id="a280d-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="a280d-105">Una stringa interpolata restituisce una stringa che sostituisce le espressioni interpolate in essa contenute con le rappresentazioni di stringa.</span><span class="sxs-lookup"><span data-stu-id="a280d-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span> <span data-ttu-id="a280d-106">Questa funzionalità è disponibile in c# 6 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a280d-106">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="a280d-107">Gli argomenti di una stringa interpolata sono più facili da comprendere rispetto a una [stringa di formato composito](../../../standard/base-types/composite-formatting.md#composite-format-string).</span><span class="sxs-lookup"><span data-stu-id="a280d-107">The arguments of an interpolated string are easier to understand than a [composite format string](../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="a280d-108">Ad esempio, la stringa interpolata</span><span class="sxs-lookup"><span data-stu-id="a280d-108">For example, the interpolated string</span></span>  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}");
```  
<span data-ttu-id="a280d-109">contiene due espressioni interpolate, '{name}' e '{ora: hh}'.</span><span class="sxs-lookup"><span data-stu-id="a280d-109">contains two interpolated expressions, '{name}' and '{hour:hh}'.</span></span> <span data-ttu-id="a280d-110">La stringa di formato composito equivalente è:</span><span class="sxs-lookup"><span data-stu-id="a280d-110">The equivalent composite format string is:</span></span>

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

<span data-ttu-id="a280d-111">La struttura di una stringa interpolata è:</span><span class="sxs-lookup"><span data-stu-id="a280d-111">The structure of an interpolated string is:</span></span>  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="a280d-112">dove:</span><span class="sxs-lookup"><span data-stu-id="a280d-112">where:</span></span> 

- <span data-ttu-id="a280d-113">*field-width* è un intero con segno che indica il numero di caratteri nel campo.</span><span class="sxs-lookup"><span data-stu-id="a280d-113">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="a280d-114">Se è positivo, il campo viene allineato a destra; se è negativo, viene allineato a sinistra.</span><span class="sxs-lookup"><span data-stu-id="a280d-114">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="a280d-115">*format-string* è una stringa di formato appropriata per il tipo di oggetto formattato.</span><span class="sxs-lookup"><span data-stu-id="a280d-115">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="a280d-116">Ad esempio, per un valore <xref:System.DateTime>, potrebbe essere una stringa di formato data e ora standard come "D" o "d".</span><span class="sxs-lookup"><span data-stu-id="a280d-116">For example, for a <xref:System.DateTime> value, it could be a standard date and time format string such as "D" or "d".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a280d-117">È possibile disporre di qualsiasi spazio vuoto tra il `$` e `"` che inizia la stringa.</span><span class="sxs-lookup"><span data-stu-id="a280d-117">You cannot have any whitespace between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="a280d-118">In questo modo, un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a280d-118">Doing so causes a compile time error.</span></span>

 <span data-ttu-id="a280d-119">È possibile usare una stringa interpolata ovunque sia possibile usare un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="a280d-119">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="a280d-120">La stringa interpolata viene valutata ogni volta che si esegue codice con la stringa interpolata.</span><span class="sxs-lookup"><span data-stu-id="a280d-120">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="a280d-121">Ciò consente di separare la definizione e la valutazione di una stringa interpolata.</span><span class="sxs-lookup"><span data-stu-id="a280d-121">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="a280d-122">Per includere una parentesi graffa ("{" o "}") in una stringa interpolata, digitarne due, ovvero "{{" o "}}".</span><span class="sxs-lookup"><span data-stu-id="a280d-122">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="a280d-123">Per altri dettagli, vedere la sezione Conversioni implicite.</span><span class="sxs-lookup"><span data-stu-id="a280d-123">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="a280d-124">Se la stringa interpolata contiene altri caratteri con un significato speciale in una stringa interpolata, ad esempio virgolette doppie ("), due punti (:) o virgola (,), è necessario specificare il carattere di escape se si presentano nel testo letterale, oppure inserirli in un'espressione racchiusa tra parentesi se sono elementi del linguaggio inclusi in un'espressione interpolata.</span><span class="sxs-lookup"><span data-stu-id="a280d-124">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="a280d-125">Nell'esempio seguente viene specificato il carattere di escape delle virgolette per includerle nella stringa di risultato e si usano le parentesi per delimitare l'espressione `(age == 1 ? "" : "s")` in modo che i due punti non vengano interpretati come l'inizio di una stringa di formato.</span><span class="sxs-lookup"><span data-stu-id="a280d-125">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]  

<span data-ttu-id="a280d-126">Verbatim interpolati utilizzare stringhe di `$` carattere seguito dal `@` carattere.</span><span class="sxs-lookup"><span data-stu-id="a280d-126">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="a280d-127">Per ulteriori informazioni sulle stringhe verbatim, vedere il [stringa](string.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="a280d-127">For more information about verbatim strings, see the [string](string.md) topic.</span></span> <span data-ttu-id="a280d-128">Il codice seguente è una versione modificata del frammento di codice precedente, utilizzando una stringa interpolata verbatim:</span><span class="sxs-lookup"><span data-stu-id="a280d-128">The following code is a modified version of the previous snippet using a verbatim interpolated string:</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings5.cs#1)]  

<span data-ttu-id="a280d-129">Le modifiche alla formattazione sono necessarie perché non sono conformi alle stringhe verbatim `\` sequenze di escape.</span><span class="sxs-lookup"><span data-stu-id="a280d-129">The formatting changes are necessary because verbatim strings do not obey `\` escape sequences.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a280d-130">Il `$` token deve precedere il `@` token in una stringa interpolata verbatim.</span><span class="sxs-lookup"><span data-stu-id="a280d-130">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>


## <a name="implicit-conversions"></a><span data-ttu-id="a280d-131">Conversioni implicite</span><span class="sxs-lookup"><span data-stu-id="a280d-131">Implicit Conversions</span></span>  

<span data-ttu-id="a280d-132">Da una stringa interpolata vengono effettuate tre conversioni di tipo implicito:</span><span class="sxs-lookup"><span data-stu-id="a280d-132">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="a280d-133">Conversione di una stringa interpolata in una <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="a280d-133">Conversion of an interpolated string to a <xref:System.String>.</span></span> <span data-ttu-id="a280d-134">L'esempio seguente restituisce una stringa in cui le espressioni di stringa interpolata sono state sostituite con le rappresentazioni di stringa.</span><span class="sxs-lookup"><span data-stu-id="a280d-134">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="a280d-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a280d-135">For example:</span></span>

   [!code-csharp[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]  

   <span data-ttu-id="a280d-136">Questo è il risultato finale di un'interpretazione della stringa.</span><span class="sxs-lookup"><span data-stu-id="a280d-136">This is the final result of a string interpretation.</span></span> <span data-ttu-id="a280d-137">Tutte le occorrenze delle parentesi graffe doppie ("{{" e "}}") vengono convertite in parentesi graffe singole.</span><span class="sxs-lookup"><span data-stu-id="a280d-137">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="a280d-138">Conversione di una stringa interpolata in una variabile <xref:System.IFormattable> che consente di creare più stringhe risultato con contenuto specifico delle impostazioni cultura da una singola istanza di <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="a280d-138">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="a280d-139">Ciò è utile per includere elementi quali i formati numerici e di data corretti per singole impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a280d-139">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="a280d-140">Tutte le occorrenze di parentesi graffe doppie ("{{" e "}}") rimangono tali finché la stringa non viene formattata in modo implicito o esplicito chiamando il metodo <xref:System.Object.ToString>.</span><span class="sxs-lookup"><span data-stu-id="a280d-140">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the <xref:System.Object.ToString> method.</span></span>  <span data-ttu-id="a280d-141">Tutte le espressioni di interpolazione contenute vengono convertite in {0}, \{1\} e così via.</span><span class="sxs-lookup"><span data-stu-id="a280d-141">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="a280d-142">Nell'esempio seguente viene usata la reflection per visualizzare i membri, nonché i valori di campi e le proprietà di una variabile <xref:System.IFormattable> creata da una stringa interpolata.</span><span class="sxs-lookup"><span data-stu-id="a280d-142">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="a280d-143">Passa, inoltre, il <xref:System.IFormattable> variabile il <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="a280d-143">It also passes the <xref:System.IFormattable> variable to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method.</span></span>

   [!code-csharp[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]  

   <span data-ttu-id="a280d-144">Si noti che la stringa interpolata può essere controllata solo tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="a280d-144">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="a280d-145">Se viene passato a una stringa come metodo di formattazione <xref:System.Console.WriteLine(System.String)>, gli elementi di formato vengono risolti e restituita la stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="a280d-145">If it is passed to a string formatting method, such as <xref:System.Console.WriteLine(System.String)>, its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="a280d-146">Conversione di una stringa interpolata in una variabile <xref:System.FormattableString> che rappresenta una stringa di formato composito.</span><span class="sxs-lookup"><span data-stu-id="a280d-146">Conversion of an interpolated string to an <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="a280d-147">Grazie all'esame della stringa di formato composito e del modo in cui viene eseguito il rendering come stringa di risultato, è ad esempio possibile attuare misure di protezione contro attacchi di tipo injection durante la creazione di una query.</span><span class="sxs-lookup"><span data-stu-id="a280d-147">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span> <span data-ttu-id="a280d-148"><xref:System.FormattableString> include anche overload <xref:System.FormattableString.ToString> che consentono di generare stringhe di risultato per <xref:System.Globalization.CultureInfo.InvariantCulture> e <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="a280d-148"><xref:System.FormattableString> also includes <xref:System.FormattableString.ToString> overloads that let you produce result strings for the <xref:System.Globalization.CultureInfo.InvariantCulture> and <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>  <span data-ttu-id="a280d-149">Tutte le occorrenze delle parentesi graffe doppie ("{{" e "}}") rimangono invariate finché non si applica la formattazione.</span><span class="sxs-lookup"><span data-stu-id="a280d-149">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces, until you format.</span></span>  <span data-ttu-id="a280d-150">Tutte le espressioni di interpolazione contenute vengono convertite in {0}, \{1\} e così via.</span><span class="sxs-lookup"><span data-stu-id="a280d-150">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   [!code-csharp[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]  

## <a name="language-specification"></a><span data-ttu-id="a280d-151">Specifiche del linguaggio</span><span class="sxs-lookup"><span data-stu-id="a280d-151">Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a280d-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a280d-152">See Also</span></span>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [<span data-ttu-id="a280d-153">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a280d-153">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a280d-154">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a280d-154">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
