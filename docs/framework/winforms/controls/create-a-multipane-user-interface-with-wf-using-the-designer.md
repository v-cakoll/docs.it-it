---
title: "Procedura: creare un'interfaccia utente a più riquadri con Windows Form utilizzando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: d0faf86ce31dad6bc053b5af8902e500d2b1c75b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529864"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Procedura: creare un'interfaccia utente a più riquadri con Windows Form utilizzando la finestra di progettazione
Nella procedura seguente, si creerà un'interfaccia utente a più riquadri simile a quella utilizzata in Microsoft Outlook, con un **cartella** elenco, un **messaggi** riquadro e un **anteprima** riquadro. Questa disposizione è ottenuta principalmente tramite ancorare i controlli con il modulo.  
  
 Quando si inserisce un controllo, determinare il bordo del contenitore padre a cui è bloccato su un controllo. Pertanto, se si imposta la <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Right>, il bordo destro del controllo viene ancorato al bordo destro del controllo padre. Inoltre, il bordo del controllo ancorato viene ridimensionato per corrispondere a quello del controllo contenitore. Per ulteriori informazioni su come <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà, vedere [procedura: ancorare controlli in Windows Form](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Questa procedura illustra la disposizione di <xref:System.Windows.Forms.SplitContainer> e altri controlli nel form, non sull'aggiunta di funzionalità per rendere l'applicazione di simulare Microsoft Outlook.  
  
 Per creare questa interfaccia utente, inserire tutti i controlli all'interno di un <xref:System.Windows.Forms.SplitContainer> controllo che contiene un <xref:System.Windows.Forms.TreeView> controllo nel riquadro a sinistra. Il riquadro di destra la <xref:System.Windows.Forms.SplitContainer> controllo contiene un secondo <xref:System.Windows.Forms.SplitContainer> controllare con un <xref:System.Windows.Forms.ListView> controllo precedente un <xref:System.Windows.Forms.RichTextBox> controllo. Questi <xref:System.Windows.Forms.SplitContainer> controlli abilitano il ridimensionamento indipendenti degli altri controlli nel form. È possibile adattare le tecniche in questa procedura per creare interfacce utente personalizzate.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Per creare un'interfaccia utente nello stile di Outlook in fase di progettazione  
  
1.  Creare un nuovo progetto applicazione Windows. Per informazioni dettagliate, vedere [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Trascinare un <xref:System.Windows.Forms.SplitContainer> controllo il **della casella degli strumenti** al form. Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>.  
  
3.  Trascinare un <xref:System.Windows.Forms.TreeView> controllo il **della casella degli strumenti** pannello sinistro del <xref:System.Windows.Forms.SplitContainer> controllo. Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Left> facendo clic sul riquadro a sinistra nell'editor dei valori visualizzati quando si fa clic sulla freccia rivolta verso il basso.  
  
4.  Trascinare un'altra <xref:System.Windows.Forms.SplitContainer> controllo il **della casella degli strumenti**; posizionarlo nel riquadro destro del <xref:System.Windows.Forms.SplitContainer> controllo aggiunto al form. Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill> e <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà <xref:System.Windows.Forms.Orientation.Horizontal>.  
  
5.  Trascinare un <xref:System.Windows.Forms.ListView> controllo il **della casella degli strumenti** al pannello superiore del secondo <xref:System.Windows.Forms.SplitContainer> controllo aggiunto al form. Impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> del controllo <xref:System.Windows.Forms.ListView> su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
6.  Trascinare un <xref:System.Windows.Forms.RichTextBox> controllo il **della casella degli strumenti** al pannello inferiore del secondo <xref:System.Windows.Forms.SplitContainer> controllo. Impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> del controllo <xref:System.Windows.Forms.RichTextBox> su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     A questo punto, se si preme F5 per eseguire l'applicazione, il modulo Visualizza un'interfaccia utente di tre parti, simile a quello di Microsoft Outlook.  
  
    > [!NOTE]
    >  Quando si posiziona il puntatore del mouse su una delle barre di divisione all'interno di <xref:System.Windows.Forms.SplitContainer> controlli, è possibile ridimensionare le dimensioni interne.  
  
     A questo punto nello sviluppo di applicazioni, avere predisposto un'interfaccia utente sofisticata. Il passaggio successivo consiste procedere con la programmazione dell'applicazione stessa, ad esempio tramite la connessione di <xref:System.Windows.Forms.TreeView> controllo e <xref:System.Windows.Forms.ListView> controlli a un tipo di origine dati. Per ulteriori informazioni sulla connessione di controlli ai dati, vedere [Data Binding e Windows Form](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.SplitContainer>  
 [Controllo SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
