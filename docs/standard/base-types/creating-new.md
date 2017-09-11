---
title: Creazione di nuove stringhe
description: Creazione di nuove stringhe
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 639397c7-e694-43e0-845b-1681c62bd9fd
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 793b5bc4b26967104459fa2559c6127bb82f3a9d
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="creating-new-strings"></a><span data-ttu-id="41cc7-104">Creazione di nuove stringhe</span><span class="sxs-lookup"><span data-stu-id="41cc7-104">Creating new strings</span></span>

<span data-ttu-id="41cc7-105">.NET consente di creare stringhe tramite una semplice assegnazione, oltre a eseguire l'overload del costruttore di classe per supportare la creazione di stringhe tramite una serie di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="41cc7-105">.NET  allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="41cc7-106">Nella classe [System.String](xref:System.String) .NET Framework fornisce anche diversi metodi per creare nuovi oggetti stringa tramite la combinazione di più stringhe, matrici di stringhe o oggetti.</span><span class="sxs-lookup"><span data-stu-id="41cc7-106">.NET also provides several methods in the [System.String](xref:System.String) class that create new string objects by combining several strings, arrays of strings, or objects.</span></span> 

## <a name="creating-strings-using-assignment"></a><span data-ttu-id="41cc7-107">Creazione di stringhe tramite assegnazione</span><span class="sxs-lookup"><span data-stu-id="41cc7-107">Creating Strings Using Assignment</span></span>

<span data-ttu-id="41cc7-108">Il modo più semplice per creare un nuovo oggetto [String](xref:System.String) consiste nell'assegnare un valore letterale stringa a un oggetto [String](xref:System.String).</span><span class="sxs-lookup"><span data-stu-id="41cc7-108">The easiest way to create a new [String](xref:System.String) object is simply to assign a string literal to a [String](xref:System.String) object.</span></span> 

## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="41cc7-109">Creazione di stringhe tramite un costruttore di classe</span><span class="sxs-lookup"><span data-stu-id="41cc7-109">Creating Strings Using a Class Constructor</span></span>

<span data-ttu-id="41cc7-110">È possibile usare overload del costruttore della classe [String](xref:System.String) per creare stringhe da matrici di caratteri.</span><span class="sxs-lookup"><span data-stu-id="41cc7-110">You can use overloads of the [String](xref:System.String) class constructor to create strings from character arrays.</span></span> <span data-ttu-id="41cc7-111">È anche possibile creare una nuova stringa duplicando un determinato carattere per un numero specifico di volte.</span><span class="sxs-lookup"><span data-stu-id="41cc7-111">You can also create a new string by duplicating a particular character a specified number of times.</span></span> 

## <a name="methods-that-return-strings"></a><span data-ttu-id="41cc7-112">Metodi che restituiscono stringhe</span><span class="sxs-lookup"><span data-stu-id="41cc7-112">Methods that Return Strings</span></span>

<span data-ttu-id="41cc7-113">Nella tabella seguente sono elencati diversi metodi utili che restituiscono nuovi oggetti stringa.</span><span class="sxs-lookup"><span data-stu-id="41cc7-113">The following table lists several useful methods that return new string objects.</span></span>

