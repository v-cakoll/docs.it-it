---
title: Operazioni di inserimento, aggiornamento ed eliminazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
ms.openlocfilehash: 7dd2eb64a9320d88c7bc3b5feb6578d70f5910b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503664"
---
# <a name="insert-update-and-delete-operations"></a>Operazioni di inserimento, aggiornamento ed eliminazione
In `Insert` le operazioni `Update`, `Delete`e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono eseguite aggiungendo, modificando e rimuovendo oggetti nel modello a oggetti. Per impostazione predefinita, le azioni vengono convertite da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in SQL e le modifiche vengono inviate al database.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] offre la massima flessibilità per la modifica e rendere persistenti le modifiche apportate agli oggetti. Non appena gli oggetti entità sono disponibili (o recuperandoli tramite una query o costruendoli), è possibile modificarli nell'applicazione come oggetti normali. Vale a dire, è possibile modificarne i valori, è possibile aggiungerli alle raccolte ed è possibile rimuoverli dalle raccolte. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene tenuta traccia delle modifiche, che verranno trasmesse di nuovo al database quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non supporta o non riconosce operazioni di eliminazione a catena. Se si desidera eliminare una riga in una tabella contenente vincoli, è necessario impostare il `ON DELETE CASCADE` regola nel vincolo di chiave esterna nel database o usare il proprio codice per eliminare innanzitutto gli oggetti figlio che impediscono l'eliminazione oggetto padre. In caso contrario, viene generata un'eccezione. Per altre informazioni, vedere [Procedura: Eliminare le righe dal Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
 Nei frammenti di codice riportati di seguito vengono usate le classi `Customer`e `Order` del database di esempio Northwind. Le definizioni di classe non sono illustrate per brevità.  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera automaticamente ed esegue i comandi SQL necessari per trasmettere di nuovo le modifiche al database.  
  
> [!NOTE]
>  È possibile eseguire l'override di questo comportamento usando una logica personalizzata, in genere mediante una stored procedure. Per altre informazioni, vedere [responsabilità di sviluppatore nell'override del comportamento predefinito](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
>   
>  Gli sviluppatori che usano Visual Studio è possono usare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per sviluppare stored procedure per questo scopo.  
  
## <a name="see-also"></a>Vedere anche
- [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
