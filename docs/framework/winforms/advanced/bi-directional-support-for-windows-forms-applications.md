---
title: Supporto bidirezionale
ms.date: 09/30/2017
helpviewer_keywords:
- globalization [Windows Forms], bi-directional support in Windows
- Windows Forms, international
- localization [Windows Forms], bi-directional support in Windows
- bi-directional language support [Windows Forms], Windows applications
- Windows Forms, bi-directional support
ms.openlocfilehash: 8b2e842fc08be78b74cede85927352fafca7bc8f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742070"
---
# <a name="bi-directional-support-for-windows-forms-applications"></a>Supporto bidirezionale per le applicazioni Windows Forms
È possibile usare Visual Studio per creare applicazioni basate su Windows che supportano lingue bidirezionali (da destra a sinistra) come l'arabo e l'ebraico. Sono inclusi form standard, finestre di dialogo, form MDI e tutti i controlli che è possibile usare in questi form, ovvero tutti gli oggetti nello spazio dei nomi <xref:System.Windows.Forms.Control>.

## <a name="culture-support"></a>Supporto delle impostazioni cultura
 Le impostazioni cultura e le impostazioni cultura dell'interfaccia utente determinano il funzionamento di un'applicazione rispetto a date, orari, valuta e altre informazioni. Il supporto per le impostazioni cultura e le impostazioni cultura dell'interfaccia utente per le lingue bidirezionali è uguale a quello per le altre lingue. Per altre informazioni, vedere [classi specifiche delle impostazioni cultura per Windows Form e Web Form globali](/visualstudio/ide/globalizing-and-localizing-applications).

## <a name="righttoleft-and-righttoleftlayout-properties"></a>Proprietà RightToLeft e RightToLeftLayout
 La classe base <xref:System.Windows.Forms.Control> da cui derivano i form include una proprietà <xref:System.Windows.Forms.Control.RightToLeft%2A> che è possibile impostare per modificare l'ordine di lettura di un form e dei relativi controlli. Se si imposta la proprietà <xref:System.Windows.Forms.Control.RightToLeft%2A>, i controlli sul form erediteranno questa impostazione per impostazione predefinita. Tuttavia, è anche possibile impostare singolarmente la proprietà <xref:System.Windows.Forms.Control.RightToLeft%2A> nella maggior parte dei controlli. Vedere anche [Procedura: visualizzare il testo da destra a sinistra in Windows Form per la globalizzazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100)).

 L'effetto della proprietà <xref:System.Windows.Forms.Control.RightToLeft%2A> può essere diverso da un controllo a un altro. In alcuni controlli, questa proprietà imposta soltanto l'ordine di lettura, come nei controlli <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.TreeView> e <xref:System.Windows.Forms.ToolTip>. In altri controlli, la proprietà <xref:System.Windows.Forms.Control.RightToLeft%2A> modifica sia ordine di lettura che il layout, ad esempio, nei controlli <xref:System.Windows.Forms.RadioButton>, <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.CheckBox>. Altri controlli richiedono che la proprietà <xref:System.Windows.Forms.Form.RightToLeftLayout%2A> venga applicata per eseguire il mirroring del layout da destra a sinistra. La tabella seguente fornisce informazioni dettagliate sugli effetti delle proprietà <xref:System.Windows.Forms.Control.RightToLeft%2A> e <xref:System.Windows.Forms.Form.RightToLeftLayout%2A> sui singoli controlli di Windows Form.

