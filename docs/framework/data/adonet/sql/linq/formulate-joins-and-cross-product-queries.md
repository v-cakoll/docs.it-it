---
title: Formulare query su prodotto incrociato e join
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 002a644ff5d48b25351228dcd74330707491d6c8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782085"
---
# <a name="formulate-joins-and-cross-product-queries"></a>Formulare query su prodotto incrociato e join
Negli esempi riportati di seguito viene illustrato come combinare risultati da più tabelle.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la navigazione con chiave `From` esterna nella clausola in`from` Visual Basic ( C#clausola in) per selezionare tutti gli ordini per i clienti di Londra.  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la navigazione con chiave `Where` esterna nella clausola in`where` Visual Basic ( C#clausola in) per filtrare per l'esaurimento `Products` delle `Supplier` scorte il cui oggetto si trova nel Stati Uniti.  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la navigazione con chiave `From` esterna nella clausola in`from` Visual Basic ( C#clausola in) per filtrare i dipendenti a Seattle e per elencarne i territori.  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la navigazione con chiave `Select` esterna nella clausola in`select` Visual Basic ( C#clausola in) per filtrare le coppie di dipendenti in cui un dipendente segnala l'altro e il punto in cui entrambi `City`i dipendenti sono dallo stesso.  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio di Visual Basic seguente viene eseguita la ricerca di tutti i clienti e gli ordini, verifica che gli ordini vengano abbinati ai clienti e garantisce che per ogni cliente nell'elenco venga fornito un nome di contatto.  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono unite in join in modo esplicito due tabelle e vengono proiettati i risultati da entrambe le tabelle.  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono unite in join in modo esplicito tre tabelle e vengono proiettati i risultati da ogni tabella.  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come ottenere `LEFT OUTER JOIN` usando `DefaultIfEmpty()`. Il metodo `DefaultIfEmpty()` restituisce null se non è presente alcun `Order` per `Employee`.  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene proiettata l'espressione `let` risultante da un join.  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un `join` con una chiave composita.  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene descritto come costruire un `join` in cui un solo lato è nullable.  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di query](query-examples.md)
