---
title: Eliminazione di spazi iniziali e finali e rimozione di caratteri dalle stringhe
description: Eliminazione di spazi iniziali e finali e rimozione di caratteri dalle stringhe
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 95d818bc-2661-43f6-adb8-13b53abf9682
ms.translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 6105861882c3bfd525a2d902fd2600f5da10417d
ms.contentlocale: it-it
ms.lasthandoff: 11/16/2016

---

# <a name="trimming-and-removing-characters-from-strings"></a><span data-ttu-id="3a0a2-104">Eliminazione di spazi iniziali e finali e rimozione di caratteri dalle stringhe</span><span class="sxs-lookup"><span data-stu-id="3a0a2-104">Trimming and removing characters from strings</span></span>

<span data-ttu-id="3a0a2-105">Se si sta analizzando una frase in singole parole, è possibile che si ottengano parole con spazi vuoti alle estremità.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-105">If you are parsing a sentence into individual words, you might end up with words that have blank spaces (also called white spaces) on either end of the word.</span></span> <span data-ttu-id="3a0a2-106">In questo caso è possibile usare uno dei metodi trim della classe [System.String](https://docs.microsoft.com/dotnet/core/api/System.String) per rimuovere un numero qualsiasi di spazi o altri caratteri da una posizione specificata nella stringa.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-106">In this situation, you can use one of the trim methods in the [System.String](https://docs.microsoft.com/dotnet/core/api/System.String) class to remove any number of spaces or other characters from a specified position in the string.</span></span> <span data-ttu-id="3a0a2-107">La tabella seguente illustra i metodi trim disponibili.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-107">The following table describes the available trim methods.</span></span>

<span data-ttu-id="3a0a2-108">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="3a0a2-108">Method name</span></span> | <span data-ttu-id="3a0a2-109">Uso</span><span class="sxs-lookup"><span data-stu-id="3a0a2-109">Use</span></span>
----------- | ---
[<span data-ttu-id="3a0a2-110">String.Trim</span><span class="sxs-lookup"><span data-stu-id="3a0a2-110">String.Trim</span></span>](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) | <span data-ttu-id="3a0a2-111">Rimuove gli spazi vuoti o i caratteri specificati in una matrice di caratteri all'inizio e alla fine di una stringa.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-111">Removes white spaces or characters specified in an array of characters from the beginning and end of a string.</span></span>
<span data-ttu-id="3a0a2-112">[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))</span><span class="sxs-lookup"><span data-stu-id="3a0a2-112">[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))</span></span> | <span data-ttu-id="3a0a2-113">Rimuove i caratteri specificati in una matrice di caratteri alla fine di una stringa.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-113">Removes characters specified in an array of characters from the end of a string.</span></span>
<span data-ttu-id="3a0a2-114">[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[]))</span><span class="sxs-lookup"><span data-stu-id="3a0a2-114">[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[]))</span></span> | <span data-ttu-id="3a0a2-115">Rimuove i caratteri specificati in una matrice di caratteri all'inizio di una stringa.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-115">Removes characters specified in an array of characters from the beginning of a string.</span></span>
<span data-ttu-id="3a0a2-116">[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3a0a2-116">[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32))</span></span> | <span data-ttu-id="3a0a2-117">Rimuove un numero specificato di caratteri da una posizione di indice specificata in una stringa.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-117">Removes a specified number of characters from a specified index position in a string.</span></span>


## <a name="trim"></a><span data-ttu-id="3a0a2-118">Trim</span><span class="sxs-lookup"><span data-stu-id="3a0a2-118">Trim</span></span>

<span data-ttu-id="3a0a2-119">È possibile rimuovere facilmente gli spazi vuoti da entrambe le estremità di una stringa usando il metodo [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim), come visualizzato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-119">You can easily remove white spaces from both ends of a string by using the [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) method, as shown in the following example.</span></span>

```csharp
string MyString = " Big   ";
Console.WriteLine("Hello{0}World!", MyString);
string TrimString = MyString.Trim();
Console.WriteLine("Hello{0}World!", TrimString);
//       The example displays the following output:
//             Hello Big   World!
//             HelloBigWorld!
```

```vb
Dim MyString As String = " Big   "
Console.WriteLine("Hello{0}World!", MyString)
Dim TrimString As String = MyString.Trim()
Console.WriteLine("Hello{0}World!", TrimString)
' The example displays the following output:
'       Hello Big   World!
'       HelloBigWorld!
```

<span data-ttu-id="3a0a2-120">È anche possibile rimuovere i caratteri specificati in una matrice di caratteri all'inizio e alla fine di una stringa.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-120">You can also remove characters that you specify in a character array from the beginning and end of a string.</span></span> <span data-ttu-id="3a0a2-121">Nell'esempio seguente vengono rimossi gli spazi vuoti, i punti e gli asterischi.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-121">The following example removes white-space characters, periods, and asterisks.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String header = "* A Short String. *";
      Console.WriteLine(header);
      Console.WriteLine(header.Trim( new Char[] { ' ', '*', '.' } ));
   }
}
// The example displays the following output:
//       * A Short String. *
//       A Short String
```

```vb
Module Example
   Public Sub Main()
      Dim header As String = "* A Short String. *"
      Console.WriteLine(header)
      Console.WriteLine(header.Trim( { " "c, "*"c, "."c } ))
   End Sub
