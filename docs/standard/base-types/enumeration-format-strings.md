---
title: Stringhe di formato di enumerazione
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
ms.openlocfilehash: c32fd9d59f61b6befe94ff9eb85b0c39ce926adb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348259"
---
# <a name="enumeration-format-strings"></a><span data-ttu-id="16b45-102">Stringhe di formato di enumerazione</span><span class="sxs-lookup"><span data-stu-id="16b45-102">Enumeration format strings</span></span>

<span data-ttu-id="16b45-103">È possibile usare il metodo <xref:System.Enum.ToString%2A?displayProperty=nameWithType> per creare un nuovo oggetto stringa che rappresenti il valore numerico, esadecimale o stringa di un membro di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="16b45-103">You can use the <xref:System.Enum.ToString%2A?displayProperty=nameWithType> method to create a new string object that represents the numeric, hexadecimal, or string value of an enumeration member.</span></span> <span data-ttu-id="16b45-104">Questo metodo accetta una delle stringhe di formattazione di enumerazione per specificare il valore che si vuole venga restituito.</span><span class="sxs-lookup"><span data-stu-id="16b45-104">This method takes one of the enumeration formatting strings to specify the value that you want returned.</span></span>

<span data-ttu-id="16b45-105">Nella tabella che segue sono elencate le stringhe di formattazione di enumerazione e i valori da esse restituiti.</span><span class="sxs-lookup"><span data-stu-id="16b45-105">The following sections list the enumeration formatting strings and the values they return.</span></span> <span data-ttu-id="16b45-106">In questi identificatori di formato non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="16b45-106">These format specifiers are not case-sensitive.</span></span>

## <a name="g-or-g"></a><span data-ttu-id="16b45-107">G o g</span><span class="sxs-lookup"><span data-stu-id="16b45-107">G or g</span></span>

<span data-ttu-id="16b45-108">Visualizza la voce di enumerazione sotto forma di valore di stringa, se possibile; in caso contrario, visualizza il valore intero dell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="16b45-108">Displays the enumeration entry as a string value, if possible, and otherwise displays the integer value of the current instance.</span></span> <span data-ttu-id="16b45-109">Se l'enumerazione viene definita con l'attributo **Flags** impostato, i valori di stringa di ogni voce valida vengono concatenati tra loro, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="16b45-109">If the enumeration is defined with the **Flags** attribute set, the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="16b45-110">Se l'attributo **Flags** non è impostato, verrà visualizzato un valore non valido come voce numerica.</span><span class="sxs-lookup"><span data-stu-id="16b45-110">If the **Flags** attribute is not set, an invalid value is displayed as a numeric entry.</span></span> <span data-ttu-id="16b45-111">L'esempio seguente illustra l'identificatore di formato G.</span><span class="sxs-lookup"><span data-stu-id="16b45-111">The following example illustrates the G format specifier.</span></span>

