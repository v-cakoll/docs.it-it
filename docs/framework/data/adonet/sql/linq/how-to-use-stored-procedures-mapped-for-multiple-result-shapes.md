---
title: "Procedura: utilizzare stored procedure mappate per più forme di risultati"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fde4dd9044ff2bc6d781d7ceafec2bde3df7e14d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a>Procedura: utilizzare stored procedure mappate per più forme di risultati
Quando una stored procedure consente di restituire più forme di risultati, il tipo restituito non può essere fortemente tipizzato a una singola forma di proiezione. Sebbene [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] può generare tutti i tipi di proiezione possibili, non è possibile conoscere l'ordine in cui saranno restituiti.  
  
 Si consideri questo scenario rispetto a stored procedure che producono più forme di risultati in sequenza. Per ulteriori informazioni, vedere [procedura: utilizzare Stored procedure mappate per forme di risultati sequenziali](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).  
  
 L'attributo <xref:System.Data.Linq.Mapping.ResultTypeAttribute> viene applicato a stored procedure che restituiscono più tipi di risultati per specificare il set di tipi che la stored procedure può restituire.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice SQL riportato di seguito la forma dei risultati dipende dall'input (`shape =1` o `shape = 2`). Non si conosce la proiezione che verrà restituita per prima.  
  
```  
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a>Esempio  
 Per eseguire questa stored procedure si utilizzerà codice simile al seguente.  
  
> [!NOTE]
>  È necessario usare il modello <xref:System.Data.Linq.IMultipleResults.GetResult%2A> per ottenere un enumeratore di tipo corretto, in base alla propria conoscenza della stored procedure.  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche  
 [stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
