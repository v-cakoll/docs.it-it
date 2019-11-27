---
title: Dichiarazione e generazione di eventi
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 6f4c303604f9cf55b4ecd500636e0d2772b6234c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345096"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Procedura dettagliata: dichiarazione e generazione di eventi (Visual Basic)
In questa procedura dettagliata viene illustrato come dichiarare e generare eventi per una classe denominata `Widget`. Dopo aver completato i passaggi, è possibile leggere l'argomento complementare, [procedura dettagliata: gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), che Mostra come utilizzare gli eventi di `Widget` oggetti per fornire informazioni sullo stato in un'applicazione.  
  
## <a name="the-widget-class"></a>Classe widget  
 Si supponga nel momento in cui si dispone di una classe di `Widget`. La classe `Widget` dispone di un metodo che può richiedere molto tempo per l'esecuzione e si desidera che l'applicazione sia in grado di inserire un tipo di indicatore di completamento.  
  
 Naturalmente, è possibile fare in modo che l'oggetto `Widget` mostri una finestra di dialogo percentuale di completamento, ma che in ogni progetto in cui è stata usata la classe `Widget` venga bloccata la finestra di dialogo. Un principio efficace della progettazione degli oggetti consiste nel consentire all'applicazione che utilizza un oggetto di gestire l'interfaccia utente, a meno che l'intero scopo dell'oggetto non sia quello di gestire un modulo o una finestra di dialogo.  
  
 Lo scopo di `Widget` consiste nell'eseguire altre attività, quindi è preferibile aggiungere un evento `PercentDone` e lasciare che la procedura che chiama i metodi di `Widget`gestisca tale evento e visualizzi gli aggiornamenti dello stato. L'evento `PercentDone` può inoltre fornire un meccanismo per annullare l'attività.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Per compilare l'esempio di codice per questo argomento  
  
1. Aprire un nuovo progetto di applicazione Windows Visual Basic e creare un modulo denominato `Form1`.  
  
2. Aggiungere due pulsanti e un'etichetta a `Form1`.  
  
3. Assegnare i nomi agli oggetti come illustrato nella tabella seguente.  
  
    |Oggetto|Proprietà|Impostazioni|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Attività di avvio|  
    |`Button2`|`Text`|Cancel|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4. Scegliere **Aggiungi classe** dal menu **progetto** per aggiungere una classe denominata `Widget.vb` al progetto.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Per dichiarare un evento per la classe widget  
  
- Usare la parola chiave `Event` per dichiarare un evento nella classe `Widget`. Si noti che è possibile che un evento includa argomenti `ByVal` e `ByRef`, come illustrato nell'evento `PercentDone` `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Quando l'oggetto chiamante riceve un evento `PercentDone`, l'argomento `Percent` contiene la percentuale dell'attività completata. L'argomento `Cancel` può essere impostato su `True` per annullare il metodo che ha generato l'evento.  
  
> [!NOTE]
> È possibile dichiarare gli argomenti dell'evento nello stesso modo in cui si eseguono gli argomenti delle procedure, con le eccezioni seguenti: gli eventi non possono avere argomenti `Optional` o `ParamArray` e gli eventi non hanno valori restituiti.  
  
 L'evento `PercentDone` viene generato dal metodo `LongTask` della classe `Widget`. `LongTask` accetta due argomenti: il periodo di tempo durante il quale il metodo tende a funzionare e l'intervallo di tempo minimo prima che `LongTask` venga sospeso per generare l'evento di `PercentDone`.  
  
#### <a name="to-raise-the-percentdone-event"></a>Per generare l'evento PercentDone  
  
1. Per semplificare l'accesso alla proprietà `Timer` utilizzata da questa classe, aggiungere un'istruzione `Imports` all'inizio della sezione delle dichiarazioni del modulo della classe, sopra l'istruzione `Class Widget`.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Aggiungere il codice seguente alla classe `Widget` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Quando l'applicazione chiama il metodo `LongTask`, la classe `Widget` genera l'evento `PercentDone` ogni `MinimumInterval` secondi. Quando l'evento viene restituito, `LongTask` verifica se l'argomento `Cancel` è stato impostato su `True`.  
  
 Qui sono necessarie alcune dichiarazioni di non responsabilità. Per semplicità, la procedura `LongTask` presuppone che si conosca in anticipo quanto tempo sarà necessario per l'attività. Questo non è il caso. Suddividere le attività in blocchi di dimensioni pari può essere difficile e spesso ciò che interessa maggiormente agli utenti è semplicemente la quantità di tempo che trascorre prima che venga indicato che si sta verificando qualcosa.  
  
 In questo esempio è possibile che si sia notato un altro difetto. La proprietà `Timer` restituisce il numero di secondi passati dalla mezzanotte. quindi, l'applicazione viene bloccata se viene avviata subito prima della mezzanotte. Un approccio più attento alla misurazione del tempo richiederebbe condizioni di limite, ad esempio in considerazione, oppure evitarle completamente, usando proprietà come `Now`.  
  
 Ora che la classe `Widget` può generare eventi, è possibile passare alla procedura dettagliata successiva. [Procedura dettagliata: gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) illustra come usare `WithEvents` per associare un gestore eventi all'evento `PercentDone`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Procedura dettagliata: Gestione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
