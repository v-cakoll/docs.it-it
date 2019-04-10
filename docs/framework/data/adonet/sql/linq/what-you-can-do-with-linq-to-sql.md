---
title: Operazioni eseguibili con LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
ms.openlocfilehash: efb7b86c3add99e596e6798c8267c09689899d56
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231578"
---
# <a name="what-you-can-do-with-linq-to-sql"></a>Operazioni eseguibili con LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta tutte le funzionalità principali usate dagli sviluppatori SQL. È possibile creare query per ottenere informazioni ed eseguire operazioni di inserimento, aggiornamento ed eliminazione di dati dalle tabelle.  
  
## <a name="selecting"></a>Selezione  
 Per eseguire una selezione (*proiezione*) è sufficiente scrivere una query [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] nel proprio linguaggio di programmazione e successivamente eseguirla per recuperare i risultati. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tutte le operazioni nelle operazioni SQL necessarie con cui ha dimestichezza indispensabili. Per altre informazioni, vedere [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
 Nell'esempio seguente i nomi di società dei clienti dell'area londinese vengono recuperati e visualizzati nella finestra della console.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a>Inserimento  
 Per eseguire un'operazione `Insert`SQL, aggiungere semplicemente oggetti al modello a oggetti creato e chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> su <xref:System.Data.Linq.DataContext>.  
  
 Nell'esempio seguente vengono aggiunti un nuovo cliente e informazioni sul cliente alla tabella `Customers` usando <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a>Updating  
 Per eseguire un'operazione `Update` per una voce del database, recuperare innanzitutto tale voce e modificarla direttamente nel modello a oggetti. Dopo avere modificato l'oggetto, chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> su <xref:System.Data.Linq.DataContext> per aggiornare il database.  
  
 Nell'esempio seguente vengono recuperati tutti i clienti dell'area londinese. Il nome della città viene quindi modificato da "London" in "London - Metro", infine viene chiamato <xref:System.Data.Linq.DataContext.SubmitChanges%2A> per inviare le modifiche al database.  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a>Eliminazione  
 Per eseguire un'operazione `Delete` per un elemento, rimuovere l'elemento dalla raccolta a cui appartiene, quindi chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> su <xref:System.Data.Linq.DataContext> per eseguire il commit della modifica.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non riconosce operazioni di eliminazione a catena. Se si desidera eliminare una riga in una tabella contenente vincoli, vedere [come: Eliminare le righe dal Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
 Nell'esempio seguente il cliente con il codice `CustomerID` `98128` viene recuperato dal database. Quindi, dopo la conferma che la riga del cliente è stata recuperata, viene chiamato <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> per rimuovere quell'oggetto dalla raccolta. Infine viene chiamato <xref:System.Data.Linq.DataContext.SubmitChanges%2A> per inoltrare l'operazione di eliminazione al database.  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)
- [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Introduzione](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
