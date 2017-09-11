---
title: Confronto di stringhe
description: Confronto di stringhe
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 920ee5e8-3d61-4941-b5af-fc50eaee427c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 47ee37886fa2662a89730e9d52ee04987e37da2f
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="comparing-strings"></a><span data-ttu-id="aa776-104">Confronto di stringhe</span><span class="sxs-lookup"><span data-stu-id="aa776-104">Comparing strings</span></span>

<span data-ttu-id="aa776-105">.NET offre diversi metodi per confrontare i valori delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="aa776-105">.NET provides several methods to compare the values of strings.</span></span> <span data-ttu-id="aa776-106">La tabella seguente elenca e descrive i metodi di confronto di valori.</span><span class="sxs-lookup"><span data-stu-id="aa776-106">The following table lists and describes the value-comparison methods.</span></span>

<span data-ttu-id="aa776-107">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="aa776-107">Method name</span></span> | <span data-ttu-id="aa776-108">Uso</span><span class="sxs-lookup"><span data-stu-id="aa776-108">Use</span></span>
----------- | ---
<span data-ttu-id="aa776-109">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="aa776-109">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))</span></span> | <span data-ttu-id="aa776-110">Confronta i valori di due stringhe.</span><span class="sxs-lookup"><span data-stu-id="aa776-110">Compares the values of two strings.</span></span> <span data-ttu-id="aa776-111">Restituisce un valore intero.</span><span class="sxs-lookup"><span data-stu-id="aa776-111">Returns an integer value.</span></span>
<span data-ttu-id="aa776-112">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="aa776-112">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))</span></span> | <span data-ttu-id="aa776-113">Confronta due stringhe senza tenere in considerazione le impostazioni cultura locali.</span><span class="sxs-lookup"><span data-stu-id="aa776-113">Compares two strings without regard to local culture.</span></span> <span data-ttu-id="aa776-114">Restituisce un valore intero.</span><span class="sxs-lookup"><span data-stu-id="aa776-114">Returns an integer value.</span></span>
<span data-ttu-id="aa776-115">[String.CompareTo](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="aa776-115">[String.CompareTo](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="aa776-116">Confronta l'oggetto stringa corrente con un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="aa776-116">Compares the current string object to another string.</span></span> <span data-ttu-id="aa776-117">Restituisce un valore intero.</span><span class="sxs-lookup"><span data-stu-id="aa776-117">Returns an integer value.</span></span>
<span data-ttu-id="aa776-118">[String.StartsWith](xref:System.String.StartsWith(System.String))</span><span class="sxs-lookup"><span data-stu-id="aa776-118">[String.StartsWith](xref:System.String.StartsWith(System.String))</span></span> | <span data-ttu-id="aa776-119">Determina se una stringa inizia con la stringa passata.</span><span class="sxs-lookup"><span data-stu-id="aa776-119">Determines whether a string begins with the string passed.</span></span> <span data-ttu-id="aa776-120">Restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="aa776-120">Returns a Boolean value.</span></span>
<span data-ttu-id="aa776-121">[String.EndsWith](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="aa776-121">[String.EndsWith](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="aa776-122">Determina se una stringa finisce con la stringa passata.</span><span class="sxs-lookup"><span data-stu-id="aa776-122">Determines whether a string ends with the string passed.</span></span> <span data-ttu-id="aa776-123">Restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="aa776-123">Returns a Boolean value.</span></span>
<span data-ttu-id="aa776-124">[String.Equals](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="aa776-124">[String.Equals](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="aa776-125">Determina se due stringhe sono uguali.</span><span class="sxs-lookup"><span data-stu-id="aa776-125">Determines whether two strings are the same.</span></span> <span data-ttu-id="aa776-126">Restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="aa776-126">Returns a Boolean value.</span></span>
<span data-ttu-id="aa776-127">[String.IndexOf](xref:System.String.IndexOf(System.Char))</span><span class="sxs-lookup"><span data-stu-id="aa776-127">[String.IndexOf](xref:System.String.IndexOf(System.Char))</span></span> | <span data-ttu-id="aa776-128">Restituisce la posizione di indice di un carattere o una stringa, a partire dall'inizio della stringa esaminata.</span><span class="sxs-lookup"><span data-stu-id="aa776-128">Returns the index position of a character or string, starting from the beginning of the string you are examining.</span></span> <span data-ttu-id="aa776-129">Restituisce un valore intero.</span><span class="sxs-lookup"><span data-stu-id="aa776-129">Returns an integer value.</span></span>
<span data-ttu-id="aa776-130">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))</span><span class="sxs-lookup"><span data-stu-id="aa776-130">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))</span></span> | <span data-ttu-id="aa776-131">Restituisce la posizione di indice di un carattere o una stringa, a partire dalla fine della stringa esaminata.</span><span class="sxs-lookup"><span data-stu-id="aa776-131">Returns the index position of a character or string, starting from the end of the string you are examining.</span></span> <span data-ttu-id="aa776-132">Restituisce un valore intero.</span><span class="sxs-lookup"><span data-stu-id="aa776-132">Returns an integer value.</span></span>

## <a name="compare"></a><span data-ttu-id="aa776-133">Compare</span><span class="sxs-lookup"><span data-stu-id="aa776-133">Compare</span></span>

<span data-ttu-id="aa776-134">Il metodo statico [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) consente di confrontare due stringhe in modo accurato.</span><span class="sxs-lookup"><span data-stu-id="aa776-134">The static [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method provides a thorough way of comparing two strings.</span></span> <span data-ttu-id="aa776-135">Questo metodo fa distinzione tra le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="aa776-135">This method is culturally aware.</span></span> <span data-ttu-id="aa776-136">È possibile usare questa funzione per confrontare due stringhe o le sottostringhe di due stringhe.</span><span class="sxs-lookup"><span data-stu-id="aa776-136">You can use this function to compare two strings or substrings of two strings.</span></span> <span data-ttu-id="aa776-137">Sono inoltre disponibili overload che consentono o meno di fare distinzione tra maiuscole e minuscole e di tenere o meno in considerazione le differenze nelle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="aa776-137">Additionally, overloads are provided that regard or disregard case and cultural variance.</span></span> <span data-ttu-id="aa776-138">La tabella seguente illustra i tre valori interi che questo metodo può restituire.</span><span class="sxs-lookup"><span data-stu-id="aa776-138">The following table shows the three integer values that this method might return.</span></span> 

<span data-ttu-id="aa776-139">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aa776-139">Return value</span></span> | <span data-ttu-id="aa776-140">Condizione</span><span class="sxs-lookup"><span data-stu-id="aa776-140">Condition</span></span>
------------ | ---------
<span data-ttu-id="aa776-141">Intero negativo</span><span class="sxs-lookup"><span data-stu-id="aa776-141">A negative integer</span></span> | <span data-ttu-id="aa776-142">La prima stringa precede la seconda stringa nella sequenza di ordinamento, oppure la prima stringa è `null`.</span><span class="sxs-lookup"><span data-stu-id="aa776-142">The first string precedes the second string in the sort order, or the first string is `null`.</span></span>
<span data-ttu-id="aa776-143">0</span><span class="sxs-lookup"><span data-stu-id="aa776-143">0</span></span> | <span data-ttu-id="aa776-144">La prima stringa e la seconda stringa sono uguali, oppure sono entrambe `null`.</span><span class="sxs-lookup"><span data-stu-id="aa776-144">The first string and the second string are equal, or both strings are `null`.</span></span>
<span data-ttu-id="aa776-145">Un intero positivo, o 1</span><span class="sxs-lookup"><span data-stu-id="aa776-145">A positive integer, or 1</span></span> | <span data-ttu-id="aa776-146">La prima stringa segue la seconda stringa nella sequenza di ordinamento, oppure la seconda stringa è Null.</span><span class="sxs-lookup"><span data-stu-id="aa776-146">The first string follows the second string in the sort order, or the second string is null.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="aa776-147">Il metodo [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) è destinato principalmente a essere usato quando si ordinano le stringhe.</span><span class="sxs-lookup"><span data-stu-id="aa776-147">The [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="aa776-148">Non usare il metodo [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) per verificare l'uguaglianza, ovvero, per cercare in modo esplicito un valore restituito pari a 0 senza considerare se una stringa è minore o maggiore dell'altra.</span><span class="sxs-lookup"><span data-stu-id="aa776-148">You should not use the [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="aa776-149">Per determinare se due stringhe sono uguali, usare invece il metodo [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).</span><span class="sxs-lookup"><span data-stu-id="aa776-149">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="aa776-150">L'esempio seguente usa il metodo [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) per determinare i valori relativi di due stringhe.</span><span class="sxs-lookup"><span data-stu-id="aa776-150">The following example uses the [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to determine the relative values of two strings.</span></span>

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.Compare(string1, "Hello World?"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.Compare(string1, "Hello World?"))
```

<span data-ttu-id="aa776-151">L'esempio visualizza `-1` nella console.</span><span class="sxs-lookup"><span data-stu-id="aa776-151">This example displays `-1` to the console.</span></span>

## <a name="compareordinal"></a><span data-ttu-id="aa776-152">CompareOrdinal</span><span class="sxs-lookup"><span data-stu-id="aa776-152">CompareOrdinal</span></span>

<span data-ttu-id="aa776-153">Il metodo [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) confronta due oggetti stringa senza considerare le impostazioni cultura locali.</span><span class="sxs-lookup"><span data-stu-id="aa776-153">The [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method compares two string objects without considering the local culture.</span></span> <span data-ttu-id="aa776-154">I valori restituiti da questo metodo sono identici a quelli restituiti dal metodo `Compare` nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="aa776-154">The return values of this method are identical to the values returned by the `Compare` method in the previous table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa776-155">Il metodo [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) è destinato principalmente a essere usato quando si ordinano le stringhe.</span><span class="sxs-lookup"><span data-stu-id="aa776-155">The [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="aa776-156">Non usare il metodo [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) per verificare l'uguaglianza, ovvero per cercare in modo esplicito un valore restituito pari a 0 senza considerare se una stringa è minore o maggiore dell'altra.</span><span class="sxs-lookup"><span data-stu-id="aa776-156">You should not use the [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="aa776-157">Per determinare se due stringhe sono uguali, usare invece il metodo [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).</span><span class="sxs-lookup"><span data-stu-id="aa776-157">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="aa776-158">L'esempio seguente usa il metodo `CompareOrdinal` per confrontare i valori di due stringhe.</span><span class="sxs-lookup"><span data-stu-id="aa776-158">The following example uses the `CompareOrdinal` method to compare the values of two strings.</span></span>

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"))
```

<span data-ttu-id="aa776-159">L'esempio visualizza `-32` nella console.</span><span class="sxs-lookup"><span data-stu-id="aa776-159">This example displays `-32` to the console.</span></span>

## <a name="compareto"></a><span data-ttu-id="aa776-160">CompareTo</span><span class="sxs-lookup"><span data-stu-id="aa776-160">CompareTo</span></span>

<span data-ttu-id="aa776-161">Il metodo [String.CompareTo](xref:System.String.CompareTo(System.String)) confronta la stringa incapsulata dall'oggetto stringa corrente con un altro oggetto o stringa.</span><span class="sxs-lookup"><span data-stu-id="aa776-161">The [String.CompareTo](xref:System.String.CompareTo(System.String)) method compares the string that the current string object encapsulates to another string or object.</span></span> <span data-ttu-id="aa776-162">I valori restituiti da questo metodo sono identici a quelli restituiti dal metodo `String.Compare` nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="aa776-162">The return values of this method are identical to the values returned by the `String.Compare` method in the previous table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa776-163">Il metodo [String.CompareTo](xref:System.String.CompareTo(System.String)) è destinato principalmente a essere usato quando si ordinano le stringhe.</span><span class="sxs-lookup"><span data-stu-id="aa776-163">The [String.CompareTo](xref:System.String.CompareTo(System.String)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="aa776-164">Non usare il metodo [String.CompareTo](xref:System.String.CompareTo(System.String)) per verificare l'uguaglianza, ovvero per cercare in modo esplicito un valore restituito pari a 0 senza considerare se una stringa è minore o maggiore dell'altra.</span><span class="sxs-lookup"><span data-stu-id="aa776-164">You should not use the [String.CompareTo](xref:System.String.CompareTo(System.String)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="aa776-165">Per determinare se due stringhe sono uguali, usare invece il metodo [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).</span><span class="sxs-lookup"><span data-stu-id="aa776-165">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="aa776-166">L'esempio seguente usa il metodo `String.CompareTo` per confrontare l'oggetto `string1` con l'oggetto `string2`.</span><span class="sxs-lookup"><span data-stu-id="aa776-166">The following example uses the `String.CompareTo` method to compare the `string1` object to the `string2` object.</span></span>

```csharp
string string1 = "Hello World";
string string2 = "Hello World!";
int MyInt = string1.CompareTo(string2);
Console.WriteLine( MyInt );
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World!"
Dim MyInt As Integer = string1.CompareTo(string2)
Console.WriteLine(MyInt)
```

<span data-ttu-id="aa776-167">L'esempio visualizza `-1` nella console.</span><span class="sxs-lookup"><span data-stu-id="aa776-167">This example displays `-1` to the console.</span></span>

## <a name="equals"></a><span data-ttu-id="aa776-168">Equals</span><span class="sxs-lookup"><span data-stu-id="aa776-168">Equals</span></span>

<span data-ttu-id="aa776-169">Il metodo [String.Equals](xref:System.String.CompareTo(System.String)) consente di determinare in modo semplice se due stringhe sono uguali.</span><span class="sxs-lookup"><span data-stu-id="aa776-169">The [String.Equals](xref:System.String.CompareTo(System.String)) method can easily determine if two strings are the same.</span></span> <span data-ttu-id="aa776-170">Questo metodo, che fa distinzione tra maiuscole e minuscole, restituisce un valore booleano `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="aa776-170">This case-sensitive method returns a `true` or `false` Boolean value.</span></span> <span data-ttu-id="aa776-171">Può essere usato da una classe esistente, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="aa776-171">It can be used from an existing class, as illustrated in the next example.</span></span> <span data-ttu-id="aa776-172">L'esempio seguente usa il metodo `Equals` per determinare se un oggetto stringa contiene la frase "Hello World".</span><span class="sxs-lookup"><span data-stu-id="aa776-172">The following example uses the `Equals` method to determine whether a string object contains the phrase "Hello World".</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.Equals("Hello World"));
```

```vb
Dim string1 As String = "Hello World"
Console.WriteLine(string1.Equals("Hello World"))
```

<span data-ttu-id="aa776-173">L'esempio visualizza `true` nella console.</span><span class="sxs-lookup"><span data-stu-id="aa776-173">This example displays `true` to the console.</span></span>

<span data-ttu-id="aa776-174">Questo metodo può anche essere usato come metodo statico.</span><span class="sxs-lookup"><span data-stu-id="aa776-174">This method can also be used as a static method.</span></span> <span data-ttu-id="aa776-175">L'esempio seguente confronta due oggetti stringa tramite un metodo statico.</span><span class="sxs-lookup"><span data-stu-id="aa776-175">The following example compares two string objects using a static method.</span></span>

```csharp
string string1 = "Hello World";
string string2 = "Hello World";
Console.WriteLine(String.Equals(string1, string2));
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World"
Console.WriteLine(String.Equals(string1, string2))
```

<span data-ttu-id="aa776-176">L'esempio visualizza `true` nella console.</span><span class="sxs-lookup"><span data-stu-id="aa776-176">This example displays `true` to the console.</span></span>

## <a name="startswith-and-endswith"></a><span data-ttu-id="aa776-177">StartsWith ed EndsWith</span><span class="sxs-lookup"><span data-stu-id="aa776-177">StartsWith and EndsWith</span></span>

<span data-ttu-id="aa776-178">È possibile usare il metodo [String.StartsWith](xref:System.String.StartsWith(System.String)) per determinare se un oggetto stringa inizia con gli stessi caratteri inclusi in un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="aa776-178">You can use the [String.StartsWith](xref:System.String.StartsWith(System.String)) method to determine whether a string object begins with the same characters that encompass another string.</span></span> <span data-ttu-id="aa776-179">Questo metodo, che fa distinzione tra maiuscole e minuscole, restituisce `true` se l'oggetto stringa corrente inizia con la stringa passata e `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="aa776-179">This case-sensitive method returns `true` if the current string object begins with the passed string and `false` if it does not.</span></span> <span data-ttu-id="aa776-180">L'esempio seguente usa questo metodo per determinare se un oggetto stringa inizia con "Hello".</span><span class="sxs-lookup"><span data-stu-id="aa776-180">The following example uses this method to determine if a string object begins with "Hello".</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.StartsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.StartsWith("Hello"))
```

<span data-ttu-id="aa776-181">L'esempio visualizza `true` nella console.</span><span class="sxs-lookup"><span data-stu-id="aa776-181">This example displays `true` to the console.</span></span>

<span data-ttu-id="aa776-182">Il metodo [String.EndsWith](xref:System.String.CompareTo(System.String)) confronta una stringa passata con i caratteri presenti alla fine dell'oggetto stringa corrente.</span><span class="sxs-lookup"><span data-stu-id="aa776-182">The [String.EndsWith](xref:System.String.CompareTo(System.String)) method compares a passed string to the characters that exist at the end of the current string object.</span></span> <span data-ttu-id="aa776-183">Anch'esso restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="aa776-183">It also returns a Boolean value.</span></span> <span data-ttu-id="aa776-184">L'esempio seguente verifica la fine di una stringa usando il metodo `EndsWith`.</span><span class="sxs-lookup"><span data-stu-id="aa776-184">The following example checks the end of a string using the `EndsWith` method.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.EndsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.EndsWith("Hello"))
```

<span data-ttu-id="aa776-185">L'esempio visualizza `false` nella console.</span><span class="sxs-lookup"><span data-stu-id="aa776-185">This example displays `false` to the console.</span></span>

## <a name="indexof-and-lastindexof"></a><span data-ttu-id="aa776-186">IndexOf e LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="aa776-186">IndexOf and LastIndexOf</span></span>

<span data-ttu-id="aa776-187">È possibile usare il metodo [String.IndexOf](xref:System.String.IndexOf(System.Char)) per determinare la posizione della prima occorrenza di un carattere specifico all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="aa776-187">You can use the [String.IndexOf](xref:System.String.IndexOf(System.Char)) method to determine the position of the first occurrence of a particular character within a string.</span></span> <span data-ttu-id="aa776-188">Questo metodo, che fa distinzione tra maiuscole e minuscole, inizia il conteggio dall'inizio di una stringa e restituisce la posizione di un carattere passato usando un indice in base zero.</span><span class="sxs-lookup"><span data-stu-id="aa776-188">This case-sensitive method starts counting from the beginning of a string and returns the position of a passed character using a zero-based index.</span></span> <span data-ttu-id="aa776-189">Se il carattere non viene trovato, viene restituito un valore -1.</span><span class="sxs-lookup"><span data-stu-id="aa776-189">If the character cannot be found, a value of –1 is returned.</span></span>

<span data-ttu-id="aa776-190">L'esempio seguente usa il metodo `IndexOf` per cercare la prima occorrenza del carattere "`l`" in una stringa.</span><span class="sxs-lookup"><span data-stu-id="aa776-190">The following example uses the `IndexOf` method to search for the first occurrence of the '`l`' character in a string.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.IndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.IndexOf("l"))
```

<span data-ttu-id="aa776-191">L'esempio visualizza `2` nella console.</span><span class="sxs-lookup"><span data-stu-id="aa776-191">This example displays `2` to the console.</span></span>

<span data-ttu-id="aa776-192">Il metodo [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) è simile al metodo `String.IndexOf`, con la differenza che restituisce la posizione dell'ultima occorrenza di un carattere specifico all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="aa776-192">The [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) method is similar to the `String.IndexOf` method except that it returns the position of the last occurrence of a particular character within a string.</span></span> <span data-ttu-id="aa776-193">Anch'esso fa distinzione tra maiuscole e minuscole e usa un indice in base zero.</span><span class="sxs-lookup"><span data-stu-id="aa776-193">It is case-sensitive and uses a zero-based index.</span></span> 

<span data-ttu-id="aa776-194">L'esempio seguente usa il metodo `LastIndexOf` per cercare l'ultima occorrenza del carattere "`l`" in una stringa.</span><span class="sxs-lookup"><span data-stu-id="aa776-194">The following example uses the `LastIndexOf` method to search for the last occurrence of the '`l`' character in a string.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.LastIndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.LastIndexOf("l"))
```

<span data-ttu-id="aa776-195">L'esempio visualizza `9` nella console.</span><span class="sxs-lookup"><span data-stu-id="aa776-195">This example displays `9` to the console.</span></span>

<span data-ttu-id="aa776-196">Entrambi i metodi sono utili quando vengono usati in combinazione con il metodo [String.Remove](xref:System.String.Remove(System.Int32)).</span><span class="sxs-lookup"><span data-stu-id="aa776-196">Both methods are useful when used in conjunction with the [String.Remove](xref:System.String.Remove(System.Int32)) method.</span></span> <span data-ttu-id="aa776-197">È possibile usare il metodo `IndexOf` o `LastIndexOf` per recuperare la posizione di un carattere e quindi specificare tale posizione nel metodo `Remove method` per rimuovere un carattere o una parola che inizia con tale carattere.</span><span class="sxs-lookup"><span data-stu-id="aa776-197">You can use either the `IndexOf` or `LastIndexOf` methods to retrieve the position of a character, and then supply that position to the `Remove method` in order to remove a character or a word that begins with that character.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa776-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa776-198">See Also</span></span>

[<span data-ttu-id="aa776-199">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="aa776-199">Basic string operations</span></span>](basic-string-operations.md)













