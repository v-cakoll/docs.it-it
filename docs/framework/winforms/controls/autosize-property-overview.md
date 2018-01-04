---
title: "Cenni preliminari sulla proprietà AutoSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34f92bdc80f62225efe5e008f0893905f49da970
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="autosize-property-overview"></a>Cenni preliminari sulla proprietà AutoSize
Il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà consente a un controllo di modifica delle dimensioni, se necessario, per ottenere il valore specificato per il <xref:System.Windows.Forms.Control.PreferredSize%2A> proprietà. Modificare il comportamento di ridimensionamento di controlli specifici impostando il `AutoSizeMode` proprietà.  
  
## <a name="autosize-behavior"></a>Comportamento di AutoSize  
 Solo alcuni controlli supportano il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà. Inoltre, alcuni controlli che supportano il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà supportano anche il `AutoSizeMode` proprietà.  
  
 Il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà produce un comportamento leggermente diverso, in base al tipo di controllo specifico e il valore di `AutoSizeMode` proprietà, se la proprietà esiste. Nella tabella seguente vengono descritti i comportamenti che sono sempre true e fornisce una breve descrizione di ogni:  
  
|Comportamento sempre true.|Descrizione|  
|--------------------------|-----------------|  
|Ridimensionamento automatico è una funzionalità in fase di esecuzione.|Ciò significa mai aumenta o si riduce di un controllo e quindi non ha alcun effetto.|  
|Se le dimensioni, il valore di un controllo cambiano relativo <xref:System.Windows.Forms.Control.Location%2A> proprietà rimane invariata.|Quando il relativo contenuto causa l'aumento, il controllo si espande verso destra e verso il basso. I controlli non raggiungano dimensioni a sinistra.|  
|Il <xref:System.Windows.Forms.Control.Dock%2A> e <xref:System.Windows.Forms.Control.Anchor%2A> proprietà vengono rispettate quando <xref:System.Windows.Forms.Control.AutoSize%2A> è `true`.|Il valore del controllo <xref:System.Windows.Forms.Control.Location%2A> proprietà è impostata sul valore corretto.<br /><br /> **Nota** il <xref:System.Windows.Forms.Label> controllo rappresenta un'eccezione a questa regola. Quando si imposta il valore di un ancorato <xref:System.Windows.Forms.Label> del controllo <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà `true`, <xref:System.Windows.Forms.Label> controllo non verrà esteso.|  
|Un controllo <xref:System.Windows.Forms.Control.MaximumSize%2A> e <xref:System.Windows.Forms.Control.MinimumSize%2A> proprietà sono sempre rispettate, indipendentemente dal valore della relativa <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.|Il <xref:System.Windows.Forms.Control.MaximumSize%2A> e <xref:System.Windows.Forms.Control.MinimumSize%2A> proprietà non sono interessate dal <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.|  
|Non è prevista una dimensione minima impostata per impostazione predefinita.|Ciò significa che se un controllo è impostato su ridotte <xref:System.Windows.Forms.Control.AutoSize%2A> ed è privo di contenuto, il valore della relativa <xref:System.Windows.Forms.Control.Size%2A> proprietà è 0,0. In questo caso, il controllo verrà ridotto a un punto e non sarà visibile immediatamente.|  
|Se un controllo non implementa il <xref:System.Windows.Forms.Control.GetPreferredSize%2A> (metodo), il <xref:System.Windows.Forms.Control.GetPreferredSize%2A> metodo restituisce l'ultimo valore assegnato al <xref:System.Windows.Forms.Control.Size%2A> proprietà.|Ciò significa che l'impostazione <xref:System.Windows.Forms.Control.AutoSize%2A> a `true` avrà alcun effetto.|  
|Un controllo in un <xref:System.Windows.Forms.TableLayoutPanel> cella sempre ridotto per adattarsi alla cella fino a quando il relativo <xref:System.Windows.Forms.Control.MinimumSize%2A> viene raggiunto.|Questa dimensione viene applicata come una dimensione massima. Questo non avviene quando la cella fa parte di un <xref:System.Windows.Forms.SizeType.AutoSize> riga o colonna.|  
  
