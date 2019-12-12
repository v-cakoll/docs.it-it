---
title: Flussi di lavoro macchina a stati
ms.date: 03/30/2017
ms.assetid: 344caacd-bf3b-4716-bd5a-eca74fc5a61d
ms.openlocfilehash: e27b9bdc43ec13e90325f5e709c5c97758daa58c
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74710916"
---
# <a name="state-machine-workflows"></a>Flussi di lavoro macchina a stati
Una macchina a stati è un paradigma noto per lo sviluppo di programmi. L'attività <xref:System.Activities.Statements.StateMachine> può essere usata insieme all'oggetto <xref:System.Activities.Statements.State>, <xref:System.Activities.Statements.Transition> e ad altre attività per compilare programmi del flusso di lavoro macchina a stati. In questo argomento viene fornita una panoramica sulla creazione dei flussi di lavoro macchina a stati.  
  
## <a name="state-machine-workflow-overview"></a>Panoramica sul flusso di lavoro macchina a stati  
 I flussi di lavoro macchina a stati forniscono uno stile di modellazione con cui è possibile modellare il flusso di lavoro come se fosse basato sugli eventi. Un'attività <xref:System.Activities.Statements.StateMachine> contiene gli stati e le transizioni che costituiscono la logica della macchina a stati e può essere usata ovunque ne sia possibile l'applicazione. Sono disponibili diverse classi nel runtime della macchina a stati:  
  
- <xref:System.Activities.Statements.StateMachine>  
  
- <xref:System.Activities.Statements.State>  
  
- <xref:System.Activities.Statements.Transition>  
  
 Per creare un flusso di lavoro macchina a stati, gli stati vengono aggiunti a un'attività <xref:System.Activities.Statements.StateMachine> e le transizioni vengono usate per controllare il flusso tra gli stati. Lo screenshot seguente, dal passaggio [Introduzione esercitazione](getting-started-tutorial.md) [procedura: Creare una](how-to-create-a-state-machine-workflow.md)del flusso di lavoro di una macchina a Stati, Mostra un flusso di lavoro della macchina a stati con tre Stati e tre transizioni. **Initialize Target** è lo stato iniziale e rappresenta il primo stato del flusso di lavoro. Viene designato dalla riga che lo conduce dal nodo **iniziale** . Lo stato finale nel flusso di lavoro è denominato **FinalState**e rappresenta il punto in cui il flusso di lavoro viene completato.  
  
 ![Illustrazione che mostra il flusso di lavoro della macchina a stati completato.](./media/state-machine-workflows/complete-state-machine-workflow.jpg)  
  
 In un flusso di lavoro macchina a stati deve essere disponibile un unico stato iniziale e almeno uno stato finale. Ogni stato che non è finale deve disporre di almeno una transizione. Le sezioni seguenti riguardano la creazione e la configurazione degli stati e delle transizioni.  
  
## <a name="creating-and-configuring-states"></a>Creazione e configurazione degli stati  
 Un oggetto <xref:System.Activities.Statements.State> rappresenta uno stato in cui può trovarsi una macchina a stati. Per aggiungere un <xref:System.Activities.Statements.State> a un flusso di lavoro, trascinare l'ActivityDesigner **stato** dalla sezione **macchina a stati** della **casella degli strumenti** e rilasciarlo su un'attività <xref:System.Activities.Statements.StateMachine> sull'area Progettazione flussi di lavoro Windows.  
  
 ![Screenshot della sezione relativa alla macchina a Stati della casella degli strumenti.](./media/state-machine-workflows/state-machine-section-toolbox.jpg)  
  
 Per configurare uno stato come **stato iniziale**, fare clic con il pulsante destro del mouse sullo stato e selezionare **Imposta come stato iniziale**. Inoltre, se non è presente alcuno stato iniziale corrente, lo stato iniziale può essere designato trascinando una linea dal nodo **iniziale** nella parte superiore del flusso di lavoro allo stato desiderato. Quando un'attività <xref:System.Activities.Statements.StateMachine> viene rilasciata nella finestra di progettazione del flusso di lavoro, viene preconfigurata con uno stato iniziale denominato **state1**. In un flusso di lavoro macchina a stati deve essere disponibile un unico stato iniziale.  
  
 Uno stato che rappresenta quello di chiusura in una macchina a stati è denominato stato finale. Uno stato finale è uno stato la cui relativa proprietà <xref:System.Activities.Statements.State.IsFinal%2A> è impostata su `true`, è privo di attività <xref:System.Activities.Statements.State.Exit%2A> e non presenta alcuna transizione che abbia origine da esso. Per aggiungere uno stato finale a un flusso di lavoro, trascinare un ActivityDesigner **FinalState** dalla sezione **macchina a stati** della **casella degli strumenti** e rilasciarlo su un'attività <xref:System.Activities.Statements.StateMachine> sull'area Progettazione flussi di lavoro di Windows. Un flusso di lavoro macchina a stati deve disporre di almeno uno stato finale.  
  
