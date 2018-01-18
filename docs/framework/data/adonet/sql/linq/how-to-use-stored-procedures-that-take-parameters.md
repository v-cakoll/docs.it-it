---
title: 'Procedura: utilizzare stored procedure che accettano parametri'
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
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 505c99b262f4762d5965789688236b22e74bdaeb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a>Procedura: utilizzare stored procedure che accettano parametri
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping dei parametri di output ai parametri di riferimento, mentre per i tipi di valori il parametro viene dichiarato come nullable.  
  
 Per un esempio di come utilizzare un parametro di input in una query che restituisce un set di righe, vedere [procedura: restituire rowset](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene accettato un solo parametro di input (l'ID del cliente) e viene restituito un parametro out (le vendite totali per quel cliente).  
  
```  
CREATE PROCEDURE [dbo].[CustOrderTotal]   
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a>Esempio  
 Chiamare questa stored procedure come segue:  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Uso dei tipi nullable](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [Tipi di valori nullable](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
