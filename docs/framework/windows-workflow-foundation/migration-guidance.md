---
title: Istruzioni di migrazione
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 45f81b29f63701f690e396de2e9834f9933fd775
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796807"
---
# <a name="migration-guidance"></a>Istruzioni di migrazione
[!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]In Microsoft sta rilasciando la seconda versione principale di Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)]è stato rilasciato in WinFX (inclusi i tipi in System. Workflow.\* Namespaces, ora indicati come WF3) e migliorato in. [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] WF3 fa anche parte di [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], ma esiste insieme a una nuova tecnologia del flusso di lavoro (i tipi in System. Activities.\* Namespaces, detti WF4). Quando si considera di usare WF4, è importante innanzitutto tenere presente che si sta controllando il tempo.  
  
- WF3 è una parte integralmente supportata di [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
- Le applicazioni WF3 vengono eseguite in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] senza alcuna modifica e continuano a essere pienamente supportate.  
  
- È possibile creare nuove applicazioni WF3 e le applicazioni esistenti possono essere modificate in Visual Studio 2012 e sono completamente supportate.  
  
 Quindi, la decisione di adottare il .NET Framework 4 è disaccoppiata dalla decisione di passare a WF4 (System. Activities.\*) da WF3 (System. Workflow.\*). In questo argomento vengono forniti i collegamenti al materiale sussidiario per la migrazione di WF che contiene informazioni sull'uso di WF3 e WF4.  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a>Whitepaper e guide di riferimento dettagliate sulla migrazione di WF  
 Nell'argomento [Panoramica della migrazione di WF](https://go.microsoft.com/fwlink/?LinkId=153873) viene fornita una panoramica generale della relazione tra WF3 e WF4 e le strategie di migrazione. Gli argomenti complementari consentono di esaminare argomenti specifici.  
  
 [Panoramica della migrazione di WF](https://go.microsoft.com/fwlink/?LinkId=153873)  
 Viene descritta la relazione tra WF3 e WF4 e le scelte che si possono effettuare in qualità di utente effettivo o potenziale della tecnologia del flusso di lavoro in .NET 4.  
  
 [Migrazione di WF: Procedure consigliate per lo sviluppo di WF3](https://go.microsoft.com/fwlink/?LinkId=153852)  
 Viene descritto come progettare gli artefatti WF3 in modo che sia possibile eseguirne facilmente la migrazione a WF4.  
  
 [Linee guida per WF: Regole](https://go.microsoft.com/fwlink/?LinkId=153854)  
 Viene descritto come visualizzare gli investimenti correlati alle regole nelle soluzioni [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
 [Linee guida per WF: Macchina a Stati](https://go.microsoft.com/fwlink/?LinkId=153855)  
 Viene descritta la modellazione del flusso di controllo di WF4 in assenza di un'attività State-Machine.  
  
 Questo materiale sussidiario si applica solo ai progetti di flusso di lavoro destinati a .NET Framework 4. I flussi di lavoro di macchina a stati sono stati aggiunti in .NET 4.0.1 con la versione Platform Update 1 e sono inclusi come parte di .NET Framework 4.5. Per ulteriori informazioni sui flussi di lavoro della macchina a stati in .NET 4.0.1-4.0.3 e .NET Framework 4,5, vedere l' [aggiornamento di 4.0.1 per le funzionalità di Microsoft .NET Framework 4 e i flussi di](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) [lavoro della macchina a stati](state-machine-workflows.md).  
  
 [Cookbook per la migrazione di WF: Attività personalizzate](https://go.microsoft.com/fwlink/?LinkId=153856)  
 Vengono forniti esempi e istruzioni per riprogettare le attività personalizzate di WF3 in WF4.  
  
 [Cookbook per la migrazione di WF: Attività personalizzate avanzate](https://go.microsoft.com/fwlink/?LinkId=275560)  
 Fornisce materiale sussidiario per la riprogettazione delle attività personalizzate avanzate WF3 che usano le code WF3 e pianificano attività figlio come attività personalizzate WF4.  
  
 [Cookbook per la migrazione di WF: Flussi](https://go.microsoft.com/fwlink/?LinkId=153858)  
 Vengono forniti esempi e istruzioni per riprogettare i flussi di lavoro di WF3 in WF4.  
  
 [Cookbook per la migrazione di WF: Hosting del flusso di lavoro](https://go.microsoft.com/fwlink/?LinkId=275561)  
 Fornisce materiale sussidiario per la riprogettazione del codice di hosting WF3 come codice di hosting WF4. Vengono analizzate le differenze principali dell'hosting di flusso di lavoro tra WF3 e WF4.  
  
 [Cookbook per la migrazione di WF: Rilevamento del flusso di lavoro](https://go.microsoft.com/fwlink/?LinkId=275562)  
 Fornisce materiale sussidiario per la riprogettazione della configurazione e del codice di rilevamento WF3 usando una configurazione e un codice di rilevamento WF4 equivalenti.  
  
 [Linee guida per WF: Servizi flusso di lavoro](https://go.microsoft.com/fwlink/?LinkId=275564)  
 Vengono fornite istruzioni dettagliate orientate all'esempio per la riprogettazione di flussi di lavoro che implementano i servizi Web Windows Communication Foundation (WCF) (comunemente definiti come servizi di flussi di lavoro) creati in WF3 per usare WF4, in scenari comuni di attività predefinite.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Statements.Interop>
