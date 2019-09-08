---
title: Metodi System.Math
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: 0b113cefa6be040924134f9d2d0cb0c9d334feef
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792398"
---
# <a name="systemmath-methods"></a><span data-ttu-id="efd3a-102">Metodi System.Math</span><span class="sxs-lookup"><span data-stu-id="efd3a-102">System.Math Methods</span></span>
<span data-ttu-id="efd3a-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportati i metodi <xref:System.Math> riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="efd3a-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support the following <xref:System.Math> methods.</span></span>  
  
- <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="efd3a-104">Differenze rispetto a .NET</span><span class="sxs-lookup"><span data-stu-id="efd3a-104">Differences from .NET</span></span>  
 <span data-ttu-id="efd3a-105">La semantica di arrotondamento di .NET Framework è diversa da quella di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="efd3a-105">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="efd3a-106">Il <xref:System.Math.Round%2A> metodo nel .NET Framework esegue l' *arrotondamento del banco*, in cui i numeri che terminano con 0,5 arrotondano alla cifra pari più vicina invece che alla cifra più alta successiva.</span><span class="sxs-lookup"><span data-stu-id="efd3a-106">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="efd3a-107">Ad esempio, 2,5 viene arrotondato a 2, mentre 3,5 viene arrotondato a 4.</span><span class="sxs-lookup"><span data-stu-id="efd3a-107">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="efd3a-108">Questa tecnica consente di evitare la distorsione sistematica verso valori più elevati nelle transazioni di grandi quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="efd3a-108">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="efd3a-109">In SQL la funzione `ROUND` applica sempre l'arrotondamento a un valore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="efd3a-109">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="efd3a-110">Pertanto 2,5 viene arrotondato a 3, mentre in .NET Framework viene arrotondato a 2.</span><span class="sxs-lookup"><span data-stu-id="efd3a-110">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="efd3a-111">passa alla semantica SQL `ROUND` e non tenta di implementare il tipo particolare di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="efd3a-111">passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd3a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efd3a-112">See also</span></span>

- [<span data-ttu-id="efd3a-113">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="efd3a-113">Data Types and Functions</span></span>](data-types-and-functions.md)
