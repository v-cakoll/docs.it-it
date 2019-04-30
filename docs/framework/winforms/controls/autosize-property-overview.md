---
title: Cenni preliminari sulla proprietà AutoSize
ms.date: 03/30/2017
helpviewer_keywords:
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
ms.openlocfilehash: 6d5c4a22f186ddc5811c4a4d5e79776decea9e50
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954297"
---
# <a name="autosize-property-overview"></a>Cenni preliminari sulla proprietà AutoSize
Il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà consente di modificarne le dimensioni, se necessario, in modo da riflettere il valore specificato da un controllo di <xref:System.Windows.Forms.Control.PreferredSize%2A> proprietà. Modificare il comportamento di ridimensionamento di controlli specifici impostando il `AutoSizeMode` proprietà.  
  
## <a name="autosize-behavior"></a>Comportamento di AutoSize  
 Solo alcuni controlli supportano il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà. Inoltre, alcuni controlli che supportano il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà supportano anche il `AutoSizeMode` proprietà.  
  
 Il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà produce un comportamento leggermente diverso, a seconda del tipo di controllo specifico e il valore del `AutoSizeMode` proprietà, se esiste una proprietà. Nella tabella seguente vengono descritti i comportamenti che sono sempre true e fornisce una breve descrizione della ognuno:  
  
|Comportamento sempre true|Descrizione|  
|--------------------------|-----------------|  
|Il ridimensionamento automatico è una funzionalità in fase di esecuzione.|Ciò significa mai aumenta o riduce un controllo e quindi non ha effetto.|  
|Se un controllo modifica la dimensione, il valore della relativa <xref:System.Windows.Forms.Control.Location%2A> proprietà rimane invariata.|Quando il relativo contenuto indurla a crescere, il controllo si espande verso destra e verso il basso. I controlli non raggiungano dimensioni a sinistra.|  
|Il <xref:System.Windows.Forms.Control.Dock%2A> e <xref:System.Windows.Forms.Control.Anchor%2A> delle proprietà vengono applicate quando <xref:System.Windows.Forms.Control.AutoSize%2A> è `true`.|Il valore del controllo <xref:System.Windows.Forms.Control.Location%2A> proprietà viene modificata in base al valore corretto.<br /><br /> **Nota** il <xref:System.Windows.Forms.Label> controllo rappresenta un'eccezione a questa regola. Quando si imposta il valore di un ancorati <xref:System.Windows.Forms.Label> del controllo <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà `true`, il <xref:System.Windows.Forms.Label> controllo non verrà ridimensionato.|  
|Un controllo <xref:System.Windows.Forms.Control.MaximumSize%2A> e <xref:System.Windows.Forms.Control.MinimumSize%2A> delle proprietà vengono rispettate sempre, indipendentemente dal valore del relativo <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.|Il <xref:System.Windows.Forms.Control.MaximumSize%2A> e <xref:System.Windows.Forms.Control.MinimumSize%2A> delle proprietà non sono interessate dal <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.|  
|Non è Nessuna dimensione minima impostata per impostazione predefinita.|Ciò significa che se un controllo è impostato su ridotte <xref:System.Windows.Forms.Control.AutoSize%2A> ed è privo di contenuto, il valore della relativa <xref:System.Windows.Forms.Control.Size%2A> proprietà è 0,0. In questo caso, il controllo verrà ridotto a un punto e non sarà immediatamente visibile.|  
|Se un controllo non implementa il <xref:System.Windows.Forms.Control.GetPreferredSize%2A> metodo, il <xref:System.Windows.Forms.Control.GetPreferredSize%2A> metodo restituisce l'ultimo valore assegnato al <xref:System.Windows.Forms.Control.Size%2A> proprietà.|Ciò significa che l'impostazione <xref:System.Windows.Forms.Control.AutoSize%2A> a `true` non avrà alcun effetto.|  
|Un controllo in una <xref:System.Windows.Forms.TableLayoutPanel> cella sempre si riduce per adattarsi alla cella fino al relativo <xref:System.Windows.Forms.Control.MinimumSize%2A> viene raggiunto.|Queste dimensioni viene imposto come una dimensione massima. Ciò non avviene quando la cella è parte di un <xref:System.Windows.Forms.SizeType.AutoSize> riga o colonna.|  
  
