---
title: Restituire il valore medio da una sequenza numerica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee3b8673-a2e7-4b2d-9b5c-4972ff9e665d
ms.openlocfilehash: 38b1b3ba2bd2116621de820855bb4e4b2cd12915
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519162"
---
# <a name="return-the-average-value-from-a-numeric-sequence"></a>Restituire il valore medio da una sequenza numerica
L'operatore <xref:System.Linq.Enumerable.Average%2A> calcola la media di una sequenza di valori numerici.  
  
> [!NOTE]
>  La conversione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di `Average` di valori integer viene calcolata come un valore integer, non come un valore double.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene restituita la media dei valori `Freight` nella tabella `Orders`.  
  
 Il risultato restituito dal database Northwind di esempio sarà `78.2442`.  
  
 [!code-csharp[DLinqQueryExamples#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#1)]
 [!code-vb[DLinqQueryExamples#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#1)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene restituito il prezzo unitario medio di tutti i valori `Products` nella tabella `Products`.  
  
 Il risultato restituito dal database Northwind di esempio sarà `28.8663`.  
  
 [!code-csharp[DLinqQueryExamples#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#2)]
 [!code-vb[DLinqQueryExamples#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#2)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `Average` per trovare i valori `Products` il cui prezzo unitario è maggiore del prezzo unitario medio della categoria a cui appartengono tali prodotti. Nell'esempio i risultati vengono visualizzati in gruppi.  
  
 Notare che in questo esempio è richiesto l'uso della parola chiave `var` in C#, perché il tipo restituito è anonimo.  
  
 [!code-csharp[DLinqQueryExamples#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#3)]
 [!code-vb[DLinqQueryExamples#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#3)]  
  
 Se si esegue questa query sul database di esempio Northwind, i risultati saranno simili ai seguenti:  
  
 `1`  
  
 `Côte de Blaye`  
  
 `Ipoh Coffee`  
  
 `2`  
  
 `Grandma's Boysenberry Spread`  
  
 `Northwoods Cranberry Sauce`  
  
 `Sirop d'érable`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `Gumbär Gummibärchen`  
  
 `Schoggi Schokolade`  
  
 `Tarte au sucre`  
  
 `4`  
  
 `Queso Manchego La Pastora`  
  
 `Mascarpone Fabioli`  
  
 `Raclette Courdavault`  
  
 `Camembert Pierrot`  
  
 `Gudbrandsdalsost`  
  
 `Mozzarella di Giovanni`  
  
 `5`  
  
 `Gustaf's Knäckebröd`  
  
 `Gnocchi di nonna Alice`  
  
 `Wimmers gute Semmelknödel`  
  
 `6`  
  
 `Mishi Kobe Niku`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Rössle Sauerkraut`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Ikura`  
  
 `Carnarvon Tigers`  
  
 `Nord-Ost Matjeshering`  
  
 `Gravad lax`  
  
## <a name="see-also"></a>Vedere anche
- [Query di aggregazione](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)
