---
title: 'Procedura: risolvere i conflitti mediante l''unione con valori di database'
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
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ee1016a6dc20e58bfafc434617a36f8f8703a3bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a>Procedura: risolvere i conflitti mediante l'unione con valori di database
Per risolvere le differenze tra i valori del database previsti ed effettivi prima del tentativo di inviare di nuovo le modifiche, è possibile usare <xref:System.Data.Linq.RefreshMode.KeepChanges> per unire i valori del database con i valori del membro client corrente. Per ulteriori informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  In tutti i casi, viene innanzitutto aggiornato il record sul client recuperando i dati aggiornati dal database. Questa azione assicura che il successivo tentativo di aggiornamento non avrà esito negativo durante gli stessi controlli di concorrenza.  
  
## <a name="example"></a>Esempio  
 In questo scenario viene generata un'eccezione <xref:System.Data.Linq.ChangeConflictException> quando User1 tenta di inviare le modifiche, in quanto nel frattempo User2 ha modificato le colonne Assistant e Department. Nella tabella seguente è illustrata questa situazione.  
  
||Manager|Assistant|Department|  
|------|-------------|---------------|----------------|  
|Stato del database originale quando viene eseguita una query da User1 e User2.|Alfreds|Maria|Sales|  
|User1 si prepara a inviare queste modifiche.|Alfred||Marketing|  
|User2 ha già inviato queste modifiche.||Mary|Servizio|  
  
 User1 decide di risolvere questo conflitto unendo i valori del database con i valori del membro client corrente. Di conseguenza, i valori del database verranno sovrascritti solo quando il set di modifiche corrente avrà modificato anche quel valore.  
  
 Quando User1 risolve il conflitto usando <xref:System.Data.Linq.RefreshMode.KeepChanges>, il risultato nel database sarà come nella tabella seguente:  
  
||Manager|Assistant|Department|  
|------|-------------|---------------|----------------|  
|Nuovo stato dopo la risoluzione dei conflitti.|Alfred<br /><br /> (da User1)|Mary<br /><br /> (da User2)|Marketing<br /><br /> (da User1)|  
  
 Nell'esempio seguente viene illustrato come unire i valori del database con i valori del membro client corrente, a meno che il client non abbia modificato anche quel valore. Non si verifica alcun conflitto di ispezione o gestione personalizzata dei singoli membri.  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: risolvere i conflitti sovrascrivendo i valori di database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 [Procedura: risolvere i conflitti mantenendo valori di database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 [Procedura: gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
