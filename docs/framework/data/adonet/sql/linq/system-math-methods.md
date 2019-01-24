---
title: Metodi System.Math
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: 45a674c86fc2f19f3e273834b8cb9d6adee5b3ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576863"
---
# <a name="systemmath-methods"></a>Metodi System.Math
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportati i metodi <xref:System.Math> riportati di seguito.  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>Differenze rispetto a .NET  
 La semantica di arrotondamento di .NET Framework è diversa da quella di SQL Server. Il <xref:System.Math.Round%2A> metodo in .NET Framework esegue *arrotondamento*, in cui i numeri che terminano in,5 arrotondati alla cifra pari anziché alla cifra più elevata successiva più vicina. Ad esempio, 2,5 viene arrotondato a 2, mentre 3,5 viene arrotondato a 4. Questa tecnica consente di evitare la distorsione sistematica verso valori più elevati nelle transazioni di grandi quantità di dati.  
  
 In SQL la funzione `ROUND` applica sempre l'arrotondamento a un valore diverso da zero. Pertanto 2,5 viene arrotondato a 3, mentre in .NET Framework viene arrotondato a 2.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] passa alla semantica SQL `ROUND` e non tenta di implementare il tipo particolare di arrotondamento.  
  
## <a name="see-also"></a>Vedere anche
- [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
