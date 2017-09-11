---
title: Uso della classe StringBuilder
description: Uso della classe StringBuilder
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: f4f5d1c7-d84d-4867-810f-2708cd6de0da
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 076e10e095b50cc96187f2ec13ade2365d83dad3
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="using-the-stringbuilder-class"></a><span data-ttu-id="569fe-104">Uso della classe StringBuilder</span><span class="sxs-lookup"><span data-stu-id="569fe-104">Using the StringBuilder class</span></span>

<span data-ttu-id="569fe-105">L'oggetto [String](xref:System.String) non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="569fe-105">The [String](xref:System.String) object is immutable.</span></span> <span data-ttu-id="569fe-106">Ogni volta che si usa uno dei metodi nella classe [System.String](xref:System.String), si crea un nuovo oggetto stringa in memoria che richiede una nuova allocazione di spazio.</span><span class="sxs-lookup"><span data-stu-id="569fe-106">Every time you use one of the methods in the [System.String](xref:System.String) class, you create a new string object in memory, which requires a new allocation of space for that new object.</span></span> <span data-ttu-id="569fe-107">In situazioni in cui è necessario modificare ripetutamente una stringa, il sovraccarico associato alla creazione di un nuovo oggetto [String](xref:System.String) può essere dispendioso.</span><span class="sxs-lookup"><span data-stu-id="569fe-107">In situations where you need to perform repeated modifications to a string, the overhead associated with creating a new [String](xref:System.String) object can be costly.</span></span> <span data-ttu-id="569fe-108">La classe [System.Text.StringBuilder](xref:System.Text.StringBuilder) può essere usata per modificare una stringa senza creare un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="569fe-108">The [System.Text.StringBuilder](xref:System.Text.StringBuilder) class can be used when you want to modify a string without creating a new object.</span></span> <span data-ttu-id="569fe-109">Ad esempio, l'uso della classe [StringBuilder](xref:System.Text.StringBuilder) può migliorare le prestazioni quando si concatenano più stringhe in un ciclo.</span><span class="sxs-lookup"><span data-stu-id="569fe-109">For example, using the [StringBuilder](xref:System.Text.StringBuilder) class can boost performance when concatenating many strings together in a loop.</span></span>

## <a name="importing-the-systemtext-namespace"></a><span data-ttu-id="569fe-110">Importazione dello spazio dei nomi System.Type</span><span class="sxs-lookup"><span data-stu-id="569fe-110">Importing the System.Text Namespace</span></span>

<span data-ttu-id="569fe-111">La classe [StringBuilder](xref:System.Text.StringBuilder) si trova nello spazio dei nomi [System.Text](xref:System.Text).</span><span class="sxs-lookup"><span data-stu-id="569fe-111">The [StringBuilder](xref:System.Text.StringBuilder) class is found in the [System.Text](xref:System.Text) namespace.</span></span> <span data-ttu-id="569fe-112">Per evitare di specificare il nome di tipo completo nel codice, è possibile importare lo spazio dei nomi [System.Text](xref:System.Text):</span><span class="sxs-lookup"><span data-stu-id="569fe-112">To avoid having to provide a fully qualified type name in your code, you can import the [System.Text](xref:System.Text) namespace:</span></span> 

```csharp
using System;
using System.Text;
```

```vb
Imports System.Text
```

## <a name="instantiating-a-stringbuilder-object"></a><span data-ttu-id="569fe-113">Creazione di un'istanza di un oggetto StringBuilder</span><span class="sxs-lookup"><span data-stu-id="569fe-113">Instantiating a StringBuilder Object</span></span>

