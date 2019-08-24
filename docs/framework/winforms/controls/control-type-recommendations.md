---
title: Consigli sui tipi di controlli
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- user controls [Windows Forms], when to use
- custom controls [Windows Forms], types
- controls [Windows Forms], creating
ms.assetid: 5235fe9d-c36a-4c08-ae76-6cb90b50085e
ms.openlocfilehash: fba10de27f7ba6f4c799d2110acd87394b7dbc95
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015991"
---
# <a name="control-type-recommendations"></a>Consigli sui tipi di controlli

.NET Framework offre funzionalità per sviluppare e implementare nuovi controlli. Oltre al tradizionale controllo utente, ora è possibile scrivere controlli personalizzati che eseguono il proprio disegno e possono anche estendere le funzionalità dei controlli esistenti tramite l'ereditarietà. Decidere quale tipo di controllo creare può generare confusione. Questa sezione evidenzia le differenze tra i vari tipi di controlli che offrono opzioni di ereditarietà e fornisce considerazioni sul tipo da scegliere per il progetto.

> [!NOTE]
> Per creare un controllo da usare nei Web Form, vedere [Sviluppo di controlli server ASP.NET personalizzati](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).

## <a name="inheriting-from-a-windows-forms-control"></a>Eredità da un controllo di Windows Form

È possibile derivare un controllo ereditato da un controllo di Windows Form esistente. Questo approccio consente di mantenere tutte le funzionalità intrinseche di un controllo di Windows Form ed estenderle mediante l'aggiunta di proprietà personalizzate, metodi o altre funzionalità. Ad esempio, è possibile creare un controllo derivato da <xref:System.Windows.Forms.TextBox> che accetta solo numeri e converte automaticamente l'input in un valore. Un controllo di questo tipo potrebbe contenere un codice di convalida chiamato a ogni modifica del testo nella casella di testo e potrebbe avere una proprietà aggiuntiva, Valore. In alcuni controlli è possibile aggiungere anche un aspetto personalizzato per l'interfaccia grafica del controllo eseguendo l'override del metodo <xref:System.Windows.Forms.Control.OnPaint%2A> della classe base.

 Ereditare da un controllo di Windows Form se:

- Molte delle funzionalità necessarie sono identiche a quelle incluse in un controllo di Windows Form esistente.

- Non è necessaria un'interfaccia grafica personalizzata oppure si vuole progettare un nuovo front-end grafico per un controllo esistente.

## <a name="inheriting-from-the-usercontrol-class"></a>Eredità dalla classe UserControl

Un controllo utente è una raccolta di controlli di Windows Form incapsulata in un contenitore comune. Il contenitore include tutte le funzionalità intrinseche associate a ciascun controllo di Windows Form e consente di esporre e associare in modo selettivo le relative proprietà. Un esempio di controllo utente potrebbe essere un controllo compilato per la visualizzazione dei dati dell'indirizzo del cliente da un database. Questo controllo include diverse caselle di testo per visualizzare tutti i campi e diversi pulsanti per spostarsi tra i record. Le proprietà di data binding possono essere esposte in modo selettivo e l'intero controllo può essere incluso in un pacchetto e riusato nelle diverse applicazioni.

Ereditare dalla classe <xref:System.Windows.Forms.UserControl> per:

- Combinare le funzionalità di vari controlli di Windows Form in una singola unità riusabile.

## <a name="inheriting-from-the-control-class"></a>Eredità dalla classe Control

Un altro metodo per creare un controllo consiste nel crearne uno praticamente dal nulla mediante eredità da <xref:System.Windows.Forms.Control>. La classe <xref:System.Windows.Forms.Control> fornisce tutte le funzionalità di base richieste dai controlli (ad esempio, gli eventi), ma nessuna funzionalità specifica del controllo o interfacce grafiche. La creazione di un controllo mediante eredità dalla classe <xref:System.Windows.Forms.Control> è molto più complesso in termini di elaborazione e di passaggi da eseguire rispetto a un controllo ereditato da un controllo utente o da un controllo di Windows Form esistente. L'autore deve scrivere un codice per l'evento <xref:System.Windows.Forms.Control.OnPaint%2A> del controllo, nonché altri codici specifici per le funzionalità necessarie. Tuttavia, questo metodo permette una maggiore flessibilità e la possibilità di personalizzare il controllo per soddisfare completamente le esigenze dell'utente. Un esempio di controllo personalizzato è un controllo clock che duplica l'aspetto e il funzionamento di un orologio analogico. Viene richiamato un disegno personalizzato che causa il movimento delle lancette dell'orologio in risposta ad eventi <xref:System.Windows.Forms.Timer.Tick> provenienti da un componente timer interno.

Ereditare dalla classe <xref:System.Windows.Forms.Control> per:

- Fornire una rappresentazione grafica personalizzata del controllo.

- È necessario implementare una funzionalità personalizzata non disponibile tramite i controlli standard.

## <a name="related-articles"></a>Articoli correlati

- [Procedura: Visualizza un controllo nella finestra di dialogo Scegli elementi della casella degli strumenti](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [Procedura dettagliata: Serializzazione di raccolte di tipi standard con DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)

- [Procedura dettagliata: Eredità da un controllo Windows Forms](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [Procedura: Specificare una bitmap della casella degli strumenti per un controllo](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [Procedura: Ereditare da controlli Windows Forms esistenti](how-to-inherit-from-existing-windows-forms-controls.md)

- [Procedura dettagliata: Debug di controlli di Windows Form personalizzati in fase di progettazione](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [Procedura: Ereditare dalla classe Control](how-to-inherit-from-the-control-class.md)

- [Procedura: Testare il comportamento in fase di esecuzione di un UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [Procedura: Allineare un controllo ai bordi dei form in fase di progettazione](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [Procedura: Ereditare dalla classe UserControl](how-to-inherit-from-the-usercontrol-class.md)

- [Procedura: Controlli autore per Windows Forms](how-to-author-controls-for-windows-forms.md)

- [Procedura: Crea controlli compositi](how-to-author-composite-controls.md)

- [Procedura dettagliata: Creazione di un controllo composito](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [Procedura dettagliata: Creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md)

- [Procedura: Creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))

## <a name="see-also"></a>Vedere anche

- [Procedura: Sviluppare un controllo Windows Forms semplice](how-to-develop-a-simple-windows-forms-control.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
