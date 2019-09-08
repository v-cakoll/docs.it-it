---
title: 'Procedura: Visualizzare un insieme di modifiche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: 5f49e123e6e980501d330eeecf2719023cdff8e7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781972"
---
# <a name="how-to-display-a-changeset"></a>Procedura: Visualizzare un insieme di modifiche
È possibile visualizzare modifiche registrate da <xref:System.Data.Linq.DataContext> usando <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono recuperati i clienti la cui città di residenza è London, la città viene modificata in Paris, quindi le modifiche vengono inviate di nuovo al database.  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 L'output generato da questo codice è analogo al seguente: Notare che il riepilogo alla fine dell'output indica che sono state apportate otto modifiche.  

 ```console
CustomerID: AROUT
   Original value: London
   Updated value: Paris
CustomerID: BSBEV
   Original value: London
   Updated value: Paris
CustomerID: CONSH
   Original value: London
   Updated value: Paris
CustomerID: EASTC
   Original value: London
   Updated value: Paris
CustomerID: NORTS
    Original value: London
    Updated value: Paris
CustomerID: PARIS
    Original value: London
    Updated value: Paris
CustomerID: SEVES
    Original value: London
    Updated value: Paris
CustomerID: SPECD
    Original value: London
    Updated value: Paris
Total changes: {Added: 0, Removed: 0, Modified: 8}
```
  
## <a name="see-also"></a>Vedere anche

- [Supporto per il debug](debugging-support.md)