<span data-ttu-id="569fe-114">È possibile creare una nuova istanza della classe [StringBuilder](xref:System.Text.StringBuilder) inizializzando la variabile con uno dei metodi del costruttore di overload, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="569fe-114">You can create a new instance of the [StringBuilder](xref:System.Text.StringBuilder) class by initializing your variable with one of the overloaded constructor methods, as illustrated in the following example.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
```

## <a name="setting-the-capacity-and-length"></a><span data-ttu-id="569fe-115">Impostazione di capacità e lunghezza</span><span class="sxs-lookup"><span data-stu-id="569fe-115">Setting the Capacity and Length</span></span>

<span data-ttu-id="569fe-116">Anche se [StringBuilder](xref:System.Text.StringBuilder) è un oggetto dinamico che consente di espandere il numero di caratteri nella stringa incapsulata, è possibile specificare un valore per il numero massimo di caratteri che può contenere.</span><span class="sxs-lookup"><span data-stu-id="569fe-116">Although the [StringBuilder](xref:System.Text.StringBuilder) is a dynamic object that allows you to expand the number of characters in the string that it encapsulates, you can specify a value for the maximum number of characters that it can hold.</span></span> <span data-ttu-id="569fe-117">Questo valore rappresenta la capacità dell'oggetto e non deve essere confuso con la lunghezza della stringa contenuta dall'oggetto [StringBuilder](xref:System.Text.StringBuilder) corrente.</span><span class="sxs-lookup"><span data-stu-id="569fe-117">This value is called the capacity of the object and should not be confused with the length of the string that the current [StringBuilder](xref:System.Text.StringBuilder) holds.</span></span> <span data-ttu-id="569fe-118">Ad esempio, è possibile creare una nuova istanza della classe [StringBuilder](xref:System.Text.StringBuilder) con la stringa "Hello", che ha una lunghezza pari a 5 caratteri, e specificare che l'oggetto ha una capacità massima di 25 caratteri.</span><span class="sxs-lookup"><span data-stu-id="569fe-118">For example, you might create a new instance of the [StringBuilder](xref:System.Text.StringBuilder) class with the string "Hello", which has a length of 5, and you might specify that the object has a maximum capacity of 25.</span></span> <span data-ttu-id="569fe-119">Quando si modifica la classe [StringBuilder](xref:System.Text.StringBuilder), le dimensioni non vengono riallocate automaticamente fino a quando non viene raggiunta la capacità specificata.</span><span class="sxs-lookup"><span data-stu-id="569fe-119">When you modify the [StringBuilder](xref:System.Text.StringBuilder), it does not reallocate size for itself until the capacity is reached.</span></span> <span data-ttu-id="569fe-120">In questo caso, il nuovo spazio viene allocato automaticamente e la capacità viene raddoppiata.</span><span class="sxs-lookup"><span data-stu-id="569fe-120">When this occurs, the new space is allocated automatically and the capacity is doubled.</span></span> <span data-ttu-id="569fe-121">È possibile specificare la capacità della classe [StringBuilder](xref:System.Text.StringBuilder) usando uno dei costruttori di overload.</span><span class="sxs-lookup"><span data-stu-id="569fe-121">You can specify the capacity of the [StringBuilder](xref:System.Text.StringBuilder) class using one of the overloaded constructors.</span></span> <span data-ttu-id="569fe-122">L'esempio seguente specifica che l'oggetto `MyStringBuilder` può essere espanso fino a un massimo di 25 spazi.</span><span class="sxs-lookup"><span data-stu-id="569fe-122">The following example specifies that the `MyStringBuilder` object can be expanded to a maximum of 25 spaces.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!", 25);
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!", 25) 
```

<span data-ttu-id="569fe-123">È anche possibile usare la proprietà [Capacity](xref:System.Text.StringBuilder.Capacity) di lettura/scrittura per impostare la lunghezza massima dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="569fe-123">Additionally, you can use the read/write [Capacity](xref:System.Text.StringBuilder.Capacity) property to set the maximum length of your object.</span></span> <span data-ttu-id="569fe-124">L'esempio seguente usa la proprietà [Capacity](xref:System.Text.StringBuilder.Capacity) per definire la lunghezza massima dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="569fe-124">The following example uses the [Capacity](xref:System.Text.StringBuilder.Capacity) property to define the maximum object length.</span></span>