### <a name="configuring-entry-and-exit-actions"></a>Configurazione delle azioni di ingresso e di uscita  
 Uno stato può disporre di un'azione <xref:System.Activities.Statements.State.Entry%2A> e di una <xref:System.Activities.Statements.State.Exit%2A>. Uno stato configurato come finale può disporre solo di un'azione di ingresso. Quando un'istanza del flusso di lavoro passa a uno stato, tutte le attività nell'azione in ingresso vengono eseguite. Quando l'azione di ingresso viene completata, i trigger per le transizioni di stato vengono pianificati. Quando una transizione a un altro stato viene confermata, le attività nell'azione di uscita vengono eseguite, anche se le transizioni di stato tornano allo stesso stato. Al termine dell'azione di uscita, le attività nell'azione della transizione vengono eseguite, quindi si passa al nuovo stato e le relative azioni di ingresso vengono pianificate.  
  
> [!NOTE]
> Durante il debug di un flusso di lavoro macchina a stati, i punti di interruzione possono essere inseriti nell'attività e negli stati della macchina a stati radice all'interno del flusso di lavoro della macchina a stati. È possibile che i punti di interruzione non siano inseriti direttamente nelle transizioni, bensì in tutte le attività contenute all'interno degli stati e delle transizioni.  
  
## <a name="creating-and-configuring-transitions"></a>Creazione e configurazione delle transizioni  
 Tutti gli stati devono disporre di almeno una transizione, ad eccezione di uno stato finale che non può presentare alcuna transizione. Le transizioni possono essere aggiunte dopo l'aggiunta di uno stato al flusso di lavoro macchina a stati. In alternativa, possono essere create quando lo stato viene rilasciato.  
  
 Per aggiungere un <xref:System.Activities.Statements.State> e creare una transizione in un passaggio, trascinare un'attività **stato** dalla sezione **macchina a stati** della **casella degli strumenti** e passarla su un altro stato nella finestra di progettazione del flusso di lavoro. Quando l'oggetto <xref:System.Activities.Statements.State> trascinato si trova su un altro oggetto <xref:System.Activities.Statements.State>, intorno a <xref:System.Activities.Statements.State> verranno visualizzati quattro triangoli. Se l'oggetto <xref:System.Activities.Statements.State> viene rilasciato su uno dei quattro triangoli, viene aggiunto alla macchina a stati e una transizione viene creata dall'oggetto <xref:System.Activities.Statements.State> di origine all'oggetto <xref:System.Activities.Statements.State> di destinazione rilasciato. Per altre informazioni, vedere ActivityDesigner [Transition](/visualstudio/workflow-designer/transition-activity-designer).  
  
 Per creare una transizione dopo l'aggiunta di uno stato sono disponibili due opzioni. La prima consiste nel trascinare lo stato dall'area di progettazione del flusso di lavoro, passarlo su uno stato esistente, quindi rilasciarlo su uno dei punti di trascinamento. Questa operazione è molto simile al metodo descritto nella sezione precedente. È inoltre possibile passare il mouse sullo stato di origine desiderato e tracciare una linea allo stato di destinazione scelto.  
  
