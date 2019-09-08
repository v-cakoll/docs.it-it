---
title: 'Procedura: Specificare quando vengono generate eccezioni di concorrenza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: c0f41d23264bbe5c9130cb5a0b03686331bc92b1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781613"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Procedura: Specificare quando vengono generate eccezioni di concorrenza
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] un'eccezione <xref:System.Data.Linq.ChangeConflictException> viene generata quando gli oggetti non vengono aggiornati a causa di conflitti di concorrenza ottimistici. Per ulteriori informazioni, vedere [concorrenza ottimistica: Panoramica](optimistic-concurrency-overview.md).  
  
 Prima di inviare le modifiche al database, è possibile specificare quando dovranno essere generate le eccezioni di concorrenza:  
  
- Generare l'eccezione al primo errore (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).  
  
- Completare tutti i tentativi di aggiornamento, accumulare tutti gli errori e segnalare gli errori accumulati nell'eccezione (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).  
  
 Quando viene generata, l'eccezione <xref:System.Data.Linq.ChangeConflictException> fornisce l'accesso a una raccolta <xref:System.Data.Linq.ChangeConflictCollection>. In questa raccolta vengono forniti i dettagli per ogni conflitto (associato a un unico tentativo di aggiornamento non riuscito), nonché l'accesso alla raccolta <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>. Per ogni conflitto fra membri viene eseguito il mapping a un unico membro nell'aggiornamento che non ha superato il controllo della concorrenza.  
  
## <a name="example"></a>Esempio  
 Nel codice riportato di seguito vengono illustrati esempi di entrambi i valori.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Gestione dei conflitti di modifica](how-to-manage-change-conflicts.md)
- [Creazione e invio di modifiche dei dati](making-and-submitting-data-changes.md)
