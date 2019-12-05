---
title: Istruzioni per la migrazione
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 672ed1a93b4409f491d76ffeeaaac5f67a1c4b6e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802609"
---
# <a name="migration-guidance"></a>Istruzioni per la migrazione

Nel .NET Framework 4 Microsoft sta rilasciando la seconda versione principale di Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] è stato rilasciato in WinFX (sono inclusi i tipi negli spazi dei nomi System. Workflow.\*, ora indicati come WF3) e avanzati in .NET Framework 3,5. WF3 fa anche parte del .NET Framework 4, ma esiste insieme alla nuova tecnologia del flusso di lavoro (i tipi negli spazi dei nomi System. Activities.\*, denominati WF4). Quando si considera di usare WF4, è importante innanzitutto tenere presente che si sta controllando il tempo.  
  
- WF3 è una parte completamente supportata del .NET Framework 4.  
  
- Le applicazioni WF3 vengono eseguite in .NET Framework 4 senza modifiche e continuano a essere completamente supportate.  
  
- È possibile creare nuove applicazioni WF3 e le applicazioni esistenti possono essere modificate in Visual Studio 2012 e sono completamente supportate.  
  
 Quindi, la decisione di adottare il .NET Framework 4 è disaccoppiata dalla decisione di passare a WF4 (System. Activities.\*) da WF3 (System. Workflow.\*). In questo argomento vengono forniti i collegamenti al materiale sussidiario per la migrazione di WF che contiene informazioni sull'uso di WF3 e WF4.  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a>Whitepaper e guide di riferimento dettagliate sulla migrazione di WF  
 Nell'argomento [Panoramica della migrazione di WF](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10)) viene fornita una panoramica generale della relazione tra WF3 e WF4 e le strategie di migrazione. Gli argomenti complementari consentono di esaminare argomenti specifici.  
  
 [Panoramica della migrazione di WF](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Viene descritta la relazione tra WF3 e WF4 e le scelte che si possono effettuare in qualità di utente effettivo o potenziale della tecnologia del flusso di lavoro in .NET 4.  
  
 [Migrazione di WF: procedure consigliate per lo sviluppo di WF3](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Viene descritto come progettare gli artefatti WF3 in modo che sia possibile eseguirne facilmente la migrazione a WF4.  
  
 [Linee guida per WF: regole](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Viene illustrato come integrare gli investimenti correlati alle regole nelle soluzioni .NET Framework 4.  
  
 [Linee guida per WF: macchina a Stati](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Viene descritta la modellazione del flusso di controllo di WF4 in assenza di un'attività State-Machine.  
  
 Questo materiale sussidiario si applica solo ai progetti di flusso di lavoro destinati a .NET Framework 4. I flussi di lavoro di macchina a stati sono stati aggiunti in .NET 4.0.1 con la versione Platform Update 1 e sono inclusi come parte di .NET Framework 4.5. Per ulteriori informazioni sui flussi di lavoro della macchina a stati in .NET 4.0.1-4.0.3 e .NET Framework 4,5, vedere l' [aggiornamento di 4.0.1 per le funzionalità di Microsoft .NET Framework 4 e i flussi di](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) [lavoro della macchina a stati](state-machine-workflows.md).  
  
 [Guida di riferimento alla migrazione di WF: attività personalizzate](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Vengono forniti esempi e istruzioni per riprogettare le attività personalizzate di WF3 in WF4.  
  
 [Guida di riferimento alla migrazione di WF: attività personalizzate avanzate](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Fornisce materiale sussidiario per la riprogettazione delle attività personalizzate avanzate WF3 che usano le code WF3 e pianificano attività figlio come attività personalizzate WF4.  
  
 [Guida di riferimento alla migrazione di WF: flussi di lavoro](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Vengono forniti esempi e istruzioni per riprogettare i flussi di lavoro di WF3 in WF4.  
  
 [Guida di riferimento alla migrazione WF: hosting del flusso di lavoro](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Fornisce materiale sussidiario per la riprogettazione del codice di hosting WF3 come codice di hosting WF4. Vengono analizzate le differenze principali dell'hosting di flusso di lavoro tra WF3 e WF4.  
  
 [Guida di riferimento alla migrazione di WF: rilevamento flussi di lavoro](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Fornisce materiale sussidiario per la riprogettazione della configurazione e del codice di rilevamento WF3 usando una configurazione e un codice di rilevamento WF4 equivalenti.  
  
 [Linee guida per WF: servizi flusso di lavoro](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Vengono fornite istruzioni dettagliate orientate all'esempio per la riprogettazione di flussi di lavoro che implementano i servizi Web Windows Communication Foundation (WCF) (comunemente definiti come servizi di flussi di lavoro) creati in WF3 per usare WF4, in scenari comuni di attività predefinite.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Statements.Interop>