```csharp
MyStringBuilder.Capacity = 25;
```

```vb
MyStringBuilder.Capacity = 25
```

<span data-ttu-id="569fe-125">Il metodo [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)) può essere usato per verificare la capacità dell'oggetto [StringBuilder](xref:System.Text.StringBuilder) corrente.</span><span class="sxs-lookup"><span data-stu-id="569fe-125">The [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)) method can be used to check the capacity of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="569fe-126">Se la capacità è maggiore del valore passato, non vengono apportate modifiche. Invece, se la capacità è minore del valore passato, la capacità corrente viene modificata in modo che corrisponda al valore passato.</span><span class="sxs-lookup"><span data-stu-id="569fe-126">If the capacity is greater than the passed value, no change is made; however, if the capacity is smaller than the passed value, the current capacity is changed to match the passed value.</span></span>

<span data-ttu-id="569fe-127">La proprietà [Length](xref:System.Text.StringBuilder.Length) può essere anche visualizzata o impostata.</span><span class="sxs-lookup"><span data-stu-id="569fe-127">The [Length](xref:System.Text.StringBuilder.Length) property can also be viewed or set.</span></span> <span data-ttu-id="569fe-128">Se si imposta la proprietà [Length](xref:System.Text.StringBuilder.Length) su un valore maggiore della proprietà [Capacity](xref:System.Text.StringBuilder.Capacity), la proprietà [Capacity](xref:System.Text.StringBuilder.Capacity) viene impostata automaticamente sullo stesso valore della proprietà [Length](xref:System.Text.StringBuilder.Length).</span><span class="sxs-lookup"><span data-stu-id="569fe-128">If you set the [Length](xref:System.Text.StringBuilder.Length) property to a value that is greater than the [Capacity](xref:System.Text.StringBuilder.Capacity) property, the [Capacity](xref:System.Text.StringBuilder.Capacity) property is automatically changed to the same value as the [Length](xref:System.Text.StringBuilder.Length) property.</span></span> <span data-ttu-id="569fe-129">L'impostazione della proprietà [Length](xref:System.Text.StringBuilder.Length) su un valore minore della lunghezza della stringa all'interno dell'oggetto [StringBuilder](xref:System.Text.StringBuilder) corrente consente di abbreviare la stringa.</span><span class="sxs-lookup"><span data-stu-id="569fe-129">Setting the [Length](xref:System.Text.StringBuilder.Length) property to a value that is less than the length of the string within the current [StringBuilder](xref:System.Text.StringBuilder) shortens the string.</span></span>

## <a name="modifying-the-stringbuilder-string"></a><span data-ttu-id="569fe-130">Modifica della stringa StringBuilder</span><span class="sxs-lookup"><span data-stu-id="569fe-130">Modifying the StringBuilder String</span></span>

