---
title: Tipi di controlli personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.assetid: 3cea09e5-4344-4ccb-9858-b66ccac210ff
ms.openlocfilehash: 106da550fc6e6c50bc40e103e1f855059a9ffa9c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950098"
---
# <a name="varieties-of-custom-controls"></a>Tipi di controlli personalizzati
Con .NET Framework è possibile sviluppare e implementare nuovi controlli. Si possono estendere le funzionalità del controllo utente con cui si ha dimestichezza nonché dei controlli esistenti attraverso l'ereditarietà. È anche possibile scrivere controlli personalizzati che eseguono il proprio disegno.  
  
 Decidere quale tipo di controllo creare può generare confusione. In questo argomento vengono evidenziate le differenze tra i vari tipi di controlli da cui è possibile ereditare e sono riportate informazioni su come scegliere un particolare tipo di controllo per il progetto.  
  
> [!NOTE]
> Per informazioni sulla creazione di un controllo da usare nei Web Form, vedere [Sviluppo di controlli server ASP.NET personalizzati](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).  
  
## <a name="base-control-class"></a>Classe di base del controllo  
 La <xref:System.Windows.Forms.Control> classe è la classe base per i controlli Windows Forms. Offre l'infrastruttura necessaria per la visualizzazione nelle applicazioni Windows Form.  
  
 La <xref:System.Windows.Forms.Control> classe esegue le attività seguenti per fornire la visualizzazione visiva nelle applicazioni Windows Forms:  
  
- Espone un handle di finestra.  
  
- Gestisce il routing dei messaggi.  
  
- Genera gli eventi di mouse e tastiera e molti altri eventi dell'interfaccia utente.  
  
- Genera le funzionalità di layout avanzate.  
  
- Contiene molte proprietà <xref:System.Windows.Forms.Control.ForeColor%2A>specifiche per la visualizzazione visiva, ad esempio <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.Height%2A>,, e <xref:System.Windows.Forms.Control.Width%2A>.  
  
- Offre la protezione e il supporto del threading necessari affinché un controllo Windows Form funzioni come un controllo Microsoft® ActiveX®.  
  
 Poiché gran parte dell'infrastruttura viene definita dalla classe di base, è relativamente semplice sviluppare i propri controlli Windows Form.  
  
## <a name="kinds-of-controls"></a>Tipi di controlli  
 Windows Form supporta tre tipi di controlli definiti dall'utente: *composito*, *esteso* e *personalizzato*. Le sezioni seguenti descrivono ogni tipo di controllo e contengono suggerimenti utili per la scelta del tipo di controllo da usare nei propri progetti.  
  
### <a name="composite-controls"></a>Controlli compositi  
 Un controllo composito è una raccolta di controlli Windows Form incapsulata in un contenitore comune. Questo tipo di controllo viene talvolta definito *controllo utente*. I controlli contenuti vengono chiamati *controlli costitutivi*.  
  
 Un controllo composito include tutte le funzionalità intrinseche associate a ogni controllo Windows Form contenuto e consente di esporre e associare in modo selettivo le relative proprietà. Un controllo composito mette inoltre a disposizione numerose funzionalità predefinite di gestione della tastiera senza richiedere ulteriori operazioni di sviluppo.  
  
 Ad esempio, un controllo composito potrebbe essere compilato per visualizzare i dati dell'indirizzo del cliente da un database. Questo controllo può includere un <xref:System.Windows.Forms.DataGridView> controllo per visualizzare i campi del database, <xref:System.Windows.Forms.BindingSource> un oggetto per gestire l'associazione a un'origine dati <xref:System.Windows.Forms.BindingNavigator> e un controllo per spostarsi tra i record. È possibile esporre le proprietà di data binding in modo selettivo, nonché includere l'intero controllo in un pacchetto e riusarlo nelle diverse applicazioni. Per un esempio di questo tipo di controllo composito, [vedere Procedura: Applicare gli attributi nei controlli](how-to-apply-attributes-in-windows-forms-controls.md)Windows Forms.  
  
 Per creare un controllo composito, derivare <xref:System.Windows.Forms.UserControl> dalla classe. La <xref:System.Windows.Forms.UserControl> classe base fornisce il routing della tastiera per i controlli figlio e consente ai controlli figlio di funzionare come un gruppo. Per altre informazioni, vedere [Sviluppo di un controllo Windows Form composito](developing-a-composite-windows-forms-control.md).  
  
 **Consigli**  
  
 Ereditare dalla classe <xref:System.Windows.Forms.UserControl> per:  
  
- Combinare le funzionalità di vari controlli di Windows Form in una singola unità riusabile.  
  