End Module
' The example displays the following output:
'       * A Short String. *
'       A Short String
```

## <a name="trimend"></a><span data-ttu-id="3a0a2-122">TrimEnd</span><span class="sxs-lookup"><span data-stu-id="3a0a2-122">TrimEnd</span></span>

<span data-ttu-id="3a0a2-123">Il metodo [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) rimuove caratteri alla fine di una stringa, creando un nuovo oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-123">The [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method removes characters from the end of a string, creating a new string object.</span></span> <span data-ttu-id="3a0a2-124">Una matrice di caratteri viene passata a questo metodo per specificare i caratteri da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-124">An array of characters is passed to this method to specify the characters to be removed.</span></span> <span data-ttu-id="3a0a2-125">L'ordine degli elementi nella matrice di caratteri non influenza l'operazione di rimozione.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-125">The order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="3a0a2-126">La rimozione si interrompe quando viene trovato un carattere non specificato nella matrice.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-126">The trim stops when a character not specified in the array is found.</span></span>

<span data-ttu-id="3a0a2-127">L'esempio seguente rimuove le ultime lettere di una stringa con il metodo TrimEnd.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-127">The following example removes the last letters of a string using the TrimEnd method.</span></span> <span data-ttu-id="3a0a2-128">In questo esempio la posizione dei caratteri `'r'` e `'W'` viene invertita per indicare che l'ordine dei caratteri nella matrice non è importante.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-128">In this example, the position of the `'r'` character and the `'W'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span> <span data-ttu-id="3a0a2-129">Si noti che questo codice rimuove l'ultima parola di `MyString` e una parte della prima parola.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-129">Notice that this code removes the last word of `MyString` plus part of the first.</span></span>

```csharp
string MyString = "Hello World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="3a0a2-130">Il codice visualizza `He` nella console.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-130">This code displays `He` to the console.</span></span>

<span data-ttu-id="3a0a2-131">L'esempio seguente rimuove l'ultima parola di una stringa con il metodo [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])).</span><span class="sxs-lookup"><span data-stu-id="3a0a2-131">The following example removes the last word of a string using the [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method.</span></span> <span data-ttu-id="3a0a2-132">In questo codice la parola `Hello` è seguita da una virgola: dato che la virgola non è specificata nella matrice di caratteri da tagliare, l'operazione di taglio termina in corrispondenza della virgola.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-132">In this code, a comma follows the word `Hello` and, because the comma is not specified in the array of characters to trim, the trim ends at the comma.</span></span>

```csharp
string MyString = "Hello, World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello, World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="3a0a2-133">Il codice visualizza `Hello,` nella console.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-133">This code displays `Hello,` to the console.</span></span>

## <a name="trimstart"></a><span data-ttu-id="3a0a2-134">TrimStart</span><span class="sxs-lookup"><span data-stu-id="3a0a2-134">TrimStart</span></span>

