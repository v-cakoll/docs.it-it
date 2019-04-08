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
# <a name="systemobject-methods"></a>Metodi System.Object
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta i seguenti <xref:System.Object> metodi.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non supporta quanto segue <xref:System.Object> metodi.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> per i tipi binari, ad esempio `BINARY`, `VARBINARY`, `IMAGE`, e `TIMESTAMP`.||  
  
## <a name="differences-from-net"></a>Differenze rispetto a .NET  
 L'output del <xref:System.Object.ToString?displayProperty=nameWithType> per la doppia Usa SQL `CONVERT`(NVARCHAR(30), @x, 2) in SQL. In SQL vengono sempre usate 16 cifre e la notazione scientifica in questo caso, ad esempio "0.000000000000000e+000" per 0. Di conseguenza, la conversione di <xref:System.Object.ToString?displayProperty=nameWithType> non genera la stessa stringa di <xref:System.Convert.ToString%2A?displayProperty=nameWithType> in .NET Framework.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