|Controllo/Componente|Effetto della proprietà RightToLeft|Effetto della proprietà RightToLeftLayout|Richiede il mirroring?|
|------------------------|------------------------------------|------------------------------------------|-------------------------|
|<xref:System.Windows.Forms.Button>|Imposta l'ordine di lettura da destra a sinistra. Inverte <xref:System.Windows.Forms.ButtonBase.TextAlign%2A>, <xref:System.Windows.Forms.ButtonBase.ImageAlign%2A> e <xref:System.Windows.Forms.ButtonBase.TextImageRelation%2A>|Nessun effetto|No|
|<xref:System.Windows.Forms.CheckBox>|La casella di controllo viene visualizzata a destra del testo|Nessun effetto|No|
|<xref:System.Windows.Forms.CheckedListBox>|Tutte le caselle di controllo vengono visualizzate a destra del testo|Nessun effetto|No|
|<xref:System.Windows.Forms.ColorDialog>|Non interessato. Dipende dal linguaggio del sistema operativo|Nessun effetto|No|
|<xref:System.Windows.Forms.ComboBox>|Gli elementi nel controllo della casella combinata sono allineati a destra|Nessun effetto|No|
|<xref:System.Windows.Forms.ContextMenu>|Viene visualizzato allineato a destra con ordine di lettura da destra a sinistra|Nessun effetto|No|
|<xref:System.Windows.Forms.DataGrid>|Viene visualizzato allineato a destra con ordine di lettura da destra a sinistra|Nessun effetto|No|
|<xref:System.Windows.Forms.DataGridView>|Influisce sul layout di controllo e sull'ordine di lettura da destra a sinistra|Nessun effetto|No|
|<xref:System.Windows.Forms.DateTimePicker>|Non interessato. Dipende dal linguaggio del sistema operativo|Esegue il mirroring del controllo|Sì|
|<xref:System.Windows.Forms.DomainUpDown>|Allinea a sinistra i pulsanti SU e GIÙ|Nessun effetto|No|
|<xref:System.Windows.Forms.ErrorProvider>|Non supportato|Nessun effetto|No|
|<xref:System.Windows.Forms.FontDialog>|Dipende dalla lingua del sistema operativo|Nessun effetto|No|
|<xref:System.Windows.Forms.Form>|Imposta l'ordine di lettura da destra a sinistra e inverte le barre di scorrimento|Esegue il mirroring del form|Sì|
|<xref:System.Windows.Forms.GroupBox>|La barra del titolo viene visualizzata allineata a destra. I controlli figlio possono ereditare questa proprietà.|Usare <xref:System.Windows.Forms.TableLayoutPanel> all'interno del controllo per il supporto al mirroring da destra a sinistra|No|
|<xref:System.Windows.Forms.HScrollBar>|Inizia con la casella di scorrimento (pulsante di scorrimento) allineata a destra|Nessun effetto|No|
|<xref:System.Windows.Forms.ImageList>|Non richiesto|Nessun effetto|No|
|<xref:System.Windows.Forms.Label>|Visualizzato allineato a destra. Inverte <xref:System.Windows.Forms.Label.TextAlign%2A> e <xref:System.Windows.Forms.Label.ImageAlign%2A>|Nessun effetto|No|
|<xref:System.Windows.Forms.LinkLabel>|Visualizzato allineato a destra. Inverte <xref:System.Windows.Forms.Label.TextAlign%2A> e <xref:System.Windows.Forms.Label.ImageAlign%2A>|Nessun effetto|No|
|<xref:System.Windows.Forms.ListBox>|Gli elementi sono allineati a destra|Nessun effetto|No|
|<xref:System.Windows.Forms.ListView>|Imposta l'ordine di lettura da destra a sinistra; gli elementi rimangono allineati a sinistra|Esegue il mirroring del controllo|Sì|
|<xref:System.Windows.Forms.MainMenu>|Visualizzato allineato a destra con ordine di lettura da destra a sinistra in fase di esecuzione (non in fase di progettazione)|Nessun effetto|No|
|<xref:System.Windows.Forms.MaskedTextBox>|Visualizza il testo da destra a sinistra.|Nessun effetto|No|
|<xref:System.Windows.Forms.MonthCalendar>|Non interessato. Dipende dal linguaggio del sistema operativo|Esegue il mirroring del controllo|Sì|
|<xref:System.Windows.Forms.NotifyIcon>|Non supportato|Non supportato|No|
|<xref:System.Windows.Forms.NumericUpDown>|I pulsanti SU e GIÙ sono allineati a sinistra|Nessun effetto|No|
|<xref:System.Windows.Forms.OpenFileDialog>|Nei sistemi operativi da destra a sinistra, l'impostazione della proprietà <xref:System.Windows.Forms.Control.RightToLeft> del form che lo contiene su <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType> localizza la finestra di dialogo |Nessun effetto|No|
|<xref:System.Windows.Forms.PageSetupDialog>|Non interessato. Dipende dal linguaggio del sistema operativo|Nessun effetto|No|
|<xref:System.Windows.Forms.Panel>|I controlli figlio possono ereditare questa proprietà|Usare <xref:System.Windows.Forms.TableLayoutPanel> all'interno del controllo per il supporto da destra a sinistra|Sì|
|<xref:System.Windows.Forms.PictureBox>|Non supportato|Nessun effetto|No|
|<xref:System.Windows.Forms.PrintDialog>|Non interessato. Dipende dal linguaggio del sistema operativo|Nessun effetto|No|
|<xref:System.Drawing.Printing.PrintDocument>|La barra di scorrimento verticale diventa allineata a sinistra e la barra di scorrimento orizzontale inizia da sinistra|Nessun effetto|No|
|<xref:System.Windows.Forms.PrintPreviewDialog>|Non supportato|Non supportato|No|
|<xref:System.Windows.Forms.ProgressBar>|Non interessato da questa proprietà|Esegue il mirroring del controllo|Sì|
|<xref:System.Windows.Forms.RadioButton>|Il pulsante di opzione viene visualizzato a destra del testo|Nessun effetto|No|
|<xref:System.Windows.Forms.RichTextBox>|Gli elementi del controllo che includono testo vengono visualizzati da destra a sinistra con ordine di lettura da destra a sinistra|Nessun effetto|No|
|<xref:System.Windows.Forms.SaveFileDialog>|Non interessato. Dipende dal linguaggio del sistema operativo|Nessun effetto|No|
|<xref:System.Windows.Forms.SplitContainer>|Il layout del pannello viene invertito; la barra di scorrimento verticale viene visualizzata a sinistra; la barra di scorrimento orizzontale inizia da destra|Usare <xref:System.Windows.Forms.TableLayoutPanel> per eseguire il mirroring dell'ordine dei controlli figlio|No|
|<xref:System.Windows.Forms.Splitter>|Non supportato|Nessun effetto|No|
|<xref:System.Windows.Forms.StatusBar>|Non supportato. In alternativa, usare <xref:System.Windows.Forms.StatusStrip>|Nessun effetto. In alternativa, usare <xref:System.Windows.Forms.StatusStrip>|No|
|<xref:System.Windows.Forms.TabControl>|Non interessato da questa proprietà|Esegue il mirroring del controllo|Sì|
|<xref:System.Windows.Forms.TextBox>|Visualizza il testo da destra a sinistra con ordine di lettura da destra a sinistra|Nessun effetto|No|
|<xref:System.Windows.Forms.Timer>|Non richiesto|Non richiesto|No|
|<xref:System.Windows.Forms.ToolBar>|Non interessato da questa proprietà. In alternativa, usare <xref:System.Windows.Forms.ToolStrip>|Nessun effetto. In alternativa, usare <xref:System.Windows.Forms.ToolStrip>|Sì|
|<xref:System.Windows.Forms.ToolTip>|Imposta l'ordine di lettura da destra a sinistra|Nessun effetto|No|
|<xref:System.Windows.Forms.TrackBar>|Lo scorrimento o l'avanzamento inizia da destra. Quando <xref:System.Windows.Forms.TrackBar.Orientation%2A> è verticale, i segni di graduazione iniziano da destra|Nessun effetto|No|
|<xref:System.Windows.Forms.TreeView>|Imposta solo l'ordine di lettura da destra a sinistra|Esegue il mirroring del controllo|Sì|
|<xref:System.Windows.Forms.UserControl>|La barra di scorrimento verticale viene visualizzata a sinistra. La barra di scorrimento orizzontale ha il pulsante di scorrimento a destra|Nessun supporto diretto. Usare <xref:System.Windows.Forms.TableLayoutPanel>|No|
|<xref:System.Windows.Forms.VScrollBar>|Visualizzato sul lato sinistro anziché sul lato destro dei controlli scorrevoli|Nessun effetto|No|