### <a name="extended-controls"></a>Controlli estesi  
 È possibile derivare un controllo ereditato da un controllo di Windows Form esistente. Questo approccio consente di mantenere tutte le funzionalità intrinseche di un controllo Windows Form e di estenderle aggiungendo proprietà personalizzate, metodi o altre funzionalità. Con questa opzione è possibile eseguire l'override della logica di disegno del controllo di base e quindi estendere la relativa interfaccia utente modificandone l'aspetto.  
  
 Ad esempio, è possibile creare un controllo derivato dal controllo <xref:System.Windows.Forms.Button> che tiene traccia del numero di volte in cui un utente ha fatto clic su di esso.  
  
 In alcuni controlli è inoltre possibile aggiungere un aspetto personalizzato all'interfaccia utente grafica del controllo eseguendo l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base. Per un pulsante esteso che tiene traccia dei clic, è possibile <xref:System.Windows.Forms.Control.OnPaint%2A> eseguire l'override del metodo per chiamare <xref:System.Windows.Forms.Control.OnPaint%2A>l'implementazione di base di, quindi tracciare il conteggio dei <xref:System.Windows.Forms.Button> clic in un angolo dell'area client del controllo.  
  
 **Consigli**  
  
 Ereditare da un controllo di Windows Form se:  
  
- Molte delle funzionalità necessarie sono identiche a quelle incluse in un controllo di Windows Form esistente.  
  
- Non è necessaria un'interfaccia utente grafica personalizzata oppure si vuole progettare una nuova interfaccia utente grafica per un controllo esistente.  
  
### <a name="custom-controls"></a>Controlli personalizzati  
 Un altro modo per creare un controllo consiste nel crearne uno sostanzialmente dall'inizio ereditando da <xref:System.Windows.Forms.Control>. La <xref:System.Windows.Forms.Control> classe fornisce tutte le funzionalità di base richieste dai controlli, inclusi gli eventi di gestione del mouse e della tastiera, ma nessuna funzionalità specifica del controllo o un'interfaccia grafica.  
  
 La creazione di un controllo mediante l' <xref:System.Windows.Forms.Control> ereditarietà dalla classe richiede un maggior numero di pensieri e sforzi rispetto a ereditare da o da <xref:System.Windows.Forms.UserControl> un controllo Windows Forms esistente. Poiché gran parte dell'implementazione spetta all'utente, il controllo può avere maggiore flessibilità rispetto a un controllo composito o esteso ed è possibile personalizzarlo in modo da soddisfare le esigenze specifiche.  
  
 Per implementare un controllo personalizzato, è necessario scrivere il codice per <xref:System.Windows.Forms.Control.OnPaint%2A> l'evento del controllo, nonché qualsiasi codice specifico della funzionalità necessario. È anche possibile eseguire l' <xref:System.Windows.Forms.Control.WndProc%2A> override del metodo e gestire direttamente i messaggi di Windows. Questo è il modo più potente di creare un controllo, ma per usare questa tecnica in modo efficace, è necessario avere familiarità con l'API Microsoft Win32®.  
  
 Un esempio di controllo personalizzato è un controllo clock che duplica l'aspetto e il funzionamento di un orologio analogico. Il disegno personalizzato viene richiamato per fare in modo che le lancette dell'orologio <xref:System.Windows.Forms.Timer.Tick> si sposti in risposta <xref:System.Windows.Forms.Timer> a eventi di un componente interno. Per altre informazioni, vedere [Procedura: Sviluppare un semplice controllo](how-to-develop-a-simple-windows-forms-control.md)Windows Forms.  
  
 **Consigli**  
  
 Ereditare dalla classe <xref:System.Windows.Forms.Control> per:  
  
- Fornire una rappresentazione grafica personalizzata del controllo.  
  
- È necessario implementare una funzionalità personalizzata non disponibile tramite i controlli standard.  
  
### <a name="activex-controls"></a>Controlli ActiveX  
 Anche se l'infrastruttura di Windows Form è stata ottimizzata per ospitare i controlli Windows Form, è comunque possibile usare i controlli ActiveX. Questa attività è supportata in Visual Studio. Per altre informazioni, vedere [Procedura: Aggiungere controlli ActiveX a Windows Forms](how-to-add-activex-controls-to-windows-forms.md).  
  
### <a name="windowless-controls"></a>Controlli senza finestra  
 Le tecnologie Microsoft Visual Basic® 6.0 e ActiveX supportano i controlli *senza finestra*. I controlli senza finestra non sono supportati in Windows Form.  
  
## <a name="custom-design-experience"></a>Esperienza di progettazione personalizzata  
 Se è necessario implementare una soluzione personalizzata in fase di progettazione, è possibile creare una propria finestra di progettazione. Per i controlli compositi, derivare la classe della <xref:System.Windows.Forms.Design.ParentControlDesigner> finestra di <xref:System.Windows.Forms.Design.DocumentDesigner> progettazione personalizzata dalle classi o. Per i controlli estesi e personalizzati, derivare la classe della <xref:System.Windows.Forms.Design.ControlDesigner> finestra di progettazione personalizzata dalla classe.  
  
 <xref:System.ComponentModel.DesignerAttribute> Usare per associare il controllo alla finestra di progettazione. Per ulteriori informazioni, vedere [estensione del supporto in fase](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)) di [progettazione e procedura: Creare un controllo Windows Forms che sfrutta le funzionalità](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))della fase di progettazione.  
  
## <a name="see-also"></a>Vedere anche

- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
- [Procedura: Sviluppare un controllo Windows Forms semplice](how-to-develop-a-simple-windows-forms-control.md)
- [Sviluppo di un controllo di Windows Form composto](developing-a-composite-windows-forms-control.md)
- [Estensione del supporto in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Procedura: Creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))
