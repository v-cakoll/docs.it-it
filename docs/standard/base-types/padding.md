---
title: Aggiunta di spaziatura interna alle stringhe
description: Aggiunta di spaziatura interna alle stringhe
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1c8b3b44-d370-49e1-90b5-64ac81c02ae91c8b3b44-d370-49e1-90b5-64ac81c02ae9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: bc3cc9028b232cc2ba6ca3130c4bdb261c4a0a42
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="padding-strings"></a><span data-ttu-id="999cc-104">Aggiunta di spaziatura interna alle stringhe</span><span class="sxs-lookup"><span data-stu-id="999cc-104">Padding strings</span></span>

<span data-ttu-id="999cc-105">Usare uno dei metodi [System.String](xref:System.String) riportati di seguito per creare una nuova stringa costituita da una stringa originale a cui vengono aggiunti caratteri iniziali o finali fino a una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="999cc-105">Use one of the following [System.String](xref:System.String) methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="999cc-106">Il carattere di riempimento può essere costituito da spazi o da un carattere specificato e di conseguenza viene visualizzato allineato a destra o sinistra.</span><span class="sxs-lookup"><span data-stu-id="999cc-106">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>

<span data-ttu-id="999cc-107">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="999cc-107">Method name</span></span> | <span data-ttu-id="999cc-108">Uso</span><span class="sxs-lookup"><span data-stu-id="999cc-108">Use</span></span>
----------- | ---
<span data-ttu-id="999cc-109">[String.PadLeft](xref:System.String.PadLeft(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="999cc-109">[String.PadLeft](xref:System.String.PadLeft(System.Int32))</span></span> | <span data-ttu-id="999cc-110">Aggiunge caratteri iniziali a una stringa fino a ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="999cc-110">Pads a string with leading characters to a specified total length.</span></span>
<span data-ttu-id="999cc-111">[String.PadRight](xref:System.String.PadRight(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="999cc-111">[String.PadRight](xref:System.String.PadRight(System.Int32))</span></span> | <span data-ttu-id="999cc-112">Aggiunge caratteri finali a una stringa fino a ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="999cc-112">Pads a string with trailing characters to a specified total length.</span></span>

## <a name="padleft"></a><span data-ttu-id="999cc-113">PadLeft</span><span class="sxs-lookup"><span data-stu-id="999cc-113">PadLeft</span></span>

<span data-ttu-id="999cc-114">Il metodo [String.PadLeft](xref:System.String.PadLeft(System.Int32)) crea una nuova stringa concatenando un numero sufficiente di caratteri di riempimento iniziali a una stringa originale per ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="999cc-114">The [String.PadLeft](xref:System.String.PadLeft(System.Int32)) method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="999cc-115">Il metodo [String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32)) usa spazi vuoti come carattere di riempimento e il metodo [String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) consente di specificare il proprio carattere di riempimento.</span><span class="sxs-lookup"><span data-stu-id="999cc-115">The [String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32)) method uses white space as the padding character and the [String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) method enables you to specify your own padding character.</span></span>

<span data-ttu-id="999cc-116">Nell'esempio di codice seguente viene usato il metodo [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) per creare una nuova stringa di venti caratteri.</span><span class="sxs-lookup"><span data-stu-id="999cc-116">The following code example uses the [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="999cc-117">L'esempio visualizza "`--------Hello World!`" nella console.</span><span class="sxs-lookup"><span data-stu-id="999cc-117">The example displays "`--------Hello World!`" to the console.</span></span>

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadLeft(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadLeft(20, "-"c))
```

## <a name="padright"></a><span data-ttu-id="999cc-118">PadRight</span><span class="sxs-lookup"><span data-stu-id="999cc-118">PadRight</span></span>

<span data-ttu-id="999cc-119">Il metodo [String.PadRight](xref:System.String.PadRight(System.Int32)) crea una nuova stringa concatenando un numero sufficiente di caratteri di riempimento finali a una stringa originale per ottenere una lunghezza totale specificata.</span><span class="sxs-lookup"><span data-stu-id="999cc-119">The [String.PadRight](xref:System.String.PadRight(System.Int32)) method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="999cc-120">Il metodo [String.PadRight(Int32)](xref:System.String.PadRight(System.Int32)) usa spazi vuoti come carattere di riempimento e il metodo [String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) consente di specificare il proprio carattere di riempimento.</span><span class="sxs-lookup"><span data-stu-id="999cc-120">The [String.PadRight(Int32)](xref:System.String.PadRight(System.Int32)) method uses white space as the padding character and the [String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) method enables you to specify your own padding character.</span></span>

<span data-ttu-id="999cc-121">Nell'esempio di codice seguente viene usato il metodo [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) per creare una nuova stringa di venti caratteri.</span><span class="sxs-lookup"><span data-stu-id="999cc-121">The following code example uses the [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="999cc-122">L'esempio visualizza "`Hello World!--------`" nella console.</span><span class="sxs-lookup"><span data-stu-id="999cc-122">The example displays "`Hello World!--------`" to the console.</span></span>

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadRight(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadRight(20, "-"c))
```

## <a name="see-also"></a><span data-ttu-id="999cc-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="999cc-123">See Also</span></span>

[<span data-ttu-id="999cc-124">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="999cc-124">Basic string operations</span></span>](basic-string-operations.md)


