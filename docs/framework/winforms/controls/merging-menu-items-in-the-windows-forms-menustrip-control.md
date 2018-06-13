---
title: Unione delle voci di menu nel controllo MenuStrip Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 2782ae483d673f8f1eccab10876aca858737260a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539789"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Unione delle voci di menu nel controllo MenuStrip Windows Form
Se si dispone di un'applicazione con interfaccia a documenti multipli (MDI), è possibile unire le voci di menu o interi menu del form figlio nel menu del form padre.  
  
 Questo argomento descrive i concetti di base associati all'unione di voci di menu in un'applicazione MDI.  
  
## <a name="general-concepts"></a>Concetti generali  
 Le procedure di unione coinvolgono una destinazione e un controllo del codice sorgente:  
  
-   La destinazione è il <xref:System.Windows.Forms.MenuStrip> controllo sul principale o form padre MDI in cui vengono unite le voci di menu.  
  
-   L'origine è il <xref:System.Windows.Forms.MenuStrip> controllo sul form figlio MDI che contiene le voci di menu che si desidera unire nel menu di destinazione.  
  
 Il <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà identifica la voce di menu, il cui elenco di riepilogo a discesa verrà popolato con i titoli di MDI corrente padre figlio MDI del form. Ad esempio, in genere vengono elencati gli elementi figlio MDI attualmente aperte nel **finestra** menu.  
  
 Il <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> proprietà identifica quali voci di menu provengono da un <xref:System.Windows.Forms.MenuStrip> in un form figlio MDI.  
  
 È possibile unire le voci di menu manualmente o automaticamente. Unire le voci di menu nello stesso modo per entrambi i metodi, ma l'unione viene attivata in modo diverso, come descritto nelle sezioni "Unione manuale" e "Unione automatica" più avanti in questo argomento. L'unione manuale e automatica, ogni azione di tipo merge influisce l'azione successiva di tipo merge.  
  
 <xref:System.Windows.Forms.MenuStrip> l'unione consente di spostare voci di menu da uno <xref:System.Windows.Forms.ToolStrip> a un altro anziché duplicarle, come nel caso con <xref:System.Windows.Forms.MainMenu>.  
  
## <a name="mergeaction-values"></a>Valori di MergeAction  
 Per impostare l'azione di unione nelle voci di menu nell'origine <xref:System.Windows.Forms.MenuStrip> utilizzando il <xref:System.Windows.Forms.MergeAction> proprietà.  
  
 Nella tabella seguente viene descritto il significato e l'utilizzo tipico di azioni di unione disponibili.  
  
|Valore di MergeAction|Descrizione|Utilizzo tipico|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|(Impostazione predefinita) Aggiunge l'elemento di origine alla fine della raccolta dell'elemento di destinazione.|Aggiunta voci di menu alla fine del menu quando viene attivata una parte del programma.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Aggiunge l'elemento di origine alla raccolta dell'elemento di destinazione, nel percorso specificato per il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> impostata sull'elemento di origine.|Aggiunta voci di menu al centro o l'inizio del menu quando viene attivata una parte del programma.<br /><br /> Se il valore di <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> è uguale per entrambe le voci di menu, vengono aggiunti in ordine inverso. Impostare <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> in modo appropriato per mantenere l'ordine originale.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Trova una corrispondenza di testo o Usa il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se non viene trovato e quindi lo sostituisce la voce di menu di destinazione corrispondente alla voce di menu di origine.|Sostituzione di una voce di menu di destinazione con una voce di menu di origine con lo stesso nome che esegue un'operazione diversa.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Trova una corrispondenza di testo o Usa il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se non viene trovato e quindi aggiunge tutte le voci di menu a discesa dall'origine alla destinazione.|Compilazione di una struttura di menu che inserisce o aggiunge voci di menu in un sottomenu o rimuove le voci di menu da un sottomenu. Ad esempio, è possibile aggiungere una voce di menu da un figlio MDI di una funzione main <xref:System.Windows.Forms.MenuStrip> **Salva con nome** menu.<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> Consente di spostarsi nella struttura di menu senza eseguire alcuna azione. Fornisce un modo per valutare gli elementi successivi.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Trova una corrispondenza di testo o Usa il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se non viene trovato e quindi rimuove l'elemento dalla destinazione.|Rimozione di una voce di menu dalla destinazione <xref:System.Windows.Forms.MenuStrip>.|  
  
## <a name="manual-merging"></a>Unione manuale  
 Solo <xref:System.Windows.Forms.MenuStrip> controlli partecipano all'unione automatica. Per combinare gli elementi di altri controlli, ad esempio <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.StatusStrip> controlli, è necessario unirli manualmente, mediante la chiamata di <xref:System.Windows.Forms.ToolStripManager.Merge%2A> e <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> metodi nel codice come richiesto.  
  
## <a name="automatic-merging"></a>Unione automatica  
 È possibile utilizzare l'unione automatica per le applicazioni MDI attivando il modulo di origine. Per utilizzare un <xref:System.Windows.Forms.MenuStrip> in un'applicazione MDI, impostare il <xref:System.Windows.Forms.Form.MainMenuStrip%2A> proprietà di destinazione <xref:System.Windows.Forms.MenuStrip> in modo che le azioni di unione eseguita sull'origine <xref:System.Windows.Forms.MenuStrip> vengono riflesse nella destinazione <xref:System.Windows.Forms.MenuStrip>.  
  
 È possibile attivare l'unione automatica attivando il <xref:System.Windows.Forms.MenuStrip> sull'origine MDI. Dopo l'attivazione, l'origine <xref:System.Windows.Forms.MenuStrip> viene unito nella destinazione MDI. Quando un nuovo form diventa attivo, l'unione è annullata sull'ultimo form e attivato il nuovo modulo. È possibile controllare questo comportamento impostando la <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> proprietà in base alle esigenze in ogni <xref:System.Windows.Forms.ToolStripItem>e impostando il <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> proprietà in ogni <xref:System.Windows.Forms.MenuStrip>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 [Controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [Procedura: Creare un elenco di finestre MDI con MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)  
 [Procedura: Impostare l'unione automatica dei menu per applicazioni MDI](../../../../docs/framework/winforms/controls/how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