<span data-ttu-id="569fe-131">La tabella seguente elenca i metodi che è possibile usare per modificare il contenuto di [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="569fe-131">The following table lists the methods you can use to modify the contents of a [StringBuilder](xref:System.Text.StringBuilder).</span></span>

<span data-ttu-id="569fe-132">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="569fe-132">Method name</span></span> | <span data-ttu-id="569fe-133">Uso</span><span class="sxs-lookup"><span data-stu-id="569fe-133">Use</span></span>
----------- | ---
<span data-ttu-id="569fe-134">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))</span><span class="sxs-lookup"><span data-stu-id="569fe-134">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))</span></span> | <span data-ttu-id="569fe-135">Aggiunge informazioni alla fine dell'oggetto [StringBuilder](xref:System.Text.StringBuilder) corrente.</span><span class="sxs-lookup"><span data-stu-id="569fe-135">Appends information to the end of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="569fe-136">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="569fe-136">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span></span> | <span data-ttu-id="569fe-137">Sostituisce un identificatore di formato passato in una stringa con il testo formattato.</span><span class="sxs-lookup"><span data-stu-id="569fe-137">Replaces a format specifier passed in a string with formatted text.</span></span>
<span data-ttu-id="569fe-138">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))</span><span class="sxs-lookup"><span data-stu-id="569fe-138">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))</span></span> | <span data-ttu-id="569fe-139">Inserisce una stringa o un oggetto nell'indice specificato dell'oggetto [StringBuilder](xref:System.Text.StringBuilder) corrente.</span><span class="sxs-lookup"><span data-stu-id="569fe-139">Inserts a string or object into the specified index of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="569fe-140">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="569fe-140">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))</span></span> | <span data-ttu-id="569fe-141">Rimuove un numero specificato di caratteri dall'oggetto [StringBuilder](xref:System.Text.StringBuilder) corrente.</span><span class="sxs-lookup"><span data-stu-id="569fe-141">Removes a specified number of characters from the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="569fe-142">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))</span><span class="sxs-lookup"><span data-stu-id="569fe-142">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))</span></span> | <span data-ttu-id="569fe-143">Sostituisce un determinato carattere nell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="569fe-143">Replaces a specified character at a specified index.</span></span>

### <a name="append"></a><span data-ttu-id="569fe-144">Aggiungi</span><span class="sxs-lookup"><span data-stu-id="569fe-144">Append</span></span>

<span data-ttu-id="569fe-145">Il metodo [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) può essere usato per aggiungere testo o una rappresentazione di stringa di un oggetto alla fine di una stringa rappresentata dall'oggetto [StringBuilder](xref:System.Text.StringBuilder) corrente.</span><span class="sxs-lookup"><span data-stu-id="569fe-145">The [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) method can be used to add text or a string representation of an object to the end of a string represented by the current [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="569fe-146">Nell'esempio seguente viene inizializzato un oggetto [StringBuilder](xref:System.Text.StringBuilder) su "Hello World" e quindi viene aggiunto il testo alla fine dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="569fe-146">The following example initializes a [StringBuilder](xref:System.Text.StringBuilder) to "Hello World" and then appends some text to the end of the object.</span></span> <span data-ttu-id="569fe-147">Lo spazio viene allocato automaticamente in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="569fe-147">Space is allocated automatically as needed.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Append(" What a beautiful day.");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World! What a beautiful day.
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Append(" What a beautiful day.")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World! What a beautiful day.
```

### <a name="appendformat"></a><span data-ttu-id="569fe-148">AppendFormat</span><span class="sxs-lookup"><span data-stu-id="569fe-148">AppendFormat</span></span>

<span data-ttu-id="569fe-149">Il metodo [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) aggiunge del testo alla fine dell'oggetto [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="569fe-149">The [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) method adds text to the end of the [StringBuilder](xref:System.Text.StringBuilder) object.</span></span> <span data-ttu-id="569fe-150">Supporta la funzionalità di formattazione composita (per altre informazioni, vedere [Formattazione composita](composite-format.md)) chiamando l'implementazione [IFormattable](xref:System.IFormattable) dell'oggetto o gli oggetti da formattare.</span><span class="sxs-lookup"><span data-stu-id="569fe-150">It supports the composite formatting feature (for more information, see [Composite Formatting](composite-format.md)) by calling the [IFormattable](xref:System.IFormattable) implementation of the object or objects to be formatted.</span></span> <span data-ttu-id="569fe-151">Pertanto, accetta le stringhe di formato standard per i valori numerici, di data e ora e di enumerazione, le stringhe di formato personalizzato per i valori numerici e di data e ora e le stringhe di formato definite per i tipi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="569fe-151">Therefore, it accepts the standard format strings for numeric, date and time, and enumeration values, the custom format strings for numeric and date and time values, and the format strings defined for custom types.</span></span> <span data-ttu-id="569fe-152">Per informazioni sulla formattazione, vedere [Formattazione di tipi](formatting-types.md)). È possibile usare questo metodo per personalizzare il formato delle variabili e aggiungere tali valori a un oggetto [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="569fe-152">(For information about formatting, see [Formatting Types](formatting-types.md).) You can use this method to customize the format of variables and append those values to a [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="569fe-153">L'esempio seguente usa il metodo AppendFormat per inserire un valore intero formattato come valore di valuta alla fine di un oggetto [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="569fe-153">The following example uses the AppendFormat method to place an integer value formatted as a currency value at the end of a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
int MyInt = 25; 
StringBuilder MyStringBuilder = new StringBuilder("Your total is ");
MyStringBuilder.AppendFormat("{0:C} ", MyInt);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Your total is $25.00
```

