---
title: Introduzione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 17b014a5a56a2c60359f6fb0b60df29feb97f2a7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529411"
---
# <a name="getting-started"></a>Introduzione
Usando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], è possibile usare il [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] tecnologia per accedere a SQL database esattamente come è possibile accedere a una raccolta in memoria.  
  
 Ad esempio, l'oggetto `nw` nel codice seguente viene creato per rappresentare il database `Northwind`, viene usata `Customers` come tabella di destinazione, le righe vengono filtrate in base a `Customers` residenti a `London` e viene selezionata una stringa da recuperare relativa a `CompanyName`.  
  
 Quando viene eseguito il ciclo, viene recuperata la raccolta di valori `CompanyName`.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>Passaggi successivi  
 Per alcuni esempi aggiuntivi, tra cui inserimento e aggiornamento, vedere [ciò che è possibile eseguire operazioni con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).  
  
 Provare quindi a eseguire alcune procedure dettagliate ed esercitazioni per acquisire un'esperienza pratica relativa all'utilizzo di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Visualizzare [apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).  
  
 Infine, informazioni su come iniziare a usare in autonomia [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto leggendo [passaggi tipici per l'uso di LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [Introduzione a LINQ](https://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