<span data-ttu-id="41cc7-114">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="41cc7-114">Method name</span></span> | <span data-ttu-id="41cc7-115">Uso</span><span class="sxs-lookup"><span data-stu-id="41cc7-115">Use</span></span>
----------- | ---
<span data-ttu-id="41cc7-116">[String.Format](xref:System.String.Format(System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="41cc7-116">[String.Format](xref:System.String.Format(System.String,System.Object))</span></span> | <span data-ttu-id="41cc7-117">Compila una stringa formattata da un insieme di oggetti di input.</span><span class="sxs-lookup"><span data-stu-id="41cc7-117">Builds a formatted string from a set of input objects.</span></span>
<span data-ttu-id="41cc7-118">[String.Concat](xref:System.String.Concat(System.String,System.String))</span><span class="sxs-lookup"><span data-stu-id="41cc7-118">[String.Concat](xref:System.String.Concat(System.String,System.String))</span></span> | <span data-ttu-id="41cc7-119">Compila stringhe da due o più stringhe.</span><span class="sxs-lookup"><span data-stu-id="41cc7-119">Builds strings from two or more strings.</span></span>
<span data-ttu-id="41cc7-120">[String.Join](xref:System.String.Join(System.String,System.String[]))</span><span class="sxs-lookup"><span data-stu-id="41cc7-120">[String.Join](xref:System.String.Join(System.String,System.String[]))</span></span> |<span data-ttu-id="41cc7-121">Compila una nuova stringa combinando una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="41cc7-121">Builds a new string by combining an array of strings.</span></span>
<span data-ttu-id="41cc7-122">[String.Insert](xref:System.String.Insert(System.Int32,System.String))</span><span class="sxs-lookup"><span data-stu-id="41cc7-122">[String.Insert](xref:System.String.Insert(System.Int32,System.String))</span></span> | <span data-ttu-id="41cc7-123">Compila una nuova stringa inserendo una stringa in corrispondenza dell'indice specificato di una stringa esistente.</span><span class="sxs-lookup"><span data-stu-id="41cc7-123">Builds a new string by inserting a string into the specified index of an existing string.</span></span>
<span data-ttu-id="41cc7-124">[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="41cc7-124">[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32))</span></span> | <span data-ttu-id="41cc7-125">Copia i caratteri specificati di una stringa in una determinata posizione all'interno di una matrice di caratteri.</span><span class="sxs-lookup"><span data-stu-id="41cc7-125">Copies specified characters in a string into a specified position in an array of characters.</span></span>

### <a name="format"></a><span data-ttu-id="41cc7-126">Formato</span><span class="sxs-lookup"><span data-stu-id="41cc7-126">Format</span></span>

<span data-ttu-id="41cc7-127">È possibile usare il metodo `String.Format` per creare stringhe formattate e concatenare stringhe che rappresentano più oggetti.</span><span class="sxs-lookup"><span data-stu-id="41cc7-127">You can use the `String.Format` method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="41cc7-128">Qualsiasi oggetto venga passato a questo metodo viene automaticamente convertito in una stringa.</span><span class="sxs-lookup"><span data-stu-id="41cc7-128">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="41cc7-129">Se, ad esempio, l'applicazione deve visualizzare un valore [Int32](xref:System.Int32) e un valore [DateTime](xref:System.DateTime), è possibile costruire con facilità una stringa che rappresenti tali valori usando il metodo `Format`.</span><span class="sxs-lookup"><span data-stu-id="41cc7-129">For example, if your application must display an [Int32](xref:System.Int32) value and a [DateTime](xref:System.DateTime) value to the user, you can easily construct a string to represent these values using the `Format` method.</span></span> <span data-ttu-id="41cc7-130">Per altre informazioni sulle convenzioni di formattazione usate con questo metodo, vedere la sezione relativa alla [formattazione composita](composite-format.md).</span><span class="sxs-lookup"><span data-stu-id="41cc7-130">For information about formatting conventions used with this method, see the section on [composite formatting](composite-format.md).</span></span>

<span data-ttu-id="41cc7-131">Nell'esempio di codice che segue il metodo `Format` viene usato per creare una stringa che usa una variabile integer.</span><span class="sxs-lookup"><span data-stu-id="41cc7-131">The following example uses the `Format` method to create a string that uses an integer variable.</span></span>

```csharp
int numberOfFleas = 12;
string miscInfo = String.Format("Your dog has {0} fleas. " +
                                "It is time to get a flea collar. " + 
                                "The current universal date is: {1:u}.", 
                                numberOfFleas, DateTime.Now);
Console.WriteLine(miscInfo);
// The example displays the following output:
//       Your dog has 12 fleas. It is time to get a flea collar. 
//       The current universal date is: 2008-03-28 13:31:40Z.
```

```vb
Dim numberOfFleas As Integer = 12
Dim miscInfo As String = String.Format("Your dog has {0} fleas. " & _
                                       "It is time to get a flea collar. " & _ 
                                       "The current universal date is: {1:u}.", _ 
                                       numberOfFleas, Date.Now)
Console.WriteLine(miscInfo)
' The example displays the following output:
'       Your dog has 12 fleas. It is time to get a flea collar. 
'       The current universal date is: 2008-03-28 13:31:40Z.
```

<span data-ttu-id="41cc7-132">In questo esempio [DateTime.Now](xref:System.DateTime.Now) visualizza l'ora e la data correnti nel modo specificato dalle impostazioni cultura associate al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="41cc7-132">In this example, [DateTime.Now](xref:System.DateTime.Now) displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>

### <a name="concat"></a><span data-ttu-id="41cc7-133">Concat</span><span class="sxs-lookup"><span data-stu-id="41cc7-133">Concat</span></span>

<span data-ttu-id="41cc7-134">Il metodo `String.Concat` può essere usato per creare facilmente un nuovo oggetto stringa da due o più oggetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="41cc7-134">The `String.Concat` method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="41cc7-135">Questo metodo rappresenta una modalità di concatenamento delle stringhe indipendente dal linguaggio.</span><span class="sxs-lookup"><span data-stu-id="41cc7-135">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="41cc7-136">Il metodo accetta qualsiasi classe che derivi da `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="41cc7-136">This method accepts any class that derives from `System.Object`.</span></span> <span data-ttu-id="41cc7-137">Nell'esempio di codice che segue viene creata una stringa da due oggetti stringa esistenti e da un carattere di separazione.</span><span class="sxs-lookup"><span data-stu-id="41cc7-137">The following example creates a string from two existing string objects and a separating character.</span></span>

```csharp
string helloString1 = "Hello";
string helloString2 = "World!";
Console.WriteLine(String.Concat(helloString1, ' ', helloString2));
// The example displays the following output:
//      Hello World!
```

```vb
Dim helloString1 As String = "Hello"
Dim helloString2 As String = "World!"
Console.WriteLine(String.Concat(helloString1, " "c, helloString2))
' The example displays the following output:
'      Hello World!
```

### <a name="join"></a><span data-ttu-id="41cc7-138">Join</span><span class="sxs-lookup"><span data-stu-id="41cc7-138">Join</span></span>

<span data-ttu-id="41cc7-139">Il metodo `String.Join` consente di creare una nuova stringa da una matrice di stringhe e da una stringa di separazione.</span><span class="sxs-lookup"><span data-stu-id="41cc7-139">The `String.Join` method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="41cc7-140">Questo metodo è utile per concatenare più stringhe, creando un elenco, eventualmente separato da virgole.</span><span class="sxs-lookup"><span data-stu-id="41cc7-140">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>

<span data-ttu-id="41cc7-141">Nell'esempio di codice seguente viene usato uno spazio per eseguire l'associazione di una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="41cc7-141">The following example uses a space to bind a string array.</span></span>

```csharp
string[] words = {"Hello", "and", "welcome", "to", "my" , "world!"};
Console.WriteLine(String.Join(" ", words));
// The example displays the following output:
//      Hello and welcome to my world!
```

```vb
Dim words() As String = {"Hello", "and", "welcome", "to", "my" , "world!"}
Console.WriteLine(String.Join(" ", words))
' The example displays the following output:
'      Hello and welcome to my world!
```

### <a name="insert"></a><span data-ttu-id="41cc7-142">INS</span><span class="sxs-lookup"><span data-stu-id="41cc7-142">Insert</span></span>

<span data-ttu-id="41cc7-143">Il metodo `String.Insert` consente di creare una nuova stringa inserendo una stringa in una posizione specificata all'interno di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="41cc7-143">The `String.Insert` method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="41cc7-144">Questo metodo usa un indice a base zero.</span><span class="sxs-lookup"><span data-stu-id="41cc7-144">This method uses a zero-based index.</span></span> <span data-ttu-id="41cc7-145">Nell'esempio di codice che segue viene inserita una stringa in corrispondenza della quinta posizione di indice di `MyString` e viene creata una nuova stringa con tale valore.</span><span class="sxs-lookup"><span data-stu-id="41cc7-145">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>

```csharp
string sentence = "Once a time.";   
 Console.WriteLine(sentence.Insert(4, " upon"));
 // The example displays the following output:
 //      Once upon a time.
```

```vb
Dim sentence As String = "Once a time."   
 Console.WriteLine(sentence.Insert(4, " upon"))
 ' The example displays the 
```

### <a name="copyto"></a><span data-ttu-id="41cc7-146">CopyTo</span><span class="sxs-lookup"><span data-stu-id="41cc7-146">CopyTo</span></span>

<span data-ttu-id="41cc7-147">Il metodo `String.CopyTo` consente di copiare parti di una stringa in una matrice di caratteri.</span><span class="sxs-lookup"><span data-stu-id="41cc7-147">The `String.CopyTo` method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="41cc7-148">È possibile specificare sia l'indice iniziale della stringa sia il numero dei caratteri da copiare.</span><span class="sxs-lookup"><span data-stu-id="41cc7-148">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="41cc7-149">Il metodo contiene l'indice di origine, una matrice di caratteri, l'indice di destinazione e il numero dei caratteri da copiare.</span><span class="sxs-lookup"><span data-stu-id="41cc7-149">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="41cc7-150">Tutti gli indici sono a base zero.</span><span class="sxs-lookup"><span data-stu-id="41cc7-150">All indexes are zero-based.</span></span>

<span data-ttu-id="41cc7-151">Nell'esempio di codice riportato di seguito il metodo `CopyTo` viene usato per copiare nella prima posizione di indice di una matrice di caratteri i caratteri della parola "Hello" di un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="41cc7-151">The following example uses the `CopyTo` method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>

```csharp
string greeting = "Hello World!";
char[] charArray = {'W','h','e','r','e'};
Console.WriteLine("The original character array: {0}", new string(charArray));
greeting.CopyTo(0, charArray,0 ,5);
Console.WriteLine("The new character array: {0}", new string(charArray));
// The example displays the following output:
//       The original character array: Where
//       The new character array: Hello
```

```vb
Dim greeting As String = "Hello World!"
Dim charArray() As Char = {"W"c, "h"c, "e"c, "r"c, "e"c}
Console.WriteLine("The original character array: {0}", New String(charArray))
greeting.CopyTo(0, charArray,0 ,5)
Console.WriteLine("The new character array: {0}", New String(charArray))
' The example displays the following output:
'       The original character array: Where
'       The new character array: Hello
```

## <a name="see-also"></a><span data-ttu-id="41cc7-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41cc7-152">See Also</span></span>

[<span data-ttu-id="41cc7-153">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="41cc7-153">Basic string operations</span></span>](basic-string-operations.md)

[<span data-ttu-id="41cc7-154">Formattazione composita</span><span class="sxs-lookup"><span data-stu-id="41cc7-154">Composite formatting</span></span>](composite-format.md)