```vb
Dim MyInt As Integer = 25
Dim MyStringBuilder As New StringBuilder("Your total is ")
MyStringBuilder.AppendFormat("{0:C} ", MyInt)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'     Your total is $25.00 
```

### <a name="insert"></a><span data-ttu-id="569fe-154">INS</span><span class="sxs-lookup"><span data-stu-id="569fe-154">Insert</span></span>

<span data-ttu-id="569fe-155">Il metodo [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) aggiunge una stringa o un oggetto in una posizione specificata nell'oggetto [StringBuilder](xref:System.Text.StringBuilder) corrente.</span><span class="sxs-lookup"><span data-stu-id="569fe-155">The [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) method adds a string or object to a specified position in the current [StringBuilder](xref:System.Text.StringBuilder) object.</span></span> <span data-ttu-id="569fe-156">L'esempio seguente usa questo metodo per inserire una parola nella sesta posizione di un oggetto [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="569fe-156">The following example uses this method to insert a word into the sixth position of a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Insert(6,"Beautiful ");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello Beautiful World!
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Insert(6, "Beautiful ")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'      Hello Beautiful World!
```

### <a name="remove"></a><span data-ttu-id="569fe-157">Rimuovi</span><span class="sxs-lookup"><span data-stu-id="569fe-157">Remove</span></span>

<span data-ttu-id="569fe-158">È possibile usare il metodo [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) per rimuovere un numero specificato di caratteri dall'oggetto [StringBuilder](xref:System.Text.StringBuilder) corrente, a partire dall'indice in base zero specificato.</span><span class="sxs-lookup"><span data-stu-id="569fe-158">You can use the [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) method to remove a specified number of characters from the current [StringBuilder](xref:System.Text.StringBuilder) object, beginning at a specified zero-based index.</span></span> <span data-ttu-id="569fe-159">L'esempio seguente usa il metodo [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) per abbreviare un oggetto [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="569fe-159">The following example uses the [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) method to shorten a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Remove(5,7);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Remove(5, 7)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello
```

### <a name="replace"></a><span data-ttu-id="569fe-160">Sostituisci</span><span class="sxs-lookup"><span data-stu-id="569fe-160">Replace</span></span>

<span data-ttu-id="569fe-161">Il metodo [StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) |Sostituisce un determinato carattere nell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="569fe-161">The [StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Replaces a specified character at a specified index.</span></span>
<span data-ttu-id="569fe-162">può essere usato per sostituire i caratteri all'interno dell'oggetto [StringBuilder](xref:System.Text.StringBuilder) con un altro carattere specificato.</span><span class="sxs-lookup"><span data-stu-id="569fe-162">method can be used to replace characters within the [StringBuilder](xref:System.Text.StringBuilder) object with another specified character.</span></span> <span data-ttu-id="569fe-163">Nell'esempio seguente viene usato il metodo [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) |Sostituisce un determinato carattere nell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="569fe-163">The following example uses the [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Replaces a specified character at a specified index.</span></span>
<span data-ttu-id="569fe-164">per cercare un oggetto [StringBuilder](xref:System.Text.StringBuilder) per tutte le istanze del carattere punto esclamativo (!) e sostituirle con il carattere punto interrogativo (?).</span><span class="sxs-lookup"><span data-stu-id="569fe-164">method to search a [StringBuilder](xref:System.Text.StringBuilder) object for all instances of the exclamation point character (!) and replace them with the question mark character (?).</span></span>
 
 ```csharp
 StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Replace('!', '?');
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World?
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Replace("!"c, "?"c)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World?
```

## <a name="converting-a-stringbuilder-object-to-a-string"></a><span data-ttu-id="569fe-165">Conversione di un oggetto StringBuilder in una stringa</span><span class="sxs-lookup"><span data-stu-id="569fe-165">Converting a StringBuilder Object to a String</span></span>

<span data-ttu-id="569fe-166">È necessario convertire l'oggetto [StringBuilder](xref:System.Text.StringBuilder) in un oggetto [String](xref:System.String) prima di poter passare la stringa rappresentata dall'oggetto [StringBuilder](xref:System.Text.StringBuilder) a un metodo che contiene un parametro [String](xref:System.String) o per visualizzarlo nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="569fe-166">You must convert the [StringBuilder](xref:System.Text.StringBuilder) object to a [String](xref:System.String) object before you can pass the string represented by the [StringBuilder](xref:System.Text.StringBuilder) object to a method that has a [String](xref:System.String) parameter or display it in the user interface.</span></span> <span data-ttu-id="569fe-167">Eseguire questa conversione chiamando il metodo [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString).</span><span class="sxs-lookup"><span data-stu-id="569fe-167">You do this conversion by calling the [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) method.</span></span> <span data-ttu-id="569fe-168">Nell'esempio seguente vengono chiamati diversi metodi [StringBuilder](xref:System.Text.StringBuilder) e quindi viene chiamato il metodo [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) per visualizzare la stringa.</span><span class="sxs-lookup"><span data-stu-id="569fe-168">The following example calls a number of [StringBuilder](xref:System.Text.StringBuilder) methods and then calls the [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) method to display the string.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      StringBuilder sb = new StringBuilder();
      bool flag = true;
      string[] spellings = { "recieve", "receeve", "receive" };
      sb.AppendFormat("Which of the following spellings is {0}:", flag);
      sb.AppendLine();
      for (int ctr = 0; ctr <= spellings.GetUpperBound(0); ctr++) {
         sb.AppendFormat("   {0}. {1}", ctr, spellings[ctr]);
         sb.AppendLine();
      }
      sb.AppendLine();
      Console.WriteLine(sb.ToString());
   }
}
// The example displays the following output:
//       Which of the following spellings is True:
//          0. recieve
//          1. receeve
//          2. receive
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim sb As New StringBuilder()
      Dim flag As Boolean = True
      Dim spellings() As String = { "recieve", "receeve", "receive" }
      sb.AppendFormat("Which of the following spellings is {0}:", flag)
      sb.AppendLine()
      For ctr As Integer = 0 To spellings.GetUpperBound(0)
         sb.AppendFormat("   {0}. {1}", ctr, spellings(ctr))
         sb.AppendLine()
      Next
      sb.AppendLine()
      Console.WriteLine(sb.ToString())
   End Sub
End Module
' The example displays the following output:
'       Which of the following spellings is True:
'          0. recieve
'          1. receeve
'          2. receive
```

## <a name="see-also"></a><span data-ttu-id="569fe-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="569fe-169">See Also</span></span>

[<span data-ttu-id="569fe-170">System.Text.StringBuilder</span><span class="sxs-lookup"><span data-stu-id="569fe-170">System.Text.StringBuilder</span></span>](xref:System.Text.StringBuilder)

[<span data-ttu-id="569fe-171">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="569fe-171">Basic string operations</span></span>](basic-string-operations.md)

[<span data-ttu-id="569fe-172">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="569fe-172">Formatting types</span></span>](formatting-types.md)

