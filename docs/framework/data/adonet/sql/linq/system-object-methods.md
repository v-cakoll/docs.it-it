---
title: Metodi System.Object
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 3a52f081f1c0c6e6c5218550009c736d0ed60514
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097668"
---
# <a name="systemobject-methods"></a><span data-ttu-id="5e059-102">Metodi System.Object</span><span class="sxs-lookup"><span data-stu-id="5e059-102">System.Object Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5e059-103">supporta i seguenti <xref:System.Object> metodi.</span><span class="sxs-lookup"><span data-stu-id="5e059-103">supports the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5e059-104">non supporta quanto segue <xref:System.Object> metodi.</span><span class="sxs-lookup"><span data-stu-id="5e059-104">does not support the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> <span data-ttu-id="5e059-105">per i tipi binari, ad esempio `BINARY`, `VARBINARY`, `IMAGE`, e `TIMESTAMP`.</span><span class="sxs-lookup"><span data-stu-id="5e059-105">for binary types such as `BINARY`, `VARBINARY`, `IMAGE`, and `TIMESTAMP`.</span></span>||  
  
## <a name="differences-from-net"></a><span data-ttu-id="5e059-106">Differenze rispetto a .NET</span><span class="sxs-lookup"><span data-stu-id="5e059-106">Differences from .NET</span></span>  
 <span data-ttu-id="5e059-107">L'output del <xref:System.Object.ToString?displayProperty=nameWithType> per la doppia Usa SQL `CONVERT`(NVARCHAR(30), @x, 2) in SQL.</span><span class="sxs-lookup"><span data-stu-id="5e059-107">The output of <xref:System.Object.ToString?displayProperty=nameWithType> for double uses SQL `CONVERT`(NVARCHAR(30), @x, 2) on SQL.</span></span> <span data-ttu-id="5e059-108">In SQL vengono sempre usate 16 cifre e la notazione scientifica in questo caso, ad esempio "0.000000000000000e+000" per 0.</span><span class="sxs-lookup"><span data-stu-id="5e059-108">SQL always uses 16 digits and scientific notation in this case (for example, "0.000000000000000e+000" for 0).</span></span> <span data-ttu-id="5e059-109">Di conseguenza, la conversione di <xref:System.Object.ToString?displayProperty=nameWithType> non genera la stessa stringa di <xref:System.Convert.ToString%2A?displayProperty=nameWithType> in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5e059-109">As a result, <xref:System.Object.ToString?displayProperty=nameWithType> conversion does not produce the same string as <xref:System.Convert.ToString%2A?displayProperty=nameWithType> in the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e059-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e059-110">See also</span></span>

- [<span data-ttu-id="5e059-111">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="5e059-111">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
