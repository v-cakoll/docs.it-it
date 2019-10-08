---
title: 'Procedura: Usare stored procedure mappate per forme di risultati sequenziali'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: 8378a175ab2479ab9769ca08579e1c89269eaba4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003215"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a>Procedura: Usare stored procedure mappate per forme di risultati sequenziali
Questo tipo di stored procedure può generare più di una forma di risultati, tuttavia si conosce l'ordine in cui tali risultati vengono restituiti. Si consideri questo scenario rispetto allo scenario in cui non si conosca la sequenza dei risultati restituiti. Per altre informazioni, vedere [Procedura: Utilizzare stored procedure mappate per più forme risultato @ no__t-0.  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato il codice T-SQL di un stored procedure che restituisce più forme di risultati in sequenza:  
  
```sql
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a>Esempio  
 Per eseguire questa stored procedure si utilizzerà codice simile al seguente.  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>Vedere anche

- [stored procedure](stored-procedures.md)
