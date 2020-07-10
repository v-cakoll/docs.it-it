---
title: Eventi del mouse
description: Informazioni su come ottenere la posizione del mouse dagli eventi del mouse e comprendere l'ordine in cui gli eventi click del mouse vengono generati nei controlli Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- MouseLeave event [Windows Forms]
- events [Windows Forms], mouse
- Click event [Windows Forms], raising order
- Windows Forms controls, click events
- MouseDoubleClick event [Windows Forms]
- MouseEnter event [Windows Forms]
- MouseHover event [Windows Forms]
- MouseDown event [Windows Forms]
- MouseClick event [Windows Forms]
- MouseMove event [Windows Forms]
- mouse [Windows Forms], events
- MouseUp event
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
ms.openlocfilehash: 640448109961ea5fdf3600ef9e72d7d10e8c9e49
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174380"
---
# <a name="mouse-events-in-windows-forms"></a>Eventi mouse in Windows Form

Quando si gestisce l'input del mouse, in genere si vogliono conoscere la posizione del puntatore del mouse e lo stato dei pulsanti. Questo argomento descrive in dettaglio come reperire tali informazioni da eventi del mouse e illustra l'ordine in cui gli eventi Click del mouse vengono generati nei controlli Windows Form. Per un elenco e una descrizione di tutti gli eventi del mouse, vedere funzionamento dell' [input del mouse in Windows Forms](how-mouse-input-works-in-windows-forms.md).  Vedere anche [Cenni preliminari sui gestori eventi (Windows Forms)](event-handlers-overview-windows-forms.md) e [Cenni preliminari sugli eventi (Windows Forms)](events-overview-windows-forms.md).

## <a name="mouse-information"></a>Informazioni sul mouse

Un oggetto <xref:System.Windows.Forms.MouseEventArgs> viene inviato ai gestori degli eventi del mouse correlati alla pressione di un pulsante e alla registrazione dei movimenti del mouse. <xref:System.Windows.Forms.MouseEventArgs> fornisce informazioni sullo stato corrente del mouse, fra cui la posizione del puntatore nelle coordinate del client, i pulsanti del mouse premuti e se la rotellina del mouse è stata fatta scorrere. Numerosi eventi del mouse, ad esempio quelli che notificano semplicemente il momento in cui il puntatore del mouse entra o esce dai limiti di un controllo, inviano un oggetto <xref:System.EventArgs> al gestore eventi senza altre informazioni.

Se si desidera conoscere lo stato corrente dei pulsanti del mouse o la posizione del puntatore ed evitare la gestione di un evento del mouse, è anche possibile usare le proprietà <xref:System.Windows.Forms.Control.MouseButtons%2A> e <xref:System.Windows.Forms.Control.MousePosition%2A> della classe <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control.MouseButtons%2A> restituisce informazioni sui pulsanti del mouse attualmente premuti. <xref:System.Windows.Forms.Control.MousePosition%2A> restituisce le coordinate dello schermo del puntatore del mouse e coincide con il valore restituito dalla proprietà <xref:System.Windows.Forms.Cursor.Position%2A>.

## <a name="converting-between-screen-and-client-coordinates"></a>Conversione tra coordinate dello schermo e del client

Poiché alcune informazioni sulla posizione del mouse sono espresse con le coordinate del client e altre con le coordinate dello schermo, può essere necessario eseguire una conversione da un sistema di coordinate all'altro. Questa operazione può essere eseguita facilmente usando i metodi <xref:System.Windows.Forms.Control.PointToClient%2A> e <xref:System.Windows.Forms.Control.PointToScreen%2A> disponibili nella classe <xref:System.Windows.Forms.Control>.

## <a name="standard-click-event-behavior"></a>Comportamento dell'evento Click standard

Se si vogliono gestire gli eventi Click del mouse nell'ordine corretto, è necessario conoscere l'ordine in cui gli eventi Click vengono generati nei controlli Windows Form. Tutti i controlli Windows Form generano eventi Click nello stesso ordine quando viene premuto e rilasciato un pulsante del mouse (indipendentemente dal pulsante), fatta eccezione per i singoli controlli segnalati nell'elenco seguente. L'ordine degli eventi generati per un singolo clic del pulsante del mouse è il seguente:

1. Evento<xref:System.Windows.Forms.Control.MouseDown> .

2. Evento<xref:System.Windows.Forms.Control.Click> .

3. Evento<xref:System.Windows.Forms.Control.MouseClick> .

4. Evento<xref:System.Windows.Forms.Control.MouseUp> .

Di seguito è riportato l'ordine degli eventi generati per un doppio clic del pulsante del mouse:

1. Evento<xref:System.Windows.Forms.Control.MouseDown> .

2. Evento<xref:System.Windows.Forms.Control.Click> .

3. Evento<xref:System.Windows.Forms.Control.MouseClick> .

