---
title: "Procedura: Usare funzioni definite dall'utente con valori scalari"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: 31797ae7d0fe23227cc4af733fbceac5d474f779
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781453"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a>Procedura: Usare funzioni definite dall'utente con valori scalari
Una funzione con valori di tabella restituisce un unico rowset, a differenza delle stored procedure che possono restituire forme di più risultati. Poiché il tipo restituito di una funzione con valori di tabella è `Table`, è possibile usare tale funzione in un punto qualsiasi del codice SQL in cui possa essere usata una tabella. È inoltre possibile gestire la funzione con valori di tabella esattamente come una tabella.  
  
## <a name="example"></a>Esempio  
 La funzione SQL riportata di seguito dichiara in modo esplicito che verrà restituito `TABLE`. La struttura del rowset restituito è quindi definita in modo implicito.  
  
```  
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] esegue il mapping della funzione come segue:  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a>Esempio  
 Il codice SQL seguente mostra come sia possibile creare un join alla tabella restituita dalla funzione e diversamente gestirla come qualsiasi altra tabella:  
  
```  
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] il rendering della query viene eseguito come segue:  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni definite dall'utente](user-defined-functions.md)
