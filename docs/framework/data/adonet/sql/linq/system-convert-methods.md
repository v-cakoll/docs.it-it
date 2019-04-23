---
title: Metodi System.Convert
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: 9836820f2c084a80fcc0a4856f20597716344dfd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59480651"
---
# <a name="systemconvert-methods"></a><span data-ttu-id="085bb-102">Metodi System.Convert</span><span class="sxs-lookup"><span data-stu-id="085bb-102">System.Convert Methods</span></span>

<span data-ttu-id="085bb-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportati i metodi <xref:System.Convert> riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="085bb-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support the following <xref:System.Convert> methods.</span></span>

- <span data-ttu-id="085bb-104">Versioni con un parametro <xref:System.IFormatProvider>.</span><span class="sxs-lookup"><span data-stu-id="085bb-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>

- <span data-ttu-id="085bb-105">Metodi che interessano matrici di caratteri o matrici di byte:</span><span class="sxs-lookup"><span data-stu-id="085bb-105">Methods that involve char arrays or byte arrays:</span></span>

  - <xref:System.Convert.FromBase64CharArray%2A>

  - <xref:System.Convert.ToBase64CharArray%2A>

  - <xref:System.Convert.FromBase64String%2A>

  - <xref:System.Convert.ToBase64String%2A>

- <span data-ttu-id="085bb-106">I seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="085bb-106">The following methods:</span></span>

  - <span data-ttu-id="085bb-107">`public static <Type2> To<Type2>(<Type1> value);` dove</span><span class="sxs-lookup"><span data-stu-id="085bb-107">`public static <Type2> To<Type2>(<Type1> value);` where</span></span>

    <span data-ttu-id="085bb-108">`Type1` e `Type2` corrispondono ognuno a `sbyte`, `uint`, `ulong` o `ushort`.</span><span class="sxs-lookup"><span data-stu-id="085bb-108">`Type1` and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>

  - <span data-ttu-id="085bb-109">C#:</span><span class="sxs-lookup"><span data-stu-id="085bb-109">C#:</span></span>

    `int To<int type>(string value, int fromBase),`

    `ToString(... value, int toBase)`

  - <span data-ttu-id="085bb-110">Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="085bb-110">Visual Basic:</span></span>

    `Function To(Of [Numeric])(value as String, fromBase As Integer)`

    `As [Numeric], ToString( value As …, toBase As Integer)`

  - <xref:System.Convert.IsDBNull%2A>

  - <xref:System.Convert.GetTypeCode%2A>

  - <xref:System.Convert.ChangeType%2A>

## <a name="see-also"></a><span data-ttu-id="085bb-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="085bb-111">See also</span></span>

- [<span data-ttu-id="085bb-112">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="085bb-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
