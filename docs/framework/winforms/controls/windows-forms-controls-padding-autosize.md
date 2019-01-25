---
title: 'Procedura dettagliata: Definire il layout dei Windows Form usando spaziatura, margini e la proprietà AutoSize'
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
ms.openlocfilehash: c92ea7b4cb2acbe84d9086698cdf8dfbf5f239bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738615"
---
# <a name="walkthrough-laying-out-windows-forms-controls-with-padding-margins-and-the-autosize-property"></a>Procedura dettagliata: Definire il layout dei Windows Form usando spaziatura, margini e la proprietà AutoSize
Per molte applicazioni è estremamente importante la sistemazione precisa dei controlli nel form. Il **finestra di progettazione Windows Form** ti offre molti strumenti di layout per eseguire questa operazione. Tre dei più importanti sono le <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, e <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà, che sono presenti in tutti i controlli Windows Form.  
  
 La proprietà <xref:System.Windows.Forms.Control.Margin%2A> definisce lo spazio intorno al controllo per mantenere gli altri controlli a una specifica distanza dai bordi del controllo stesso.  
  
 La proprietà <xref:System.Windows.Forms.Control.Padding%2A> definisce lo spazio all'interno di un controllo per mantenere il contenuto del controllo, ad esempio il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A>, a una specifica distanza dai bordi del controllo stesso.  
  
 L'illustrazione seguente mostra le proprietà <xref:System.Windows.Forms.Control.Padding%2A> e <xref:System.Windows.Forms.Control.Margin%2A> in un controllo.  
  
 ![Spaziatura e margini per Windows Form controlli](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")  
  
 Il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà indica un controllo ridimensionato automaticamente in base al relativo contenuto. Il ridimensionamento non verrà eseguito per essere inferiore rispetto al valore dell'originale <xref:System.Windows.Forms.Control.Size%2A> proprietà che verrà tenuto in considerazione per il valore del relativo <xref:System.Windows.Forms.Control.Padding%2A> proprietà.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione di un progetto Windows Form  
  
-   Impostazione dei margini per i controlli  
  
-   Impostazione della spaziatura interna per i controlli  
  
-   Ridimensionamento automatico dei controlli  
  
 Al termine, si avrà una migliore comprensione del ruolo svolto da queste importanti funzionalità di layout.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Autorizzazioni sufficienti per essere in grado di creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un **applicazione di Windows** progetto denominato `LayoutExample`. Per altre informazioni, vedere [Procedura: Creare un progetto di applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) .  
  
2.  Selezionare il form nel **finestra di progettazione Windows Form**.  
  
## <a name="setting-margins-for-your-controls"></a>Impostazione dei margini per i controlli  
 È possibile impostare la distanza predefinita tra i controlli usando le <xref:System.Windows.Forms.Control.Margin%2A> proprietà. Quando si sposta un controllo abbastanza ravvicinati per un altro controllo, si noterà una Guida di allineamento che mostra i margini per i due controlli. Il controllo che si sposta anche verrà bloccato a distanza definita per i margini.  
  
#### <a name="to-arrange-controls-on-your-form-using-the-margin-property"></a>Per disporre i controlli nel form utilizzando la proprietà Margin  
  
1.  Trascinare due <xref:System.Windows.Forms.Button> dei controlli il **casella degli strumenti** nel form.  
  
2.  Selezionare una del <xref:System.Windows.Forms.Button> controlla e spostarlo accanto a altro, fino a quando non si stanno quasi toccando.  
  
     Osservare la Guida di allineamento che viene visualizzato tra di essi. La distanza è la somma di due controlli <xref:System.Windows.Forms.Control.Margin%2A> valori. Il controllo che si sposta viene bloccato sulla distanza. Per informazioni dettagliate, vedere [procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
3.  Modifica il <xref:System.Windows.Forms.Control.Margin%2A> proprietà di uno dei controlli espandendo il <xref:System.Windows.Forms.Control.Margin%2A> voce nella **proprietà** finestra e impostando il <xref:System.Windows.Forms.Padding.All%2A> su 20.  
  
4.  Selezionare una del <xref:System.Windows.Forms.Button> controlla e spostarlo più vicino a altro.  
  
     La Guida di allineamento che definisce la somma dei valori di margine è più lungo e che il controllo si Aggancia a una distanza maggiore da un altro controllo.  
  
5.  Modifica il <xref:System.Windows.Forms.Control.Margin%2A> proprietà del controllo selezionato, espandere il <xref:System.Windows.Forms.Control.Margin%2A> voce nella **proprietà** finestra e impostando il <xref:System.Windows.Forms.Padding.Top%2A> proprietà a 5.  
  
6.  Spostare il controllo selezionato sotto l'altro controllo e osservare che la Guida di allineamento è più breve. Spostare il controllo selezionato a sinistra di altro controllo e osservare che la Guida di allineamento mantiene il valore ottenuto nel passaggio 4.  
  
7.  È possibile impostare ciascuno degli aspetti del <xref:System.Windows.Forms.Control.Margin%2A> proprietà, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, su valori diversi oppure è possibile impostarle tutte allo stesso valore con il <xref:System.Windows.Forms.Padding.All%2A> proprietà.  
  
## <a name="setting-padding-for-your-controls"></a>Impostazione della spaziatura interna per i controlli  
 Per ottenere il layout preciso richiesto per l'applicazione, i controlli spesso contiene controlli figlio. Quando si desidera specificare la prossimità del bordo del controllo figlio del mouse sul bordo del controllo padre, usare il controllo padre <xref:System.Windows.Forms.Control.Padding%2A> proprietà in combinazione con il controllo figlio <xref:System.Windows.Forms.Control.Margin%2A> proprietà. Il <xref:System.Windows.Forms.Control.Padding%2A> proprietà viene utilizzata anche per controllare la vicinanza del contenuto di un controllo (ad esempio, una <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Text%2A> proprietà) per i bordi.  
  
#### <a name="to-arrange-controls-on-your-form-using-padding"></a>Per disporre i controlli nel form utilizzando spaziatura interna  
  
1.  Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.  
  
2.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.AutoSize%2A> , su `true`.  
  
3.  Modifica il <xref:System.Windows.Forms.Control.Padding%2A> proprietà espandendo il <xref:System.Windows.Forms.Control.Padding%2A> voce nella **proprietà** finestra e impostando il <xref:System.Windows.Forms.Padding.All%2A> proprietà a 5.  
  
     Il controllo si espande per lasciare spazio per il riempimento di nuovo.  
  
4.  Trascinare un controllo <xref:System.Windows.Forms.GroupBox> dalla **Casella degli strumenti** al form. Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nel <xref:System.Windows.Forms.GroupBox> controllo. Posizione di <xref:System.Windows.Forms.Button> controllare in modo che sia allineato con l'angolo inferiore destro del <xref:System.Windows.Forms.GroupBox> controllo.  
  
     Osservare le guide di allineamento che appaiono come le <xref:System.Windows.Forms.Button> controllo sta per raggiungere i bordi inferiore e destro del <xref:System.Windows.Forms.GroupBox> controllo. Queste guide di allineamento corrispondono al <xref:System.Windows.Forms.Control.Margin%2A> proprietà del <xref:System.Windows.Forms.Button>.  
  
5.  Modifica il <xref:System.Windows.Forms.GroupBox> del controllo <xref:System.Windows.Forms.Control.Padding%2A> proprietà espandendo il <xref:System.Windows.Forms.Control.Padding%2A> voce nella **le proprietà** finestra e impostando il <xref:System.Windows.Forms.Padding.All%2A> su 20.  
  
6.  Selezionare il <xref:System.Windows.Forms.Button> controllo all'interno di <xref:System.Windows.Forms.GroupBox> controllano e spostarlo verso il centro del <xref:System.Windows.Forms.GroupBox>.  
  
     Le guide di allineamento vengono visualizzati a una maggiore distanza dai bordi del <xref:System.Windows.Forms.GroupBox> controllo. La distanza è la somma del <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Margin%2A> proprietà e il <xref:System.Windows.Forms.GroupBox> del controllo <xref:System.Windows.Forms.Control.Padding%2A> proprietà.  
  
## <a name="automatically-sizing-your-controls"></a>Ridimensionamento automatico dei controlli  
 In alcune applicazioni, le dimensioni di un controllo non sarà lo stesso in fase di esecuzione è stato in fase di progettazione. Il testo di un <xref:System.Windows.Forms.Button> controllo, ad esempio, potrebbe essere ottenuto da un database e la sua lunghezza non è noto in anticipo.  
  
 Quando la <xref:System.Windows.Forms.Control.AutoSize%2A> è impostata su `true`, il controllo viene ridimensionato in base al relativo contenuto. Per altre informazioni, vedere [Cenni preliminari sulle proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
#### <a name="to-arrange-controls-on-your-form-using-the-autosize-property"></a>Per disporre i controlli nel form utilizzando la proprietà AutoSize  
  
1.  Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.  
  
2.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.AutoSize%2A> , su `true`.  
  
3.  Modifica il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Text%2A> proprietà su "**di questo pulsante è una stringa lunga per la proprietà Text**."  
  
     Quando si esegue il commit della modifica, la <xref:System.Windows.Forms.Button> controllo viene ridimensionata per adattarsi al testo nuovi.  
  
4.  Trascinare un'altra <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nel form.  
  
5.  Modifica il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Text%2A> proprietà su "**di questo pulsante è una stringa lunga per la proprietà Text.**"  
  
     Quando si esegue il commit della modifica, la <xref:System.Windows.Forms.Button> controllo non viene ridimensionato automaticamente e il testo viene ritagliato in base al bordo destro del controllo.  
  
6.  Modifica il <xref:System.Windows.Forms.Control.Padding%2A> proprietà espandendo il <xref:System.Windows.Forms.Control.Padding%2A> voce nella **proprietà** finestra e impostando il <xref:System.Windows.Forms.Padding.All%2A> proprietà a 5.  
  
     Il testo interno del controllo viene troncato in tutti e quattro i lati.  
  
7.  Modifica il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà `true`.  
  
     Il <xref:System.Windows.Forms.Button> controllo viene ridimensionato automaticamente in modo da includere l'intera stringa. Spaziatura interna è stata inoltre aggiunta la intorno al testo, causando la <xref:System.Windows.Forms.Button> controllo da espandere in tutte e quattro le direzioni.  
  
8.  Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form. Posizionarlo accanto all'angolo in basso a destra del form.  
  
9. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.AutoSize%2A> , su `true`.  
  
10. Impostare il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.  
  
11. Modifica il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Text%2A> proprietà su "**di questo pulsante è una stringa lunga per la proprietà Text.**"  
  
     Quando si esegue il commit della modifica, la <xref:System.Windows.Forms.Button> controllo ridimensionato verso sinistra. In generale, ridimensionamento automatico aumenta le dimensioni di un controllo nella direzione opposta relativo <xref:System.Windows.Forms.Control.Anchor%2A> l'impostazione della proprietà.  
  
## <a name="autosize-and-autosizemode-properties"></a>Proprietà AutoSize e AutoSizeMode  
 Alcuni controlli supportano il `AutoSizeMode` proprietà, che offre maggiore controllo con granularità fine sul comportamento di ridimensionamento automatico di un controllo.  
  
#### <a name="to-use-the-autosizemode-property"></a>Usare il AutoSizeMode (proprietà)  
  
1.  Trascinare un controllo <xref:System.Windows.Forms.Panel> dalla **Casella degli strumenti** al form.  
  
2.  Impostare il valore della <xref:System.Windows.Forms.Panel> del controllo <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà `true`.  
  
3.  Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nel <xref:System.Windows.Forms.Panel> controllo.  
  
4.  Sul posto di <xref:System.Windows.Forms.Button> angolo in basso a destra del controllo il <xref:System.Windows.Forms.Panel> controllo.  
  
5.  Selezionare il <xref:System.Windows.Forms.Panel> controllano e quadratino di ridimensionamento in basso a destra. Ridimensionare il <xref:System.Windows.Forms.Panel> controllo sia maggiori e minori.  
  
    > [!NOTE]
    >  È possibile ridimensionare liberamente le <xref:System.Windows.Forms.Panel> controllo, ma è possibile renderlo più piccolo la posizione del <xref:System.Windows.Forms.Button> nell'angolo in basso a destra del controllo. Questo comportamento viene specificato per il valore predefinito di `AutoSizeMode` proprietà, ovvero <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.  
  
6.  Impostare il valore della <xref:System.Windows.Forms.Panel> del controllo `AutoSizeMode` proprietà <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.  
  
     Il <xref:System.Windows.Forms.Panel> viene ridimensionato in modo da racchiudere il <xref:System.Windows.Forms.Button> controllo. Non è possibile ridimensionare il <xref:System.Windows.Forms.Panel> controllo.  
  
7.  Trascinare il <xref:System.Windows.Forms.Button> verso l'angolo superiore sinistro del controllo di <xref:System.Windows.Forms.Panel> controllo.  
  
     Il <xref:System.Windows.Forms.Panel> controllo viene ridimensionato al <xref:System.Windows.Forms.Button> nuova posizione del controllo.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Esistono molte altre funzionalità di layout per la disposizione dei controlli nelle applicazioni Windows Form. Ecco alcune combinazioni di cui è possibile provare a:  
  
-   Compilazione di un form utilizzando un <xref:System.Windows.Forms.TableLayoutPanel> controllo. Per informazioni dettagliate, vedere [procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Provare a modificare i valori del <xref:System.Windows.Forms.TableLayoutPanel> del controllo <xref:System.Windows.Forms.Control.Padding%2A> proprietà, così come il <xref:System.Windows.Forms.Control.Margin%2A> proprietà per i controlli figlio.  
  
-   Provare a stesso esperimento usando un <xref:System.Windows.Forms.FlowLayoutPanel> controllo. Per informazioni dettagliate, vedere [procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
-   Esperimento con ancorare i controlli figlio in un <xref:System.Windows.Forms.Panel> controllo. Il <xref:System.Windows.Forms.Control.Padding%2A> proprietà è una realizzazione più generale del <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> proprietà ed è possibile provarlo che ciò avviene inserendo un controllo figlio in un <xref:System.Windows.Forms.Panel> controllo e l'impostazione del controllo figlio <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>. Impostare il <xref:System.Windows.Forms.Panel> del controllo <xref:System.Windows.Forms.Control.Padding%2A> proprietà per diversi valori e notare l'effetto.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [Panoramica sulla proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
