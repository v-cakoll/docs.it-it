---
title: Disponi contenuto WPF in Windows Forms in fase di progettazione
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5a6b12def45052e117fb149555946ea42d6cd3c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746826"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a>Procedura dettagliata: disposizione del contenuto WPF in Windows Forms in fase di progettazione

Questo articolo illustra come usare le funzionalità di layout di Windows Forms, ad esempio l'ancoraggio e le guide di allineamento, per disporre i controlli Windows Presentation Foundation (WPF).

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-project"></a>Creare il progetto

Aprire Visual Studio e creare un nuovo progetto di applicazione Windows Forms in Visual Basic o C# in un oggetto visivo denominato `ArrangeElementHost`.

> [!NOTE]
> Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.

## <a name="create-the-wpf-control"></a>Creare il controllo WPF

Dopo avere aggiunto un controllo WPF al progetto, è possibile disporlo sul form.

1. Aggiungere un nuovo <xref:System.Windows.Controls.UserControl> WPF al progetto. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovi contenuti WPF in Windows Forms in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.

3. Nella finestra **Proprietà** impostare il valore delle proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> su **200**.

4. Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su **blu**.

5. Compilazione del progetto.

## <a name="host-wpf-controls-in-a-layout-panel"></a>Ospitare controlli WPF in un pannello di layout

È possibile usare i controlli WPF nei pannelli di layout nello stesso modo in cui si usano gli altri controlli Windows Form.

1. Aprire `Form1` in Progettazione Windows Form.

2. Nella **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> sul form.

3. Nel pannello smart tag del controllo <xref:System.Windows.Forms.TableLayoutPanel> selezionare **Rimuovi ultima riga**.

4. Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> impostando una larghezza e un'altezza maggiori.

5. Nella **casella degli strumenti**fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nella prima cella del controllo <xref:System.Windows.Forms.TableLayoutPanel>.

   L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.

6. Nella **casella degli strumenti**fare doppio clic su `UserControl1` per creare un'altra istanza nella seconda cella del controllo <xref:System.Windows.Forms.TableLayoutPanel>.

7. Nella finestra **struttura documento** selezionare `tableLayoutPanel1`.

8. Nella finestra **Proprietà** impostare il valore della proprietà <xref:System.Windows.Forms.Control.Padding%2A> su 10, 10 **, 10, 10**.

   Entrambi i controlli <xref:System.Windows.Forms.Integration.ElementHost> vengono ridimensionati per essere adattati al nuovo layout.

## <a name="use-snaplines-to-align-wpf-controls"></a>Utilizzare le guide di allineamento per allineare i controlli WPF

Le guide di allineamento semplificano l'allineamento dei controlli su un form. È possibile usare le guide di allineamento anche per allineare i controlli WPF. Per ulteriori informazioni, vedere [procedura dettagliata: disposizione dei controlli su Windows Forms mediante guide di allineamento](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

1. Dalla **casella degli strumenti**trascinare un'istanza di `UserControl1` nel form e posizionarla nello spazio sotto il controllo <xref:System.Windows.Forms.TableLayoutPanel>.

   L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost3`.

2. Tramite le guide di allineamento allineare il bordo sinistro di `elementHost3` al bordo sinistro del controllo <xref:System.Windows.Forms.TableLayoutPanel>.

3. Tramite le guide di allineamento ridimensionare `elementHost3` impostando la stessa larghezza del controllo <xref:System.Windows.Forms.TableLayoutPanel>.

4. Spostare `elementHost3` verso il controllo <xref:System.Windows.Forms.TableLayoutPanel> finché non viene visualizzata una guida di allineamento centrale tra i due controlli.

5. Nella finestra **Proprietà** impostare il valore della proprietà Margin su **20, 20, 20, 20**.

6. Spostare `elementHost3` dal controllo <xref:System.Windows.Forms.TableLayoutPanel> finché non viene di nuovo visualizzata la guida di allineamento centrale. La guida di allineamento centrale indica ora un margine di 20.

7. Spostare `elementHost3` a destra finché il bordo sinistro non è allineato al bordo sinistro del `elementHost1`.

8. Modificare la larghezza di `elementHost3` finché il bordo destro non è allineato a quello destro di `elementHost2`.

## <a name="anchor-and-dock-wpf-controls"></a>Ancorare e ancorare controlli WPF

Un controllo WPF incluso in un form è soggetto alle stesse regole di ancoraggio e aggancio degli altri controlli Windows Form.

1. Selezionare `elementHost1`.

2. Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> su in **alto, in basso, a sinistra, a destra**.

3. Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> impostando dimensioni superiori.

   Il controllo `elementHost1` verrà ridimensionato fino ad occupare l'intera cella.

4. Selezionare `elementHost2`.

5. Nella finestra **Proprietà** impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.

   Il controllo `elementHost2` verrà ridimensionato fino ad occupare l'intera cella.

6. Selezionare il controllo <xref:System.Windows.Forms.TableLayoutPanel>.

7. Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Top>.

8. Selezionare `elementHost3`.

9. Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.

   Il controllo `elementHost3` verrà ridimensionato fino a occupare lo spazio rimanente sul form.

10. Ridimensionare il form.

    Tutti e tre i controlli <xref:System.Windows.Forms.Integration.ElementHost> verranno ridimensionati in maniera appropriata.

    Per altre informazioni, vedere [procedura: ancorare e ancorare controlli figlio in un controllo TableLayoutPanel](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Procedura: Allineare un controllo ai bordi dei form in fase di progettazione](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Migrazione e interoperabilità](../../wpf/advanced/migration-and-interoperability.md)
- [Uso di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