## <a name="autosizemode-property"></a>AutoSizeMode (proprietà)  
 Il `AutoSizeMode` proprietà offre un maggiore controllo con granularità fine tramite l'impostazione predefinita <xref:System.Windows.Forms.Control.AutoSize%2A> comportamento. Il `AutoSizeMode` proprietà specifica come un controllo Ridimensiona in base al contenuto. Il contenuto, ad esempio, potrebbe essere il testo per un <xref:System.Windows.Forms.Button> controllo o i controlli figlio per un contenitore.  
  
 La tabella seguente illustra il <xref:System.Windows.Forms.AutoSizeMode> impostazioni e una descrizione del comportamento determinato da ogni impostazione.  
  
|AutoSizeMode impostazione|Comportamento|  
|--------------------------|--------------|  
|GrowAndShrink|Il controllo viene ingrandito o si riduce per adattarsi al contenuto.<br /><br /> Il <xref:System.Windows.Forms.Control.MinimumSize%2A> e <xref:System.Windows.Forms.Control.MaximumSize%2A> i valori vengono applicati, ma il valore corrente del <xref:System.Windows.Forms.Control.Size%2A> proprietà viene ignorata.<br /><br /> Questo è lo stesso comportamento di controlli con il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà e nessun `AutoSizeMode` proprietà.|  
|GrowOnly|Il controllo si espande quanto necessario per includere il relativo contenuto, ma non riduce di sotto del valore specificato dalla relativa <xref:System.Windows.Forms.Control.Size%2A> proprietà.<br /><br /> Questo è il valore predefinito per `AutoSizeMode`.|  
  
## <a name="controls-that-support-the-autosize-property"></a>Controlli che supportano la proprietà AutoSize  
 Nella tabella seguente elenca i controlli che supportano il <xref:System.Windows.Forms.Control.AutoSize%2A> e `AutoSizeMode` proprietà.  
  
|Supporto per la proprietà AutoSize|Tipo di controllo|  
|----------------------|------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà supportata.<br />-Nessun `AutoSizeMode` proprietà.|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox> (<xref:System.Windows.Forms.TextBox> base)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà supportata.<br />-   `AutoSizeMode` proprietà supportata.|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|-Nessun <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## <a name="autosize-in-the-design-environment"></a>Ridimensiona automaticamente nell'ambiente di progettazione  
 La tabella seguente descrive il comportamento di ridimensionamento di un controllo in fase di progettazione, in base al valore del relativo <xref:System.Windows.Forms.Control.AutoSize%2A> e `AutoSizeMode` proprietà.  
  
 Eseguire l'override di <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> proprietà per determinare se un determinato controllo è in uno stato ridimensionabili dall'utente. Nella tabella seguente, "non è" significa <xref:System.Windows.Forms.Design.SelectionRules.Moveable> , solo "può" significa <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> e <xref:System.Windows.Forms.Design.SelectionRules.Moveable>.  
  
|Impostazioni di ridimensionamento automatico|Azione di ridimensionamento in fase di progettazione|  
|-----------------------|---------------------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-Nessun `AutoSizeMode` proprietà.|L'utente non è possibile ridimensionare il controllo in fase di progettazione, fatta eccezione per i controlli seguenti:<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>|L'utente non è possibile ridimensionare il controllo in fase di progettazione.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>|L'utente può ridimensionare il controllo in fase di progettazione. Quando il <xref:System.Windows.Forms.Control.Size%2A> viene impostata, l'utente può solo aumentare le dimensioni del controllo.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`, o <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà è nascosta.|Utente può ridimensionare il controllo in fase di progettazione.|  
  
> [!NOTE]
>  Per ottimizzare la produttività, le ombreggiature Windows Form Designer il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà per il <xref:System.Windows.Forms.Form> classe. In fase di progettazione, il modulo si comporti come se il <xref:System.Windows.Forms.Control.AutoSize%2A> è impostata su `false`, indipendentemente dall'impostazione effettiva. In fase di esecuzione, non viene effettuata alcuna facilitazione speciale e il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà viene applicata come specificato dall'impostazione della proprietà.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.PreferredSize%2A>
- <xref:System.Windows.Forms.Control.GetPreferredSize%2A>