## <a name="encoding"></a>Codifica
 I Windows Form supportano Unicode, pertanto è possibile includere qualsiasi set di caratteri durante la creazione di applicazioni bidirezionali. Tuttavia, non tutti i controlli di Windows Form supportano Unicode su tutte le piattaforme.

## <a name="gdi"></a>GDI+
 È possibile utilizzare GDI+ per creare il testo con ordine di lettura da destra a sinistra. Il metodo <xref:System.Drawing.Graphics.DrawString%2A>, usato per creare il testo, supporta un parametro `StringFormat` che è possibile impostare sul membro <xref:System.Drawing.StringFormatFlags.DirectionRightToLeft> dell'enumerazione <xref:System.Drawing.StringFormatFlags> per invertire il punto di origine del testo.

## <a name="common-dialog-boxes"></a>Finestre di dialogo comuni
 Gli strumenti di sistema, ad esempio la finestra di dialogo Apri file, sono controllati da Windows. Gli elementi del linguaggio vengono ereditati dal sistema operativo. Se si usa una versione di Windows con le impostazioni di lingua appropriate, queste finestre di dialogo funzioneranno correttamente con le lingue bidirezionali.

 Allo stesso modo, le finestre di messaggio vengono controllate dal sistema operativo e supportano il testo bidirezionale. Le barre del titolo nei pulsanti delle finestre di messaggio sono basate sull'impostazione della lingua corrente. Per impostazione predefinita, le finestre di messaggio non usano l'ordine di lettura da destra a sinistra, ma è possibile specificare un parametro per modificare l'ordine di lettura quando vengono visualizzate.

