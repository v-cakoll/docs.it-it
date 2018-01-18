---
title: Operazioni di inserimento, aggiornamento ed eliminazione
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
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 51af1dad545f6ac948b17d1bdbd39bfc688c7f11
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="insert-update-and-delete-operations"></a>Operazioni di inserimento, aggiornamento ed eliminazione
In `Insert` le operazioni `Update`, `Delete`e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono eseguite aggiungendo, modificando e rimuovendo oggetti nel modello a oggetti. Per impostazione predefinita, le azioni vengono convertite da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in SQL e le modifiche vengono inviate al database.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]offre la massima flessibilità per la modifica e salvare le modifiche apportate agli oggetti in modo permanente. Non appena gli oggetti entità sono disponibili (in recuperandoli tramite una query o costruendoli), è possibile modificarle in un'applicazione come oggetti normali. Vale a dire, è possibile modificare i relativi valori, è possibile aggiungerli alle raccolte e rimuoverli dalle raccolte. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene tenuta traccia delle modifiche, che verranno trasmesse di nuovo al database quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non supporta o non riconosce operazioni di eliminazione a catena. Se si desidera eliminare una riga in una tabella contenente vincoli, è necessario impostare il `ON DELETE CASCADE` regola nel vincolo di chiave esterna nel database o utilizzare il proprio codice per eliminare prima gli oggetti figlio che impediscono l'eliminazione oggetto padre. In caso contrario, viene generata un'eccezione. Per ulteriori informazioni, vedere [procedura: eliminare righe dal Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
 Nei frammenti di codice riportati di seguito vengono usate le classi `Customer`e `Order` del database di esempio Northwind. Le definizioni di classe non sono illustrate per brevità.  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera automaticamente ed esegue i comandi SQL necessari per trasmettere di nuovo le modifiche al database.  
  
> [!NOTE]
>  È possibile eseguire l'override di questo comportamento usando una logica personalizzata, in genere mediante una stored procedure. Per ulteriori informazioni, vedere [responsabilità dello sviluppatore nell'override del comportamento predefinito](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
>   
>  Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] possono adoperare [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per sviluppare stored procedure a questo scopo.  
  
## <a name="see-also"></a>Vedere anche  
 [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
