---
title: Come convertire una matrice di byte in una guida per C# programmatori int
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
ms.openlocfilehash: 9f477649dba1b42d7a10d521c010977707daf3ec
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75698755"
---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a><span data-ttu-id="7ef50-102">Come convertire una matrice di byte in un int (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="7ef50-102">How to convert a byte array to an int (C# Programming Guide)</span></span>

<span data-ttu-id="7ef50-103">Questo esempio mostra come usare la classe <xref:System.BitConverter> per convertire una matrice di byte in un valore [int](../../language-reference/builtin-types/integral-numeric-types.md) e di nuovo in una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="7ef50-103">This example shows you how to use the <xref:System.BitConverter> class to convert an array of bytes to an [int](../../language-reference/builtin-types/integral-numeric-types.md) and back to an array of bytes.</span></span> <span data-ttu-id="7ef50-104">Può essere necessario ad esempio convertire i byte in un tipo di dati predefinito dopo la lettura dei byte dalla rete.</span><span class="sxs-lookup"><span data-stu-id="7ef50-104">You may have to convert from bytes to a built-in data type after you read bytes off the network, for example.</span></span> <span data-ttu-id="7ef50-105">Oltre al metodo [ToInt32 (Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) nell'esempio, nella tabella seguente sono elencati i metodi della classe <xref:System.BitConverter> che convertono i byte (da una matrice di byte) ad altri tipi incorporati.</span><span class="sxs-lookup"><span data-stu-id="7ef50-105">In addition to the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method in the example, the following table lists methods in the <xref:System.BitConverter> class that convert bytes (from an array of bytes) to other built-in types.</span></span>

|<span data-ttu-id="7ef50-106">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="7ef50-106">Type returned</span></span>|<span data-ttu-id="7ef50-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="7ef50-107">Method</span></span>|
|-------------------|------------|
|`bool`|<span data-ttu-id="7ef50-108">[ToBoolean (byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="7ef50-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span></span>|
|`char`|<span data-ttu-id="7ef50-109">[ToChar (byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="7ef50-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span></span>|
|`double`|<span data-ttu-id="7ef50-110">[ToDouble (byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="7ef50-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span></span>|
|`short`|<span data-ttu-id="7ef50-111">[ToInt16 (byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="7ef50-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span></span>|
|`int`|<span data-ttu-id="7ef50-112">[ToInt32 (byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="7ef50-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span></span>|
|`long`|<span data-ttu-id="7ef50-113">[ToInt64 (byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="7ef50-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span></span>|
|`float`|<span data-ttu-id="7ef50-114">[ToSingle (byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="7ef50-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span></span>|
|`ushort`|<span data-ttu-id="7ef50-115">[ToUInt16 (byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="7ef50-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span></span>|
|`uint`|<span data-ttu-id="7ef50-116">[ToUInt32 (byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="7ef50-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span></span>|
|`ulong`|<span data-ttu-id="7ef50-117">[ToUInt64 (byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="7ef50-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span></span>|

## <a name="example"></a><span data-ttu-id="7ef50-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ef50-118">Example</span></span>

<span data-ttu-id="7ef50-119">Questo esempio Inizializza una matrice di byte, inverte la matrice se l'architettura del computer è Little-endian (ovvero il byte meno significativo viene archiviato per primo), quindi chiama il metodo [ToInt32 (byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) per convertire quattro byte nella matrice in un `int`.</span><span class="sxs-lookup"><span data-stu-id="7ef50-119">This example initializes an array of bytes, reverses the array if the computer architecture is little-endian (that is, the least significant byte is stored first), and then calls the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method to convert four bytes in the array to an `int`.</span></span> <span data-ttu-id="7ef50-120">Il secondo argomento di [ToInt32 (Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) specifica l'indice iniziale della matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="7ef50-120">The second argument to [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) specifies the start index of the array of bytes.</span></span>

> [!NOTE]
> <span data-ttu-id="7ef50-121">L'output può variare a seconda dell'aspetto dell'architettura del computer.</span><span class="sxs-lookup"><span data-stu-id="7ef50-121">The output may differ depending on the endianness of your computer's architecture.</span></span>

[!code-csharp[csProgGuideTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#22)]

## <a name="example"></a><span data-ttu-id="7ef50-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ef50-122">Example</span></span>

<span data-ttu-id="7ef50-123">In questo esempio viene chiamato il metodo <xref:System.BitConverter.GetBytes%28System.Int32%29> della classe <xref:System.BitConverter> per convertire un valore `int` in una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="7ef50-123">In this example, the <xref:System.BitConverter.GetBytes%28System.Int32%29> method of the <xref:System.BitConverter> class is called to convert an `int` to an array of bytes.</span></span>

> [!NOTE]
> <span data-ttu-id="7ef50-124">L'output può variare a seconda dell'aspetto dell'architettura del computer.</span><span class="sxs-lookup"><span data-stu-id="7ef50-124">The output may differ depending on the endianness of your computer's architecture.</span></span>

[!code-csharp[csProgGuideTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#23)]

## <a name="see-also"></a><span data-ttu-id="7ef50-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ef50-125">See also</span></span>

- <xref:System.BitConverter>
- <xref:System.BitConverter.IsLittleEndian>
- [<span data-ttu-id="7ef50-126">Tipi</span><span class="sxs-lookup"><span data-stu-id="7ef50-126">Types</span></span>](./index.md)