## <a name="righttoleft-scrollbars-and-scrollablecontrol"></a>RightToLeft, barre di scorrimento e ScrollableControl
 Esiste attualmente una limitazione in Windows Form che impedisce il corretto funzionamento di tutte le classi derivate da <xref:System.Windows.Forms.ScrollableControl> quando <xref:System.Windows.Forms.Control.RightToLeft%2A> è abilitato e <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> è impostato su <xref:System.Windows.Forms.RightToLeft.Yes>. Ad esempio, si supponga di inserire un controllo come <xref:System.Windows.Forms.Panel>, o una classe contenitore derivata da <xref:System.Windows.Forms.Panel> (ad esempio <xref:System.Windows.Forms.FlowLayoutPanel> o <xref:System.Windows.Forms.TableLayoutPanel>), nel form. Se si imposta <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> nel contenitore su <xref:System.Windows.Forms.RightToLeft.Yes> e si imposta la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> di uno o più controlli all'interno del contenitore su <xref:System.Windows.Forms.AnchorStyles.Right>, non verrà visualizzata alcuna barra di scorrimento. La classe derivata da <xref:System.Windows.Forms.ScrollableControl> agisce come se <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> fosse impostato su <xref:System.Windows.Forms.RightToLeft.No>.

 Attualmente, l'unica soluzione alternativa consiste nell'annidare <xref:System.Windows.Forms.ScrollableControl> in un altro <xref:System.Windows.Forms.ScrollableControl>. Ad esempio, se è necessario <xref:System.Windows.Forms.TableLayoutPanel> per lavorare in questa situazione, è possibile inserirlo all'interno di un controllo <xref:System.Windows.Forms.Panel> e impostare <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> in <xref:System.Windows.Forms.Panel> su <xref:System.Windows.Forms.RightToLeft.Yes>.

## <a name="mirroring"></a>Mirroring
 *Mirroring* fa riferimento all'inversione del layout degli elementi dell'interfaccia utente in modo tale che scorrano da destra a sinistra. In un Windows Form con mirroring, ad esempio, i pulsanti Riduci a icona, Ingrandisci e Chiudi vengono visualizzati all'estrema sinistra della barra del titolo, non all'estrema destra.

 L'impostazione di un form o di una proprietà del controllo <xref:System.Windows.Forms.Control.RightToLeft%2A> su `true` inverte l'ordine di lettura degli elementi in un form, ma questa impostazione non inverte il layout da destra a sinistra, ovvero non causa il mirroring. Ad esempio, se si imposta questa proprietà i pulsanti **Riduci a icona**, **Ingrandisci** e **Chiudi** nella barra del titolo del modulo non vengono spostati sul lato sinistro del modulo. Analogamente, alcuni controlli, ad esempio <xref:System.Windows.Forms.TreeView>, richiedono il mirroring per modificare la visualizzazione affinché diventi appropriata per l'arabo o l'ebraico. È possibile eseguire il mirroring di questi controlli impostando la proprietà <xref:System.Windows.Forms.Form.RightToLeftLayout%2A>.

 È possibile creare versioni con mirroring dei controlli seguenti:

- <xref:System.Windows.Forms.ColumnHeader.ListView%2A>

- <xref:System.Windows.Forms.Panel>

- <xref:System.Windows.Forms.StatusBar>

- <xref:System.Windows.Forms.TabControl>

- <xref:System.Windows.Forms.TabPage>

- <xref:System.Windows.Forms.ToolBar>

- <xref:System.Windows.Forms.TreeView>

 Alcuni controlli sono sealed, quindi non è possibile derivare un nuovo controllo da essi. Questi controlli includono <xref:System.Windows.Forms.ImageList> e <xref:System.Windows.Forms.ProgressBar>.

## <a name="see-also"></a>Vedere anche

- [Supporto bidirezionale per applicazioni Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/6eedwbtt(v=vs.100))