> [!NOTE]
> Un singolo stato in una macchina a stati può essere composto da un massimo di 76 transizioni create mediante la finestra di progettazione flussi di lavoro. Il limite alle transizioni per uno stato per i flussi di lavoro creati all'esterno della finestra di progettazione è stabilito solo dalle risorse di sistema.  
  
 Una transizione può disporre delle proprietà <xref:System.Activities.Statements.Transition.Trigger%2A>, <xref:System.Activities.Statements.Transition.Condition%2A> e <xref:System.Activities.Statements.Transition.Action%2A>. La proprietà <xref:System.Activities.Statements.Transition.Trigger%2A> di una transizione viene pianificata al completamento dell'azione <xref:System.Activities.Statements.State.Entry%2A> dello stato di origine della transizione. In genere, la proprietà <xref:System.Activities.Statements.Transition.Trigger%2A> è un'attività in attesa del verificarsi di alcuni tipi di evento, ma può trattarsi di una qualsiasi attività o di nessuna attività. Una volta completata l'attività <xref:System.Activities.Statements.Transition.Trigger%2A>, la proprietà <xref:System.Activities.Statements.Transition.Condition%2A>, se presente, viene valutata. Se non è disponibile alcuna attività <xref:System.Activities.Statements.Transition.Trigger%2A>, viene valutata immediatamente la proprietà <xref:System.Activities.Statements.Transition.Condition%2A>. Se viene restituito `false` dalla condizione, la transizione viene annullata e l'attività <xref:System.Activities.Statements.Transition.Trigger%2A> per tutte le transizioni dallo stato viene ripianificata. Se vi sono altre transizioni che condividono lo stesso stato di origine della transizione corrente, le azioni <xref:System.Activities.Statements.Transition.Trigger%2A> vengono annullate, nonché ripianificate. Se la proprietà <xref:System.Activities.Statements.Transition.Condition%2A> restituisce `true`, o non esiste alcuna condizione, viene eseguita l'azione <xref:System.Activities.Statements.State.Exit%2A> dello stato di origine, quindi viene eseguita la proprietà <xref:System.Activities.Statements.Transition.Action%2A> della transizione. Al termine dell'<xref:System.Activities.Statements.Transition.Action%2A>, il controllo passa allo stato di **destinazione**  
  
 Le transizioni che condividono un trigger comune sono note come transizioni del trigger condivise. Ogni transizione in un gruppo di transizioni del trigger condivise ha lo stesso trigger, ma una proprietà <xref:System.Activities.Statements.Transition.Condition%2A> e un'azione univoche. Per aggiungere altre azioni a una transizione e creare una transizione condivisa, fare clic sul cerchio che indica l'inizio della transizione desiderata e trascinarlo nello stato desiderato. La nuova transizione condividerà uno stesso trigger della transizione iniziale, ma avrà una condizione e un'azione univoche. Le transizioni condivise possono essere create anche dall'interno della finestra di progettazione della transizione facendo clic su **Aggiungi transizione del trigger condiviso** nella parte inferiore della finestra di progettazione della transizione e quindi selezionando lo stato di destinazione desiderato dall'elenco **a discesa stati disponibili per la connessione** .  
  
> [!NOTE]
> Si noti che se <xref:System.Activities.Statements.Transition.Condition%2A> di una transizione restituisce `False` (o tutti gli stati di una transizione trigger condivisa restituiscono `False`), la transizione non si verificherà e tutti i trigger per tutte le transizioni dallo stato verranno rinviati.  
  
 Per ulteriori informazioni sulla creazione di flussi di lavoro della macchina a Stati, vedere [procedura: Creare una](how-to-create-a-state-machine-workflow.md)del flusso di lavoro di una macchina a Stati, ActivityDesigner [StateMachine](/visualstudio/workflow-designer/statemachine-activity-designer), ActivityDesigner [state](/visualstudio/workflow-designer/state-activity-designer), ActivityDesigner [FinalState](/visualstudio/workflow-designer/finalstate-activity-designer)e [ActivityDesigner Transition](/visualstudio/workflow-designer/transition-activity-designer).  
  
## <a name="state-machine-terminology"></a>Terminologia della macchina a stati  
 Contenuto della sezione viene definito il vocabolario della macchina a stati usato in questo argomento.  
  
 State  
 L'unità di base che costituisce una macchina a stati. Una macchina a stati può trovarsi in uno stato in qualsiasi momento particolare.  
  
 Azione di ingresso  
 Un'attività eseguita quando si passa a uno stato.  
  
 Azione di uscita  
 Un'attività eseguita quando si esce da uno stato.  
  
 Transizione  
 Una relazione diretta tra due stati che rappresenta la risposta completa di una macchina a stati al verificarsi di un evento di un tipo particolare.  
  
 Transizione condivisa  
 Una transizione che condivide uno stato e un trigger di origine con una o più transizioni, ma dispone di una condizione e un'azione univoche.  
  
 Trigger  
 Un'attività di trigger che genera una transizione.  
  
 Condizione  
 Un vincolo che deve restituire `true` dopo il verificarsi del trigger affinché la transizione venga completata.  
  
 Azione di transizione  
 Un'attività che viene eseguita quando si effettua una determinata transizione.  
  
 Transizione condizionale  
 Una transizione con una condizione esplicita.  
  
 Transizione autodirezionale  
 Una transizione che passa da uno stato a se stessa.  
  
 Stato iniziale  
 Uno stato che rappresenta il punto iniziale della macchina a stati.  
  
 Stato finale  
 Uno stato che rappresenta il completamento della macchina a stati.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare un flusso di lavoro della macchina a stati](how-to-create-a-state-machine-workflow.md)
- [Activity Designer StateMachine](/visualstudio/workflow-designer/statemachine-activity-designer)
- [Activity Designer State](/visualstudio/workflow-designer/state-activity-designer)
- [Activity Designer FinalState](/visualstudio/workflow-designer/finalstate-activity-designer)
- [Activity Designer Transition](/visualstudio/workflow-designer/transition-activity-designer)
