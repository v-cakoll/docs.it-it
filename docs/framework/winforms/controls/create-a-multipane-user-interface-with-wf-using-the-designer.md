---
title: "Procedura: Creare un'interfaccia utente a più riquadri con Windows Forms usando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 9f3350e32c0fbff58678052d26be954d30d512a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011515"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Procedura: Creare un'interfaccia utente a più riquadri con Windows Forms usando la finestra di progettazione
Nella procedura seguente, si creerà un'interfaccia utente a più riquadri simile a quello usato in Microsoft Outlook, con un **cartella** elenco, un **messaggi** riquadro e un **anteprima** riquadro. Questa disposizione avviene principalmente tramite l'ancoraggio dei controlli con il modulo.  
  
 Quando si effettua l'ancoraggio di un controllo, determinare il bordo del contenitore padre a cui è bloccato su un controllo. Di conseguenza, se si imposta la <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Right>, il bordo destro del controllo sarà ancorato al bordo destro del controllo padre. Inoltre, il bordo ancorato il controllo viene ridimensionato in modo corrisponde a quello del controllo contenitore. Per altre informazioni sul modo in cui <xref:System.Windows.Forms.SplitContainer.Dock%2A> funzionamento di proprietà, vedere [come: Ancorare i controlli in Windows Form](how-to-dock-controls-on-windows-forms.md).  
  
 Questa procedura illustra la disposizione di <xref:System.Windows.Forms.SplitContainer> e gli altri controlli nel form e non sull'aggiunta di funzionalità che semplificano l'applicazione di simulare Microsoft Outlook.  
  
 Per creare questa interfaccia utente, inserire tutti i controlli all'interno di un <xref:System.Windows.Forms.SplitContainer> controllo, che contiene un <xref:System.Windows.Forms.TreeView> controllo nel Pannello di sinistra. Il pannello destro del <xref:System.Windows.Forms.SplitContainer> controllo contiene un secondo <xref:System.Windows.Forms.SplitContainer> controllare con un <xref:System.Windows.Forms.ListView> controllo sopra un <xref:System.Windows.Forms.RichTextBox> controllo. Questi <xref:System.Windows.Forms.SplitContainer> controlli abilitare il ridimensionamento indipendente degli altri controlli nel form. È possibile adattare le tecniche in questa procedura per le interfacce utente personalizzate di creazione personalizzato.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Per creare un'interfaccia utente in stile Outlook in fase di progettazione  
  
1. Creare un nuovo progetto applicazione Windows (**File** > **New** > **progetto** > **Visual C#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).  
  
2. Trascinare un <xref:System.Windows.Forms.SplitContainer> controllare dal **casella degli strumenti** al form. Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
3. Trascinare un <xref:System.Windows.Forms.TreeView> controllare dal **casella degli strumenti** al pannello a sinistra del <xref:System.Windows.Forms.SplitContainer> controllo. Nel **le proprietà** impostare nella finestra di <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Left> facendo clic sul pannello a sinistra nell'editor dei valori visualizzato quando si fa clic sulla freccia in giù.  
  
4. Trascinare un altro <xref:System.Windows.Forms.SplitContainer> controllare dal **casella degli strumenti**; posizionarlo nel pannello a destra della finestra di <xref:System.Windows.Forms.SplitContainer> controllo è stato aggiunto al form. Nel **proprietà** impostare nella finestra di <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill> e il <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà <xref:System.Windows.Forms.Orientation.Horizontal>.  
  
5. Trascinare un <xref:System.Windows.Forms.ListView> controllare dal **della casella degli strumenti** al riquadro superiore della seconda <xref:System.Windows.Forms.SplitContainer> controllo è stato aggiunto al form. Impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> del controllo <xref:System.Windows.Forms.ListView> su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
6. Trascinare un <xref:System.Windows.Forms.RichTextBox> controllare dal **casella degli strumenti** al riquadro inferiore del secondo <xref:System.Windows.Forms.SplitContainer> controllo. Impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> del controllo <xref:System.Windows.Forms.RichTextBox> su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     A questo punto, se si preme F5 per eseguire l'applicazione, il modulo Visualizza un'interfaccia utente di tre parti, simile a quella di Microsoft Outlook.  
  
    > [!NOTE]
    >  Quando si posiziona il puntatore del mouse su una delle barre di divisione all'interno di <xref:System.Windows.Forms.SplitContainer> controlli, è possibile ridimensionare le dimensioni interne.  
  
     A questo punto nello sviluppo di applicazioni, aver creato un'interfaccia utente sofisticata. Procedere con la programmazione dell'applicazione stessa, il passaggio successivo tramite la connessione è probabilmente il <xref:System.Windows.Forms.TreeView> controllo e <xref:System.Windows.Forms.ListView> controlli a un tipo di origine dati. Per altre informazioni sulla connessione di controlli ai dati, vedere [Data Binding e Windows Form](../data-binding-and-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SplitContainer>
- [Controllo SplitContainer](splitcontainer-control-windows-forms.md)
