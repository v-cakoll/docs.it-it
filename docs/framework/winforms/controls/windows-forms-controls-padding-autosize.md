---
title: Layout dei controlli con spaziatura interna, margini e proprietà AutoSize
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: ca7942c04434592f2541252c47ac3dd17e03dbac
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742379"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>Procedura dettagliata: disposizione dei controlli con spaziatura interna, margini e proprietà AutoSize

Per molte applicazioni è estremamente importante la sistemazione precisa dei controlli nel form. Il **Progettazione Windows Form** in Visual Studio offre molti strumenti di layout a questo scopo. Tre dei più importanti sono le proprietà <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>e <xref:System.Windows.Forms.Control.AutoSize%2A>, che sono presenti in tutti i controlli Windows Forms.

La proprietà <xref:System.Windows.Forms.Control.Margin%2A> definisce lo spazio intorno al controllo per mantenere gli altri controlli a una specifica distanza dai bordi del controllo stesso.

La proprietà <xref:System.Windows.Forms.Control.Padding%2A> definisce lo spazio all'interno di un controllo per mantenere il contenuto del controllo, ad esempio il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A>, a una specifica distanza dai bordi del controllo stesso.

L'illustrazione seguente mostra le proprietà <xref:System.Windows.Forms.Control.Padding%2A> e <xref:System.Windows.Forms.Control.Margin%2A> in un controllo.

![Spaziatura e margine per controlli Windows Form](./media/vs-winformpadmargin.gif)

La proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> indica a un controllo di ridimensionarsi automaticamente in base al relativo contenuto. Non verrà ridimensionato in modo da essere minore del valore della proprietà <xref:System.Windows.Forms.Control.Size%2A> originale e verrà considerato il valore della relativa proprietà <xref:System.Windows.Forms.Control.Padding%2A>.

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-project"></a>Creare il progetto

1. In Visual Studio creare un progetto di **applicazione Windows** denominato `LayoutExample`.

2. Selezionare il modulo nella **Progettazione Windows Form**.

## <a name="set-margins-for-controls"></a>Impostare i margini per i controlli

È possibile impostare la distanza predefinita tra i controlli usando la proprietà <xref:System.Windows.Forms.Control.Margin%2A>. Quando si sposta un controllo abbastanza vicino a un altro controllo, viene visualizzata una guide di allineamento che mostra i margini dei due controlli. Il controllo che si sta spostando verrà inoltre bloccato sulla distanza definita dai margini.

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>Disporre i controlli nel form usando la proprietà Margin

1. Trascinare due controlli <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel form.

2. Selezionare uno dei controlli <xref:System.Windows.Forms.Button> e spostarlo vicino all'altro, fino a quando non sono quasi toccati.

   Osservare la guide di allineamento visualizzata tra di essi. Questa distanza è la somma dei due controlli ' <xref:System.Windows.Forms.Control.Margin%2A> valori. Il controllo spostato si blocca a questa distanza. Per informazioni dettagliate, vedere [procedura dettagliata: disposizione dei controlli su Windows Forms usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

3. Modificare la proprietà <xref:System.Windows.Forms.Control.Margin%2A> di uno dei controlli espandendo la voce <xref:System.Windows.Forms.Control.Margin%2A> nella finestra **Proprietà** e impostando la proprietà <xref:System.Windows.Forms.Padding.All%2A> su **20**.

4. Selezionare uno dei controlli <xref:System.Windows.Forms.Button> e spostarlo vicino all'altro.

   La pagina di allineamento che definisce la somma dei valori dei margini è più lunga e il controllo si blocca a una distanza maggiore rispetto all'altro.

5. Modificare la proprietà <xref:System.Windows.Forms.Control.Margin%2A> del controllo selezionato espandendo la voce <xref:System.Windows.Forms.Control.Margin%2A> nella finestra **Proprietà** e impostando la proprietà <xref:System.Windows.Forms.Padding.Top%2A> su **5**.

6. Spostare il controllo selezionato sotto l'altro controllo e osservare che la guide di allineamento è più breve. Spostare il controllo selezionato a sinistra dell'altro controllo e osservare che la Guida di allineamento mantiene il valore osservato nel passaggio 4.

7. È possibile impostare tutti gli aspetti della proprietà <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A><xref:System.Windows.Forms.Padding.Bottom%2A>, su valori diversi oppure è possibile impostarli tutti sullo stesso valore con la proprietà <xref:System.Windows.Forms.Padding.All%2A>.

## <a name="set-padding-for-controls"></a>Imposta spaziatura interna per i controlli

