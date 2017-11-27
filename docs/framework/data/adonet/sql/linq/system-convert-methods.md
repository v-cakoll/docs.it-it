---
title: Metodi System.Convert
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7f4ed9cc6ae4668fe978b0e7f685e360f1044e6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="systemconvert-methods"></a><span data-ttu-id="7421a-102">Metodi System.Convert</span><span class="sxs-lookup"><span data-stu-id="7421a-102">System.Convert Methods</span></span>
<span data-ttu-id="7421a-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportati i metodi <xref:System.Convert> riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="7421a-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support the following <xref:System.Convert> methods.</span></span>  
  
-   <span data-ttu-id="7421a-104">Versioni con un parametro <xref:System.IFormatProvider>.</span><span class="sxs-lookup"><span data-stu-id="7421a-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>  
  
-   <span data-ttu-id="7421a-105">Metodi che interessano matrici di caratteri o matrici di byte:</span><span class="sxs-lookup"><span data-stu-id="7421a-105">Methods that involve char arrays or byte arrays:</span></span>  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   <span data-ttu-id="7421a-106">I seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="7421a-106">The following methods:</span></span>  
  
    -   <span data-ttu-id="7421a-107">`public static <Type2> To<Type2>(<Type1> value);` dove</span><span class="sxs-lookup"><span data-stu-id="7421a-107">`public static <Type2> To<Type2>(<Type1> value);` where</span></span>  
  
         <span data-ttu-id="7421a-108">`Type1` e `Type2` corrispondono ognuno a `sbyte`, `uint`, `ulong` o `ushort`.</span><span class="sxs-lookup"><span data-stu-id="7421a-108">`Type1` and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>  
  
    -   <span data-ttu-id="7421a-109">C#:</span><span class="sxs-lookup"><span data-stu-id="7421a-109">C#:</span></span>  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   <span data-ttu-id="7421a-110">Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="7421a-110">Visual Basic:</span></span>  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a><span data-ttu-id="7421a-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7421a-111">See Also</span></span>  
 [<span data-ttu-id="7421a-112">Funzioni e tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7421a-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