[!code-csharp[Formatting.Enum#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
[!code-vb[Formatting.Enum#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]

## <a name="f-or-f"></a><span data-ttu-id="16b45-112">F o f</span><span class="sxs-lookup"><span data-stu-id="16b45-112">F or f</span></span>

<span data-ttu-id="16b45-113">Visualizza la voce di enumerazione come valore di stringa, se possibile.</span><span class="sxs-lookup"><span data-stu-id="16b45-113">Displays the enumeration entry as a string value, if possible.</span></span> <span data-ttu-id="16b45-114">Se il valore può essere visualizzato interamente come somma delle voci nell'enumerazione (anche se l'attributo **Flags** è assente), i valori di stringa di ogni voce valida vengono concatenati tra loro, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="16b45-114">If the value can be completely displayed as a summation of the entries in the enumeration (even if the **Flags** attribute is not present), the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="16b45-115">Se non è possibile determinare completamente il valore sulla base delle voci di enumerazione, il valore verrà formattato sotto forma di valore intero.</span><span class="sxs-lookup"><span data-stu-id="16b45-115">If the value cannot be completely determined by the enumeration entries, then the value is formatted as the integer value.</span></span> <span data-ttu-id="16b45-116">L'esempio seguente illustra l'identificatore di formato F.</span><span class="sxs-lookup"><span data-stu-id="16b45-116">The following example illustrates the F format specifier.</span></span>

[!code-csharp[Formatting.Enum#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
[!code-vb[Formatting.Enum#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]

## <a name="d-or-d"></a><span data-ttu-id="16b45-117">D o d</span><span class="sxs-lookup"><span data-stu-id="16b45-117">D or d</span></span>

<span data-ttu-id="16b45-118">Visualizza la voce di enumerazione come valore intero nella rappresentazione più breve possibile.</span><span class="sxs-lookup"><span data-stu-id="16b45-118">Displays the enumeration entry as an integer value in the shortest representation possible.</span></span> <span data-ttu-id="16b45-119">L'esempio seguente illustra l'identificatore di formato D.</span><span class="sxs-lookup"><span data-stu-id="16b45-119">The following example illustrates the D format specifier.</span></span>

[!code-csharp[Formatting.Enum#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
[!code-vb[Formatting.Enum#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]

## <a name="x-or-x"></a><span data-ttu-id="16b45-120">X o x</span><span class="sxs-lookup"><span data-stu-id="16b45-120">X or x</span></span>

<span data-ttu-id="16b45-121">Visualizza la voce di enumerazione come valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="16b45-121">Displays the enumeration entry as a hexadecimal value.</span></span> <span data-ttu-id="16b45-122">Il valore viene rappresentato con zeri inziali, se necessario, per garantire che la stringa del risultato abbia due caratteri per ogni byte nel [tipo numerico sottostante](xref:System.Enum.GetUnderlyingType%2A) del tipo di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="16b45-122">The value is represented with leading zeros as necessary, to ensure that the result string has two characters for each byte in the enumeration type's [underlying numeric type](xref:System.Enum.GetUnderlyingType%2A).</span></span> <span data-ttu-id="16b45-123">L'esempio seguente illustra l'identificatore di formato X.</span><span class="sxs-lookup"><span data-stu-id="16b45-123">The following example illustrates the X format specifier.</span></span> <span data-ttu-id="16b45-124">Nell'esempio il tipo sottostante di <xref:System.ConsoleColor> e <xref:System.IO.FileAttributes> è <xref:System.Int32> o un numero intero a 32 bit (o 4 byte) che produce una stringa del risultato di 8 caratteri.</span><span class="sxs-lookup"><span data-stu-id="16b45-124">In the example, the underlying type of both <xref:System.ConsoleColor> and <xref:System.IO.FileAttributes> is <xref:System.Int32>, or a 32-bit (or 4-byte) integer, which produces an 8-character result string.</span></span>

[!code-csharp[Formatting.Enum#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]      
[!code-vb[Formatting.Enum#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]

## <a name="example"></a><span data-ttu-id="16b45-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="16b45-125">Example</span></span>

<span data-ttu-id="16b45-126">L'esempio seguente definisce un'enumerazione denominata `Colors` costituita dalle tre voci `Red`, `Blue` e `Green`.</span><span class="sxs-lookup"><span data-stu-id="16b45-126">The following example defines an enumeration called `Colors` that consists of three entries: `Red`, `Blue`, and `Green`.</span></span>

[!code-csharp[Formatting.Enum#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
[!code-vb[Formatting.Enum#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]

<span data-ttu-id="16b45-127">Dopo aver definito l'enumerazione è possibile dichiararne un'istanza nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="16b45-127">After the enumeration is defined, an instance can be declared in the following manner.</span></span>

[!code-csharp[Formatting.Enum#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
[!code-vb[Formatting.Enum#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]

<span data-ttu-id="16b45-128">Sarà quindi possibile usare il metodo `Color.ToString(System.String)` per visualizzare il valore di enumerazione in modi diversi, a seconda dell'identificatore di formato passato.</span><span class="sxs-lookup"><span data-stu-id="16b45-128">The `Color.ToString(System.String)` method can then be used to display the enumeration value in different ways, depending on the format specifier passed to it.</span></span>

[!code-csharp[Formatting.Enum#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
[!code-vb[Formatting.Enum#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]

## <a name="see-also"></a><span data-ttu-id="16b45-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16b45-129">See also</span></span>

- [<span data-ttu-id="16b45-130">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="16b45-130">Formatting Types</span></span>](formatting-types.md)
