---
title: 'Procedura: Usare stored procedure che accettano parametri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: 8dd463c895efcddfe288fe1dc8571981872d9d80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181766"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a>Procedura: Usare stored procedure che accettano parametri
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] esegue il mapping di parametri di output ai parametri di riferimento e per i tipi di valore dichiara il parametro come nullable.  
  
 Per un esempio di come usare un parametro di input in una query che restituisce un set di righe, vedere [come: Restituire rowset](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).  
  
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

- [Stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Utilizzo dei tipi nullable](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)
- [Tipi di valori nullable](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
