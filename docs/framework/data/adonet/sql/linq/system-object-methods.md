---
title: Metodi System.Object
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 319dc7ceae191de417bbdd33a5e234b42f3454de
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="systemobject-methods"></a>Metodi System.Object
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]supporta i seguenti <xref:System.Object> metodi.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportati i metodi <xref:System.Object> riportati di seguito.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> per i tipi binari, ad esempio `BINARY`, `VARBINARY`, `IMAGE` e `TIMESTAMP`.||  
  
## <a name="differences-from-net"></a>Differenze rispetto a .NET  
 L'output di <xref:System.Object.ToString?displayProperty=nameWithType> per doppia utilizza SQL `CONVERT`(nvarchar (30), @x, 2) in SQL. In SQL vengono sempre usate 16 cifre e la notazione scientifica in questo caso, ad esempio "0.000000000000000e+000" per 0. Di conseguenza, la conversione di <xref:System.Object.ToString?displayProperty=nameWithType> non genera la stessa stringa di <xref:System.Convert.ToString%2A?displayProperty=nameWithType> in .NET Framework.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