4. Evento<xref:System.Windows.Forms.Control.MouseUp> .

5. Evento<xref:System.Windows.Forms.Control.MouseDown> .

6. Evento<xref:System.Windows.Forms.Control.DoubleClick> . Può variare se il controllo in questione ha il bit di stile <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> impostato su `true`. Per altre informazioni sulla modalità di impostazione di un bit <xref:System.Windows.Forms.Control.SetStyle%2A>, vedere il metodo <xref:System.Windows.Forms.ControlStyles>.

7. Evento<xref:System.Windows.Forms.Control.MouseDoubleClick> .

8. Evento<xref:System.Windows.Forms.Control.MouseUp> .

Per un esempio di codice che illustra l'ordine degli eventi click del mouse, vedere [procedura: gestire eventi di input utente nei controlli Windows Forms](how-to-handle-user-input-events-in-windows-forms-controls.md).

### <a name="individual-controls"></a>Controlli autonomi

I controlli seguenti non sono conformi al comportamento standard dell'evento Click del mouse:

- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.CheckBox>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.RadioButton>

  > [!NOTE]
  > Per il controllo <xref:System.Windows.Forms.ComboBox>, il comportamento dell'evento descritto di seguito si verifica se l'utente fa clic sul campo di modifica, sul pulsante o su una voce dell'elenco.

  - Clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Clic con pulsante destro: nessun evento Click generato

  - Doppio clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Doppio clic con pulsante destro: nessun evento Click generato

- Controlli <xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox> e <xref:System.Windows.Forms.CheckedListBox>

  > [!NOTE]
  > Il comportamento dell'evento descritto di seguito si verifica se l'utente fa clic in un punto qualsiasi di tali controlli.

  - Clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Clic con pulsante destro: nessun evento Click generato

  - Doppio clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>

  - Doppio clic con pulsante destro: nessun evento Click generato

- Controllo <xref:System.Windows.Forms.ListView>

  > [!NOTE]
  > Il comportamento dell'evento descritto di seguito si verifica solo quando l'utente fa clic sugli elementi nel controllo <xref:System.Windows.Forms.ListView>. Per i clic in altri punti del controllo non verranno generati eventi. Oltre agli eventi descritti di seguito esistono gli eventi <xref:System.Windows.Forms.ListView.BeforeLabelEdit> e <xref:System.Windows.Forms.ListView.AfterLabelEdit>, rilevanti se si desidera usare la convalida con il controllo <xref:System.Windows.Forms.ListView>.

  - Clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Clic con pulsante destro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Doppio clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>

  - Doppio clic con pulsante destro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>

- Controllo <xref:System.Windows.Forms.TreeView>

  > [!NOTE]
  > Il comportamento dell'evento descritto di seguito si verifica solo quando l'utente fa clic sugli elementi stessi o a destra degli elementi nel controllo <xref:System.Windows.Forms.TreeView>. Per i clic in altri punti del controllo non verranno generati eventi. Oltre agli eventi descritti di seguito, esistono gli eventi <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> e <xref:System.Windows.Forms.TreeView.AfterLabelEdit>, rilevanti se si desidera usare la convalida con il controllo <xref:System.Windows.Forms.TreeView>.

  - Clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Clic con pulsante destro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Doppio clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>

  - Doppio clic con pulsante destro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>

### <a name="painting-behavior-of-toggle-controls"></a>Comportamento del disegno dei controlli di attivazione/disimpostazione

I controlli di attivazione/disattivazione, quali quelli che derivano dalla classe <xref:System.Windows.Forms.ButtonBase>, presentano il seguente comportamento di disegno distintivo in combinazione con eventi Click del mouse:

1. L'utente preme il pulsante del mouse.

2. Il controllo viene disegnato nello stato premuto.

3. Viene generato l'evento <xref:System.Windows.Forms.Control.MouseDown>.

4. L'utente rilascia il pulsante del mouse.

5. Il controllo viene disegnato nello stato generato.

6. Viene generato l'evento <xref:System.Windows.Forms.Control.Click>.

7. Viene generato l'evento <xref:System.Windows.Forms.Control.MouseClick>.

8. Viene generato l'evento <xref:System.Windows.Forms.Control.MouseUp>.

    > [!NOTE]
    > Se l'utente sposta il puntatore all'esterno del controllo di attivazione/disattivazione mentre il pulsante del mouse è premuto, ad esempio spostando il mouse dal controllo <xref:System.Windows.Forms.Button> mentre il pulsante è premuto, il controllo di attivazione/disattivazione viene disegnato nello stato generato e si verifica solo l'evento <xref:System.Windows.Forms.Control.MouseUp>. In tale situazione l'evento <xref:System.Windows.Forms.Control.Click> o <xref:System.Windows.Forms.Control.MouseClick> non si verificherà.

## <a name="see-also"></a>Vedere anche

- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
