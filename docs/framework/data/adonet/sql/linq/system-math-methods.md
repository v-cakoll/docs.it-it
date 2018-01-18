---
title: Metodi System.Math
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: cfcbf915703c72211fc9d958abfda7ffac8aafdc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="systemmath-methods"></a>Metodi System.Math
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportati i metodi <xref:System.Math> riportati di seguito.  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>Differenze rispetto a .NET  
 La semantica di arrotondamento di .NET Framework è diversa da quella di SQL Server. Il <xref:System.Math.Round%2A> metodo in .NET Framework esegue *arrotondamento*, in cui i numeri che terminano,5 arrotondare la cifra più vicina anche anziché alla successiva cifra più elevata. Ad esempio, 2,5 viene arrotondato a 2, mentre 3,5 viene arrotondato a 4. Questa tecnica consente di evitare la distorsione sistematica verso valori più elevati nelle transazioni di grandi quantità di dati.  
  
 In SQL la funzione `ROUND` applica sempre l'arrotondamento a un valore diverso da zero. Pertanto 2,5 viene arrotondato a 3, mentre in .NET Framework viene arrotondato a 2.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] passa alla semantica SQL `ROUND` e non tenta di implementare il tipo particolare di arrotondamento.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