<span data-ttu-id="3a0a2-135">Il metodo [String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) è simile al metodo [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) ma crea una nuova stringa rimuovendo caratteri dall'inizio di un oggetto stringa esistente.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-135">The [String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) method is similar to the [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method except that it creates a new string by removing characters from the beginning of an existing string object.</span></span> <span data-ttu-id="3a0a2-136">Una matrice di caratteri viene passata al metodo [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) per specificare i caratteri da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-136">An array of characters is passed to the [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) method to specify the characters to be removed.</span></span> <span data-ttu-id="3a0a2-137">Come per il metodo [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])), l'ordine degli elementi nella matrice di caratteri non è importante per l'operazione di rimozione.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-137">As with the [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method, the order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="3a0a2-138">La rimozione si interrompe quando viene trovato un carattere non specificato nella matrice.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-138">The trim stops when a character not specified in the array is found.</span></span>

<span data-ttu-id="3a0a2-139">L'esempio seguente rimuove la prima parola di una stringa.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-139">The following example removes the first word of a string.</span></span> <span data-ttu-id="3a0a2-140">In questo esempio la posizione dei caratteri `'l'` e `'H'` viene invertita per indicare che l'ordine dei caratteri nella matrice non è importante.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-140">In this example, the position of the `'l'` character and the `'H'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span>

```csharp
string MyString = "Hello World!";
char[] MyChar = {'e', 'H','l','o',' ' };
string NewString = MyString.TrimStart(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"e","H","l","o"," " }
Dim NewString As String = MyString.TrimStart(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="3a0a2-141">Il codice visualizza `World!` nella console.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-141">This code displays `World!` to the console.</span></span>

## <a name="remove"></a><span data-ttu-id="3a0a2-142">Rimuovi</span><span class="sxs-lookup"><span data-stu-id="3a0a2-142">Remove</span></span>

<span data-ttu-id="3a0a2-143">Il metodo [String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) rimuove un numero specificato di caratteri a partire da una posizione specificata in una stringa esistente.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-143">The [String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) method removes a specified number of characters that begin at a specified position in an existing string.</span></span> <span data-ttu-id="3a0a2-144">Questo metodo presuppone un indice a base zero.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-144">This method assumes a zero-based index.</span></span>

<span data-ttu-id="3a0a2-145">L'esempio seguente rimuove dieci caratteri da una stringa a partire dalla posizione cinque di un indice a base zero della stringa.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-145">The following example removes ten characters from a string beginning at position five of a zero-based index of the string.</span></span>

```csharp
string MyString = "Hello Beautiful World!";
Console.WriteLine(MyString.Remove(5,10));
// The example displays the following output:
//         Hello World!  
```

```vb
Dim MyString As String = "Hello Beautiful World!"
Console.WriteLine(MyString.Remove(5,10))
' The example displays the following output:
'         Hello World!
```

<span data-ttu-id="3a0a2-146">È anche possibile rimuovere da una stringa una sottostringa o un carattere specificato chiamando il metodo [String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String)) e specificando in sostituzione una stringa vuota ([String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)).</span><span class="sxs-lookup"><span data-stu-id="3a0a2-146">You can also remove a specified character or substring from a string by calling the [String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String)) method and specifying an empty string ([String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)) as the replacement.</span></span> <span data-ttu-id="3a0a2-147">Nell'esempio seguente vengono rimosse tutte le virgole da una stringa.</span><span class="sxs-lookup"><span data-stu-id="3a0a2-147">The following example removes all commas from a string.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String phrase = "a cold, dark night";
      Console.WriteLine("Before: {0}", phrase);
      phrase = phrase.Replace(",", "");
      Console.WriteLine("After: {0}", phrase);
   }
}
// The example displays the following output:
//       Before: a cold, dark night
//       After: a cold dark night
```

```vb
Module Example
   Public Sub Main()
      Dim phrase As String = "a cold, dark night"
      Console.WriteLine("Before: {0}", phrase)
      phrase = phrase.Replace(",", "")
      Console.WriteLine("After: {0}", phrase)
   End Sub
End Module
' The example displays the following output:
'       Before: a cold, dark night
'       After: a cold dark night
```

## <a name="see-also"></a><span data-ttu-id="3a0a2-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a0a2-148">See Also</span></span>

[<span data-ttu-id="3a0a2-149">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="3a0a2-149">Basic string operations</span></span>](basic-string-operations.md)


