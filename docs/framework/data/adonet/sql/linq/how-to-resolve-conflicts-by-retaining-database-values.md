---
title: 'Procedura: Risolvere conflitti mantenendo i valori di database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
ms.openlocfilehash: e42f48a188741c3ddff44f6444fa351192c8175f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793340"
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a>Procedura: Risolvere conflitti mantenendo i valori di database
Per risolvere le differenze tra i valori del database previsti ed effettivi prima del tentativo di inviare di nuovo le modifiche, è possibile usare <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> per conservare i valori trovati nel database. I valori correnti nel modello a oggetti vengono quindi sovrascritti. Per ulteriori informazioni, vedere [concorrenza ottimistica: Panoramica](optimistic-concurrency-overview.md).  
  
> [!NOTE]
> In tutti i casi, viene innanzitutto aggiornato il record sul client recuperando i dati aggiornati dal database. Questa azione assicura che il successivo tentativo di aggiornamento non avrà esito negativo durante gli stessi controlli di concorrenza.  
  
## <a name="example"></a>Esempio  
 In questo scenario viene generata un'eccezione <xref:System.Data.Linq.ChangeConflictException> quando User1 tenta di inviare le modifiche, in quanto nel frattempo User2 ha modificato le colonne Assistant e Department. Nella tabella seguente è illustrata questa situazione.  
  
||Manager|Assistant|department|  
|------|-------------|---------------|----------------|  
|Stato del database originale quando viene eseguita una query da User1 e User2.|Alfreds|Maria|Sales|  
|User1 si prepara a inviare queste modifiche.|Alfred||Marketing|  
|User2 ha già inviato queste modifiche.||Mary|Service|  
  
 User1 decide di risolvere questo conflitto sovrascrivendo i valori correnti nel modello a oggetti con i valori del database più recenti.  
  
 Quando User1 risolve il conflitto usando <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, il risultato nel database sarà come nella tabella seguente:  
  
||Manager|Assistant|department|  
|------|-------------|---------------|----------------|  
|Nuovo stato dopo la risoluzione dei conflitti.|Alfreds<br /><br /> (originale)|Mary<br /><br /> (da User2)|Service<br /><br /> (da User2)|  
  
 Nel codice di esempio seguente viene illustrato come sovrascrivere i valori correnti nel modello a oggetti con i valori del database. Non si verificano conflitti di ispezione o gestione personalizzata dei singoli membri.  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Gestione dei conflitti di modifica](how-to-manage-change-conflicts.md)