## <a name="autosizemode-property"></a>AutoSizeMode (proprietà)  
 Il `AutoSizeMode` proprietà fornisce un controllo più accurato tramite il valore predefinito <xref:System.Windows.Forms.Control.AutoSize%2A> comportamento. Il `AutoSizeMode` proprietà specifica come un controllo Ridimensiona al relativo contenuto. Il contenuto, ad esempio, può essere il testo per un <xref:System.Windows.Forms.Button> controllo o i controlli figlio per un contenitore.  
  
 La tabella seguente mostra il <xref:System.Windows.Forms.AutoSizeMode> impostazioni e una descrizione del comportamento determinato da ogni impostazione.  
  
|Impostazione di AutoSizeMode|Comportamento|  
|--------------------------|--------------|  
|GrowAndShrink|Il controllo aumenta o riduce per adattarsi al contenuto.<br /><br /> Il <xref:System.Windows.Forms.Control.MinimumSize%2A> e <xref:System.Windows.Forms.Control.MaximumSize%2A> i valori vengono applicati, ma il valore corrente di <xref:System.Windows.Forms.Control.Size%2A> proprietà viene ignorata.<br /><br /> Questo è lo stesso comportamento di controlli con il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà e nessun `AutoSizeMode` proprietà.|  
|GrowOnly|Il controllo aumenta quanto necessario per racchiudere il contenuto, ma non riduce rispetto al valore specificato dal relativo <xref:System.Windows.Forms.Control.Size%2A> proprietà.<br /><br /> Questo è il valore predefinito per `AutoSizeMode`.|  
  
## <a name="controls-that-support-the-autosize-property"></a>Controlli che supportano la proprietà AutoSize  
 Nella tabella seguente sono elencati i controlli che supportano il <xref:System.Windows.Forms.Control.AutoSize%2A> e `AutoSizeMode` proprietà.  
  
|Supporto di AutoSize|Tipo di controllo|  
|----------------------|------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A>proprietà supportata.<br />-Non `AutoSizeMode` proprietà.|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox>(<xref:System.Windows.Forms.TextBox> base)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A>proprietà supportata.<br />-   `AutoSizeMode`proprietà supportata.|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|-Non <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## <a name="autosize-in-the-design-environment"></a>AutoSize nell'ambiente di progettazione  
 La tabella seguente descrive il comportamento di ridimensionamento di un controllo in fase di progettazione, in base al valore del relativo <xref:System.Windows.Forms.Control.AutoSize%2A> e `AutoSizeMode` proprietà.  
  
 Eseguire l'override di <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> proprietà per determinare se un determinato controllo è in uno stato ridimensionabili dall'utente. Nella tabella seguente, "non è possibile" significa <xref:System.Windows.Forms.Design.SelectionRules.Moveable> solo "può" significa <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> e <xref:System.Windows.Forms.Design.SelectionRules.Moveable>.  
  
|Impostazioni di AutoSize|Azione di ridimensionamento in fase di progettazione|  
|-----------------------|---------------------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-Non `AutoSizeMode` proprietà.|L'utente non è possibile ridimensionare il controllo in fase di progettazione, tranne i seguenti controlli:<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>|L'utente non è possibile ridimensionare il controllo in fase di progettazione.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>|L'utente può ridimensionare il controllo in fase di progettazione. Quando il <xref:System.Windows.Forms.Control.Size%2A> è impostata, l'utente può solo aumentare le dimensioni del controllo.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`, o <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà è nascosta.|Utente può ridimensionare il controllo in fase di progettazione.|  
  
> [!NOTE]
>  Per ottimizzare la produttività, le ombre Progettazione Windows Form di <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà per il <xref:System.Windows.Forms.Form> classe. In fase di progettazione, il modulo si comporti come se il <xref:System.Windows.Forms.Control.AutoSize%2A> è impostata su `false`, indipendentemente dall'impostazione effettiva. In fase di esecuzione, non viene effettuata alcuna ristorazione speciali e <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà viene applicata come specificato dall'impostazione della proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.Control.PreferredSize%2A>  
 <xref:System.Windows.Forms.Control.GetPreferredSize%2A>