Per ottenere il layout preciso necessario per l'applicazione, i controlli contengono spesso controlli figlio. Quando si desidera specificare la prossimità del bordo del controllo figlio al bordo del controllo padre, utilizzare la proprietà <xref:System.Windows.Forms.Control.Padding%2A> del controllo padre insieme alla proprietà <xref:System.Windows.Forms.Control.Margin%2A> del controllo figlio. La proprietà <xref:System.Windows.Forms.Control.Padding%2A> viene utilizzata anche per controllare la prossimità del contenuto di un controllo, ad esempio una proprietà <xref:System.Windows.Forms.Control.Text%2A> di un controllo <xref:System.Windows.Forms.Button>, ai relativi bordi.

### <a name="arrange-controls-on-your-form-using-padding"></a>Disporre i controlli nel form usando la spaziatura interna

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.

2. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> del controllo <xref:System.Windows.Forms.Button> su **true**.

3. Modificare la proprietà <xref:System.Windows.Forms.Control.Padding%2A> espandendo la voce <xref:System.Windows.Forms.Control.Padding%2A> nella finestra **Proprietà** e impostando la proprietà <xref:System.Windows.Forms.Padding.All%2A> su **5**.

   Il controllo si espande per fornire spazio per la nuova spaziatura interna.

4. Trascinare un controllo <xref:System.Windows.Forms.GroupBox> dalla **Casella degli strumenti** al form. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel controllo <xref:System.Windows.Forms.GroupBox>. Posizionare il controllo <xref:System.Windows.Forms.Button> in modo che sia allineato all'angolo inferiore destro del controllo <xref:System.Windows.Forms.GroupBox>.

   Osservare le guide di allineamento visualizzate come il controllo <xref:System.Windows.Forms.Button> si avvicina ai bordi inferiore e destro del controllo <xref:System.Windows.Forms.GroupBox>. Queste guide di allineamento corrispondono alla proprietà <xref:System.Windows.Forms.Control.Margin%2A> della <xref:System.Windows.Forms.Button>.

5. Modificare la proprietà <xref:System.Windows.Forms.Control.Padding%2A> del controllo <xref:System.Windows.Forms.GroupBox> espandendo la voce <xref:System.Windows.Forms.Control.Padding%2A> nella finestra **Proprietà** e impostando la proprietà <xref:System.Windows.Forms.Padding.All%2A> su **20**.

6. Selezionare il controllo <xref:System.Windows.Forms.Button> all'interno del controllo <xref:System.Windows.Forms.GroupBox> e spostarlo verso il centro della <xref:System.Windows.Forms.GroupBox>.

   Le guide di allineamento vengono visualizzate a una distanza maggiore dai bordi del controllo <xref:System.Windows.Forms.GroupBox>. Questa distanza è la somma della proprietà <xref:System.Windows.Forms.Control.Margin%2A> del controllo <xref:System.Windows.Forms.Button> e della proprietà <xref:System.Windows.Forms.Control.Padding%2A> del controllo <xref:System.Windows.Forms.GroupBox>.

## <a name="size-controls-automatically"></a>Ridimensiona automaticamente i controlli

In alcune applicazioni, le dimensioni di un controllo non saranno uguali in fase di esecuzione, come in fase di progettazione. Il testo di un controllo <xref:System.Windows.Forms.Button>, ad esempio, può essere tratto da un database e la sua lunghezza non è nota in anticipo.

Quando la proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> è impostata su `true`, il controllo verrà ridimensionato in base al relativo contenuto. Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](autosize-property-overview.md).

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>Disporre i controlli nel form usando la proprietà AutoSize

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.

2. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> del controllo <xref:System.Windows.Forms.Button> su **true**.

3. Modificare la proprietà <xref:System.Windows.Forms.Control.Text%2A> del controllo <xref:System.Windows.Forms.Button> su **questo pulsante ha una stringa long per la relativa proprietà Text**.

   Quando si esegue il commit della modifica, il controllo <xref:System.Windows.Forms.Button> viene ridimensionato per adattarsi al nuovo testo.

4. Trascinare un altro controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel form.

5. Modificare la proprietà <xref:System.Windows.Forms.Control.Text%2A> del controllo <xref:System.Windows.Forms.Button> su "**questo pulsante ha una stringa long per la relativa proprietà Text".**

   Quando si esegue il commit della modifica, il controllo <xref:System.Windows.Forms.Button> non viene ridimensionato automaticamente e il testo viene ritagliato in base al bordo destro del controllo.

6. Modificare la proprietà <xref:System.Windows.Forms.Control.Padding%2A> espandendo la voce <xref:System.Windows.Forms.Control.Padding%2A> nella finestra **Proprietà** e impostando la proprietà <xref:System.Windows.Forms.Padding.All%2A> su **5**.

   Il testo nell'interno del controllo viene ritagliato su tutti e quattro i lati.

7. Modificare la proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> del controllo <xref:System.Windows.Forms.Button> su **true**.

   Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato per includere l'intera stringa. È stata inoltre aggiunta la spaziatura interna intorno al testo, causando l'espansione del controllo <xref:System.Windows.Forms.Button> in tutte e quattro le direzioni.

8. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form. Posizionarlo vicino all'angolo inferiore destro del form.

9. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> del controllo <xref:System.Windows.Forms.Button> su **true**.

10. Impostare la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> del controllo <xref:System.Windows.Forms.Button> su <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.

11. Modificare la proprietà <xref:System.Windows.Forms.Control.Text%2A> del controllo <xref:System.Windows.Forms.Button> su "**questo pulsante ha una stringa long per la relativa proprietà Text".**

   Quando si esegue il commit della modifica, il controllo <xref:System.Windows.Forms.Button> si ridimensiona verso sinistra. In generale, il ridimensionamento automatico aumenterà le dimensioni di un controllo nella direzione opposta all'impostazione della proprietà <xref:System.Windows.Forms.Control.Anchor%2A>.

## <a name="autosize-and-autosizemode-properties"></a>Proprietà AutoSize e AutoSizeMode

 Alcuni controlli supportano la proprietà `AutoSizeMode`, che offre un controllo più granulare sul comportamento di ridimensionamento automatico di un controllo.

### <a name="use-the-autosizemode-property"></a>Usare la proprietà AutoSizeMode

1. Trascinare un controllo <xref:System.Windows.Forms.Panel> dalla **Casella degli strumenti** al form.

2. Impostare il valore della proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> del controllo <xref:System.Windows.Forms.Panel> su **true**.

3. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel controllo <xref:System.Windows.Forms.Panel>.

4. Posizionare il controllo <xref:System.Windows.Forms.Button> vicino all'angolo inferiore destro del controllo <xref:System.Windows.Forms.Panel>.

5. Selezionare il controllo <xref:System.Windows.Forms.Panel> e il quadratino di ridimensionamento in basso a destra. Ridimensionare il controllo <xref:System.Windows.Forms.Panel> in modo che sia maggiore e minore.

   > [!NOTE]
   > È possibile ridimensionare liberamente il controllo <xref:System.Windows.Forms.Panel>, ma non è possibile ridimensionarlo più in basso rispetto alla posizione dell'angolo inferiore destro del controllo <xref:System.Windows.Forms.Button>. Questo comportamento viene specificato dal valore predefinito della proprietà `AutoSizeMode`, che è <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.

6. Impostare il valore della proprietà `AutoSizeMode` del controllo <xref:System.Windows.Forms.Panel> su <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.

   Il controllo <xref:System.Windows.Forms.Panel> dimensioni stesse per racchiudere il controllo <xref:System.Windows.Forms.Button>. Non è possibile ridimensionare il controllo <xref:System.Windows.Forms.Panel>.

7. Trascinare il controllo <xref:System.Windows.Forms.Button> verso l'angolo superiore sinistro del controllo <xref:System.Windows.Forms.Panel>.

   Il controllo <xref:System.Windows.Forms.Panel> si ridimensiona alla nuova posizione del controllo <xref:System.Windows.Forms.Button>.

## <a name="next-steps"></a>Passaggi successivi

Sono disponibili molte altre funzionalità di layout per la disposizione dei controlli nelle applicazioni Windows Forms. Di seguito sono riportate alcune combinazioni che è possibile provare:

- Compilare un form usando un controllo <xref:System.Windows.Forms.TableLayoutPanel>. Per informazioni dettagliate, vedere [procedura dettagliata: disposizione dei controlli in Windows Forms usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Provare a modificare i valori della proprietà <xref:System.Windows.Forms.Control.Padding%2A> del controllo <xref:System.Windows.Forms.TableLayoutPanel>, nonché la proprietà <xref:System.Windows.Forms.Control.Margin%2A> nei relativi controlli figlio.

- Provare lo stesso esperimento usando un controllo <xref:System.Windows.Forms.FlowLayoutPanel>. Per informazioni dettagliate, vedere [procedura dettagliata: disposizione dei controlli in Windows Forms tramite FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

- Sperimentare l'ancoraggio dei controlli figlio in un controllo <xref:System.Windows.Forms.Panel>. La proprietà <xref:System.Windows.Forms.Control.Padding%2A> è una realizzazione più generale della proprietà <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> ed è possibile soddisfarla in questo modo inserendo un controllo figlio in un controllo <xref:System.Windows.Forms.Panel> e impostando la proprietà <xref:System.Windows.Forms.Control.Dock%2A> del controllo figlio su <xref:System.Windows.Forms.DockStyle.Fill>. Impostare la proprietà <xref:System.Windows.Forms.Control.Padding%2A> del controllo <xref:System.Windows.Forms.Panel> su diversi valori e annotare l'effetto.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [Panoramica sulla proprietà AutoSize](autosize-property-overview.md)
- [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
