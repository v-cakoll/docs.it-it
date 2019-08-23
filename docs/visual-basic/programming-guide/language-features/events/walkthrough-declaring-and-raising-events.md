---
title: Dichiarazione e generazione di eventi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 20e2b0efbf40597049c515134f408927f18d5603
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956328"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Procedura dettagliata: Dichiarazione e generazione di eventi (Visual Basic)
In questa procedura dettagliata viene illustrato come dichiarare e generare eventi per una `Widget`classe denominata. Al termine della procedura, è possibile leggere l'argomento [complementare: Gestione degli](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)eventi, in cui viene illustrato come utilizzare `Widget` gli eventi degli oggetti per fornire informazioni sullo stato in un'applicazione.  
  
## <a name="the-widget-class"></a>Classe widget  
 Si supponga che nel momento in cui si `Widget` dispone di una classe. La `Widget` classe dispone di un metodo che può richiedere molto tempo per l'esecuzione e si desidera che l'applicazione sia in grado di inserire un tipo di indicatore di completamento.  
  
 Naturalmente, è possibile fare in modo `Widget` che l'oggetto mostri una finestra di dialogo percentuale di completamento, ma in ogni progetto in cui è stata usata la `Widget` classe verrà bloccata la finestra di dialogo. Un principio efficace della progettazione degli oggetti consiste nel consentire all'applicazione che utilizza un oggetto di gestire l'interfaccia utente, a meno che l'intero scopo dell'oggetto non sia quello di gestire un modulo o una finestra di dialogo.  
  
 Lo scopo di `Widget` è quello di eseguire altre attività, quindi è preferibile aggiungere `PercentDone` un evento e consentire alla routine che `Widget`chiama i metodi di gestire l'evento e visualizzare gli aggiornamenti dello stato. L' `PercentDone` evento può inoltre fornire un meccanismo per annullare l'attività.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Per compilare l'esempio di codice per questo argomento  
  
1. Aprire un nuovo progetto di applicazione Windows Visual Basic e creare un modulo `Form1`denominato.  
  
2. Aggiungere due pulsanti e un'etichetta a `Form1`.  
  
3. Assegnare i nomi agli oggetti come illustrato nella tabella seguente.  
  
    |Oggetto|Proprietà|Impostazione|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Attività di avvio|  
    |`Button2`|`Text`|Annulla|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4. Scegliere **Aggiungi classe** dal menu `Widget.vb` **progetto** per aggiungere una classe denominata al progetto.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Per dichiarare un evento per la classe widget  
  
- Usare la `Event` parola chiave per dichiarare un evento `Widget` nella classe. Si noti che un evento può `ByVal` avere `ByRef` argomenti e, `Widget`come `PercentDone` illustrato nell'evento:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Quando l'oggetto chiamante riceve un `PercentDone` evento, l' `Percent` argomento contiene la percentuale dell'attività completata. L' `Cancel` argomento può essere impostato su `True` per annullare il metodo che ha generato l'evento.  
  
> [!NOTE]
> È possibile dichiarare gli argomenti dell'evento nello stesso modo in cui si eseguono gli argomenti delle procedure, con le eccezioni seguenti: Gli eventi non `Optional` possono `ParamArray` avere argomenti o e gli eventi non hanno valori restituiti.  
  
 L' `PercentDone` evento viene generato `LongTask` dal metodo della `Widget` classe. `LongTask`accetta due argomenti: il periodo di tempo durante il quale il metodo tende a funzionare e l'intervallo di tempo minimo prima `LongTask` della pausa per generare l' `PercentDone` evento.  
  
#### <a name="to-raise-the-percentdone-event"></a>Per generare l'evento PercentDone  
  
1. Per semplificare l'accesso alla `Timer` proprietà usata da questa classe, aggiungere un' `Imports` istruzione all'inizio della sezione delle dichiarazioni del modulo della classe, sopra l' `Class Widget` istruzione.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Aggiungere il codice seguente alla classe `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Quando l'applicazione chiama il `LongTask` metodo, la `Widget` classe genera l' `PercentDone` evento ogni `MinimumInterval` secondi. Quando l'evento viene restituito `LongTask` , verifica se l' `Cancel` argomento è stato impostato su `True`.  
  
 Qui sono necessarie alcune dichiarazioni di non responsabilità. Per semplicità, la `LongTask` procedura presuppone che si conosca in anticipo quanto tempo sarà necessario per l'attività. Questo non è il caso. Suddividere le attività in blocchi di dimensioni pari può essere difficile e spesso ciò che interessa maggiormente agli utenti è semplicemente la quantità di tempo che trascorre prima che venga indicato che si sta verificando qualcosa.  
  
 In questo esempio è possibile che si sia notato un altro difetto. La `Timer` proprietà restituisce il numero di secondi passati dalla mezzanotte, quindi l'applicazione viene bloccata se viene avviata immediatamente prima della mezzanotte. Un approccio più attento alla misurazione del tempo richiederebbe condizioni di limite, ad esempio in considerazione, oppure evitarle completamente, usando proprietà `Now`come.  
  
 Ora che la `Widget` classe può generare eventi, è possibile passare alla procedura dettagliata successiva. [Procedura dettagliata: La `WithEvents` ](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) gestionedegli`PercentDone` eventi illustra come usare per associare un gestore eventi all'evento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Procedura dettagliata: Gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
