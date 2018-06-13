---
title: Materiale sussidiario di migrazione
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 562ee0913f657b349d88fe7be1627ecd9469f317
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516682"
---
# <a name="migration-guidance"></a>Materiale sussidiario di migrazione
Nel [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], viene rilasciata la seconda versione principale di Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] è stato rilasciato in [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] (inclusi i tipi nei namespace System.Workflow.*, ora definiti WF3) e migliorato in [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. WF3 fa anche parte del [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], ma è presente insieme alla nuova tecnologia del flusso di lavoro (i tipi System. Activities.\* gli spazi dei nomi; definiti WF4). Quando si considera di usare WF4, è importante innanzitutto tenere presente che si sta controllando il tempo.  
  
-   WF3 è una parte integralmente supportata di [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
-   Le applicazioni WF3 vengono eseguite in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] senza alcuna modifica e continuano a essere pienamente supportate.  
  
-   È possibile creare nuove applicazioni WF3, mentre le applicazioni esistenti possono essere modificate in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] con il pieno supporto.  
  
 Di conseguenza, la decisione di adottare .NET Framework 4 è dipende a WF4 (System.Activities.*) da WF3 (System. workflow.\*). In questo argomento vengono forniti i collegamenti al materiale sussidiario per la migrazione di WF che contiene informazioni sull'uso di WF3 e WF4.  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a>Whitepaper e guide di riferimento dettagliate sulla migrazione di WF  
 Il [Cenni preliminari sulla migrazione di WF](http://go.microsoft.com/fwlink/?LinkId=153873) argomento fornisce un'ampia panoramica della relazione tra WF3 e WF4 e migrazione strategie. Gli argomenti complementari consentono di esaminare argomenti specifici.  
  
 [Panoramica della migrazione di WF](http://go.microsoft.com/fwlink/?LinkId=153873)  
 Viene descritta la relazione tra WF3 e WF4 e le scelte che si possono effettuare in qualità di utente effettivo o potenziale della tecnologia del flusso di lavoro in .NET 4.  
  
 [Migrazione di WF: Procedure consigliate per lo sviluppo di WF3](http://go.microsoft.com/fwlink/?LinkId=153852)  
 Viene descritto come progettare gli artefatti WF3 in modo che sia possibile eseguirne facilmente la migrazione a WF4.  
  
 [Materiale sussidiario per WF: regole](http://go.microsoft.com/fwlink/?LinkId=153854)  
 Viene descritto come visualizzare gli investimenti correlati alle regole nelle soluzioni [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
 [Materiale sussidiario per WF: Macchina a stati](http://go.microsoft.com/fwlink/?LinkId=153855)  
 Viene descritta la modellazione del flusso di controllo di WF4 in assenza di un'attività State-Machine.  
  
 Questo materiale sussidiario si applica solo ai progetti di flusso di lavoro destinati a .NET Framework 4. I flussi di lavoro di macchina a stati sono stati aggiunti in .NET 4.0.1 con la versione Platform Update 1 e sono inclusi come parte di .NET Framework 4.5. Per ulteriori informazioni sui flussi di lavoro macchina stati in .NET 4.0.1 - 4.0.3 e .NET Framework 4.5, vedere [aggiornamento 4.0.1 per Microsoft .NET Framework 4 funzioni](http://msdn.microsoft.com/library/de3297bd-c3e1-4126-95be-2ed7fe2a98fc) e [flussi di lavoro macchina stato](../../../docs/framework/windows-workflow-foundation/state-machine-workflows.md).  
  
 [Migrazioni di WF: Attività personalizzate](http://go.microsoft.com/fwlink/?LinkId=153856)  
 Vengono forniti esempi e istruzioni per riprogettare le attività personalizzate di WF3 in WF4.  
  
 [Migrazioni di WF: Attività personalizzate avanzate](http://go.microsoft.com/fwlink/?LinkId=275560)  
 Fornisce materiale sussidiario per la riprogettazione delle attività personalizzate avanzate WF3 che usano le code WF3 e pianificano attività figlio come attività personalizzate WF4.  
  
 [Migrazioni di WF: flussi di lavoro](http://go.microsoft.com/fwlink/?LinkId=153858)  
 Vengono forniti esempi e istruzioni per riprogettare i flussi di lavoro di WF3 in WF4.  
  
 [Istruzioni per la migrazione di WF: Hosting del flusso di lavoro](http://go.microsoft.com/fwlink/?LinkId=275561)  
 Fornisce materiale sussidiario per la riprogettazione del codice di hosting WF3 come codice di hosting WF4. Vengono analizzate le differenze principali dell'hosting di flusso di lavoro tra WF3 e WF4.  
  
 [WF migrazioni: Rilevamento del flusso di lavoro](http://go.microsoft.com/fwlink/?LinkId=275562)  
 Fornisce materiale sussidiario per la riprogettazione della configurazione e del codice di rilevamento WF3 usando una configurazione e un codice di rilevamento WF4 equivalenti.  
  
 [Materiale sussidiario per WF: Servizi di flusso di lavoro](http://go.microsoft.com/fwlink/?LinkId=275564)  
 Vengono fornite istruzioni dettagliate orientate all'esempio per la riprogettazione di flussi di lavoro che implementano i servizi Web Windows Communication Foundation (WCF) (comunemente definiti come servizi di flussi di lavoro) creati in WF3 per usare WF4, in scenari comuni di attività predefinite.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Activities.Statements.Interop>
