---
title: Introduzione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 6f9592ecebdaaac7cdec60ce12e99b910275d553
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490061"
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

- [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [Introduzione a LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [Introduzione a LINQ (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
