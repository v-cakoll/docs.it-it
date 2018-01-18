---
title: 'Procedura: eliminare righe dal database'
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
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f0af9bc56ca3a3dd3128c9f052674343c592fdd8
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-delete-rows-from-the-database"></a>Procedura: eliminare righe dal database
È possibile eliminare righe in un database rimuovendo corrispondente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] oggetti dall'insieme alla tabella correlata. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Converte le modifiche apportate alla SQL appropriate `DELETE` comandi.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non supporta o non riconosce operazioni di eliminazione a catena. Se si desidera eliminare una riga in una tabella contenente vincoli, è necessario effettuare una delle attività seguenti:  
  
-   Impostare la regola `ON DELETE CASCADE` nel vincolo di chiave esterna del database.  
  
-   Usare il codice personalizzato per eliminare prima gli oggetti figlio che impediscono l'eliminazione dell'oggetto padre.  
  
 In caso contrario, viene generata un'eccezione. Vedere il secondo esempio di codice riportato più avanti in questo argomento.  
  
> [!NOTE]
>  È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`. Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] possono adoperare [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per sviluppare stored procedure allo stesso scopo.  
  
 Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind. Per ulteriori informazioni, vedere [procedura: connettersi a un Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### <a name="to-delete-a-row-in-the-database"></a>Per eliminare una riga dal database  
  
1.  Eseguire una query sul database per la riga da eliminare.  
  
2.  Chiamare il metodo <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>.  
  
3.  Inviare le modifiche al database.  
  
## <a name="example"></a>Esempio  
 Nel primo esempio di codice viene eseguita una query sul database per ottenere dettagli relativi all'ordine N. 11000, questi dettagli relativi all'ordine vengono contrassegnati per l'eliminazione e tali modifiche vengono inviate al database.  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a>Esempio  
 Nel secondo esempio, l'obiettivo è l'eliminazione di un ordine (N. 10250). Il codice esamina innanzitutto la tabella `OrderDetails` per verificare se l'ordine da eliminare dispone di elementi figlio. In tal caso, gli elementi figlio e successivamente l'ordine vengono contrassegnati per l'eliminazione. L'oggetto <xref:System.Data.Linq.DataContext> ordina correttamente le eliminazioni effettive in modo che i comandi di eliminazione inviati al database si attengano ai vincoli del database.  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Procedura: assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [Creazione e invio di modifiche dei dati](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
