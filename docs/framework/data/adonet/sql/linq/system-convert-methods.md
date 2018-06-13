---
title: Metodi System.Convert
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: a16839bf64d5786caa6feb557333fe93c66edc3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357374"
---
# <a name="systemconvert-methods"></a><span data-ttu-id="4eed1-102">Metodi System.Convert</span><span class="sxs-lookup"><span data-stu-id="4eed1-102">System.Convert Methods</span></span>
<span data-ttu-id="4eed1-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportati i metodi <xref:System.Convert> riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="4eed1-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support the following <xref:System.Convert> methods.</span></span>  
  
-   <span data-ttu-id="4eed1-104">Versioni con un parametro <xref:System.IFormatProvider>.</span><span class="sxs-lookup"><span data-stu-id="4eed1-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>  
  
-   <span data-ttu-id="4eed1-105">Metodi che interessano matrici di caratteri o matrici di byte:</span><span class="sxs-lookup"><span data-stu-id="4eed1-105">Methods that involve char arrays or byte arrays:</span></span>  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   <span data-ttu-id="4eed1-106">I seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="4eed1-106">The following methods:</span></span>  
  
    -   <span data-ttu-id="4eed1-107">`public static <Type2> To<Type2>(<Type1> value);` dove</span><span class="sxs-lookup"><span data-stu-id="4eed1-107">`public static <Type2> To<Type2>(<Type1> value);` where</span></span>  
  
         <span data-ttu-id="4eed1-108">`Type1` e `Type2` corrispondono ognuno a `sbyte`, `uint`, `ulong` o `ushort`.</span><span class="sxs-lookup"><span data-stu-id="4eed1-108">`Type1` and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>  
  
    -   <span data-ttu-id="4eed1-109">C#:</span><span class="sxs-lookup"><span data-stu-id="4eed1-109">C#:</span></span>  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   <span data-ttu-id="4eed1-110">Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="4eed1-110">Visual Basic:</span></span>  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a><span data-ttu-id="4eed1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4eed1-111">See Also</span></span>  
 [<span data-ttu-id="4eed1-112">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="4eed1-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
