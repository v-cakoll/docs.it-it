---
title: Modifica della combinazione di maiuscole e minuscole
description: Modifica della combinazione di maiuscole e minuscole
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 646c5afd-8aec-4393-9c00-f68ad2580c68
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 023f40969095627242d3652add853eb999c30c4b
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="changing-case"></a><span data-ttu-id="f4726-104">Modifica della combinazione di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="f4726-104">Changing case</span></span>

<span data-ttu-id="f4726-105">Quando si scrive un'applicazione che accetta input dall'utente non si può conoscere la combinazione di maiuscole e minuscole che verrà usata durante l'immissione dei dati.</span><span class="sxs-lookup"><span data-stu-id="f4726-105">If you write an application that accepts input from a user, you can never be sure what case he or she will use to enter the data.</span></span> <span data-ttu-id="f4726-106">Spesso è desiderabile che le la combinazione di maiuscole e minuscole nelle stringhe sia coerente, in particolare se le stringhe vengono visualizzate nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="f4726-106">Often, you want strings to be cased consistently, particularly if you are displaying them in the user interface.</span></span> <span data-ttu-id="f4726-107">La tabella seguente descrive due metodi per la modifica della combinazione di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f4726-107">The following table describes two case-changing methods.</span></span>

<span data-ttu-id="f4726-108">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="f4726-108">Method name</span></span> | <span data-ttu-id="f4726-109">Uso</span><span class="sxs-lookup"><span data-stu-id="f4726-109">Use</span></span>
----------- | ---
[<span data-ttu-id="f4726-110">String.ToUpper</span><span class="sxs-lookup"><span data-stu-id="f4726-110">String.ToUpper</span></span>](xref:System.String.ToUpper) | <span data-ttu-id="f4726-111">Converte tutti i caratteri di una stringa in lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="f4726-111">Converts all characters in a string to uppercase.</span></span>
[<span data-ttu-id="f4726-112">String.ToLower</span><span class="sxs-lookup"><span data-stu-id="f4726-112">String.ToLower</span></span>](xref:System.String.ToLower) | <span data-ttu-id="f4726-113">Converte tutti i caratteri di una stringa in lettere minuscole.</span><span class="sxs-lookup"><span data-stu-id="f4726-113">Converts all characters in a string to lowercase.</span></span>

> [!WARNING]  
> <span data-ttu-id="f4726-114">Si noti che i metodi `String.ToUpper` e `String.ToLower` non vanno usati per convertire le stringhe a scopo di confronto o verifica dell'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="f4726-114">Note that the `String.ToUpper` and `String.ToLower` methods should not be used to convert strings in order to compare them or test them for equality.</span></span> 

## <a name="comparing-strings-of-mixed-case"></a><span data-ttu-id="f4726-115">Confronto di stringhe con una combinazione mista di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="f4726-115">Comparing strings of mixed case</span></span>

<span data-ttu-id="f4726-116">Per confrontare stringhe di caratteri maiuscoli e minuscoli per determinare se sono uguali, chiamare uno degli overload del metodo [String](xref:System) `Equals` con un parametro *comparisonType* parametro e specificare un valore di [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) o [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) per l'argomento *comparisonType*.</span><span class="sxs-lookup"><span data-stu-id="f4726-116">To compare strings of mixed case to determine whether they are equal, their, call one of the overloads of the [String](xref:System) `Equals` method with a *comparisonType* parameter, and provide a value of either [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for the *comparisonType* argument.</span></span> 

<span data-ttu-id="f4726-117">Per altre informazioni, vedere [Best Practices for Using Strings](best-practices.md) (Procedure consigliate per l'uso di stringhe).</span><span class="sxs-lookup"><span data-stu-id="f4726-117">For more information, see [Best Practices for Using Strings](best-practices.md).</span></span> 

## <a name="toupper"></a><span data-ttu-id="f4726-118">ToUpper</span><span class="sxs-lookup"><span data-stu-id="f4726-118">ToUpper</span></span>

<span data-ttu-id="f4726-119">Il metodo [String.ToUpper](xref:System.String.ToUpper) converte tutti i caratteri di una stringa in lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="f4726-119">The [String.ToUpper](xref:System.String.ToUpper) method changes all characters in a string to uppercase.</span></span> <span data-ttu-id="f4726-120">L'esempio seguente converte la stringa "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="f4726-120">The following example converts the string "Hello World!"</span></span> <span data-ttu-id="f4726-121">da caratteri maiuscoli e minuscoli in caratteri maiuscoli.</span><span class="sxs-lookup"><span data-stu-id="f4726-121">from mixed case to uppercase.</span></span>

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToUpper());
// This example displays the following output:
//       HELLO WORLD!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToUpper())
' This example displays the following output:
'       HELLO WORLD!
```

## <a name="tolower"></a><span data-ttu-id="f4726-122">ToLower</span><span class="sxs-lookup"><span data-stu-id="f4726-122">ToLower</span></span>

<span data-ttu-id="f4726-123">Il metodo [String.ToLower](xref:System.String.ToLower) è simile al precedente, ma converte tutti i caratteri di una stringa in lettere minuscole.</span><span class="sxs-lookup"><span data-stu-id="f4726-123">The [String.ToLower](xref:System.String.ToLower) method is similar to the previous method, but instead converts all the characters in a string to lowercase.</span></span> <span data-ttu-id="f4726-124">L'esempio seguente converte la stringa "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="f4726-124">The following example converts the string "Hello World!"</span></span> <span data-ttu-id="f4726-125">in caratteri minuscoli.</span><span class="sxs-lookup"><span data-stu-id="f4726-125">to lowercase.</span></span>

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToLower());
// This example displays the following output:
//       hello world!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToLower())
' This example displays the following output:
'       hello world!
```

## <a name="see-also"></a><span data-ttu-id="f4726-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4726-126">See Also</span></span>

[<span data-ttu-id="f4726-127">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="f4726-127">Basic string operations</span></span>](basic-string-operations.md)

