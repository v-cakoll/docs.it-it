---
title: Attività del flusso di controllo in WF
description: Questo articolo riepiloga le attività .NET Framework 4.6.1 per controllare il flusso di esecuzione all'interno di un flusso di lavoro.
ms.date: 03/30/2017
ms.assetid: 6892885b-f7c5-4aea-8f5e-28863fb4ae75
ms.openlocfilehash: 18ff982d3f215e3fd46108eb2411f3d1a5ab9745
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420071"
---
# <a name="control-flow-activities-in-wf"></a>Attività del flusso di controllo in WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] offre diverse attività per il controllo del flusso di esecuzione all'interno di un flusso di lavoro. Alcune di queste attività (ad esempio `Switch` e `If` ) implementano strutture di controllo del flusso simili a quelle degli ambienti di programmazione come Visual C#, mentre altre, ad esempio, `Pick` modellano nuove strutture di programmazione.  
  
 Si noti che mentre attività quali `Parallel` e `ParallelForEach` pianificano l'esecuzione di più attività figlio contemporaneamente, per un flusso di lavoro viene usato un solo thread. Ogni attività figlio di queste attività viene eseguita in sequenza e le attività successive non vengono eseguite fino a quando le attività precedenti non vengono completate o non diventano inattive. Di conseguenza, queste attività sono molto utili per applicazioni nelle quali diverse attività potenzialmente di blocco devono essere eseguite in un modo caratterizzato da interfoliazione. Se nessuna delle attività figlio di queste attività diventa inattiva, un'attività `Parallel` viene eseguita come un'attività `Sequence` e un'attività `ParallelForEach` viene eseguita come un'attività `ForEach`. Se, tuttavia, vengono usate attività asincrone (come le attività che derivano da <xref:System.Activities.AsyncCodeActivity>) o attività di messaggistica, il controllo passa al branch successivo mentre l'attività figlio attende la ricezione del messaggio o il completamento del relativo lavoro asincrono.  
  
## <a name="flow-control-activities"></a>Attività di controllo del flusso  
  
|Attività|Descrizione|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.DoWhile>|Esegue una volta le attività contenute e continua mentre una condizione è `true`.|  
|<xref:System.Activities.Statements.ForEach%601>|Esegue un'istruzione incorporata in sequenza per ogni elemento in una raccolta. <xref:System.Activities.Statements.ForEach%601> è simile alla parola chiave `foreach`, ma viene implementato come un'attività piuttosto che un'istruzione di linguaggio.|  
|<xref:System.Activities.Statements.If>|Esegue le attività contenute se una condizione è `true` e può eseguire attività contenute nella proprietà <xref:System.Activities.Statements.If.Else%2A> se la condizione è `false`.|  
|<xref:System.Activities.Statements.Parallel>|Esegue attività contenute in parallelo.|  
|<xref:System.Activities.Statements.ParallelForEach%601>|Esegue un'istruzione incorporata in parallelo per ogni elemento in una raccolta.|  
|<xref:System.Activities.Statements.Pick>|Fornisce modellazione del flusso di controllo basato sull'evento.|  
|<xref:System.Activities.Statements.PickBranch>|Rappresenta un percorso potenziale di esecuzione in un'attività <xref:System.Activities.Statements.Pick>.|  
|<xref:System.Activities.Statements.Sequence>|Esegue attività contenute in sequenza.|  
|<xref:System.Activities.Statements.Switch%601>|Seleziona una scelta da un numero di attività da eseguire, in base al valore di una determinata espressione.|  
|<xref:System.Activities.Statements.While>|Esegue le attività contenute mentre una condizione è `true`.|
