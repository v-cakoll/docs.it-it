---
title: Unione delle voci di menu nel controllo MenuStrip Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 9a1f59a065faaa3a08a9d8a68973adb1faa5ed09
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64582924"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Unione delle voci di menu nel controllo MenuStrip Windows Form
Se si dispone di un'applicazione di interfaccia a documenti multipli (MDI), è possibile unire le voci di menu o i form figlio interi menu nei menu del form padre.  
  
 Questo argomento descrive i concetti di base associati all'unione delle voci di menu in un'applicazione MDI.  
  
## <a name="general-concepts"></a>Concetti generali  
 Le procedure di unione coinvolgono una destinazione e un controllo del codice sorgente:  
  
- La destinazione è il <xref:System.Windows.Forms.MenuStrip> controllo sul principale o form padre MDI in cui si uniscono le voci di menu.  
  
- L'origine è il <xref:System.Windows.Forms.MenuStrip> controllo sul form figlio MDI che contiene le voci di menu da unire nel menu di destinazione.  
  
 Il <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà identifica la voce di menu con elenco a discesa verrà popolato con i titoli di MDI corrente padre figlio MDI del form. Ad esempio, in genere vengono elencati gli elementi figlio MDI attualmente aperte nel **finestra** menu.  
  
 Il <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> identificata dalla proprietà quali le voci di menu provengono da un <xref:System.Windows.Forms.MenuStrip> su un form figlio MDI.  
  
 È possibile unire le voci di menu manualmente o automaticamente. Unire le voci di menu nello stesso modo per entrambi i metodi, ma il merge è attivato in modo diverso, come descritto nelle sezioni di "Unione manuale" e "Unione automatica" più avanti in questo argomento. Unione manuali e automatici, ogni azione di tipo merge interessa l'azione di tipo merge successiva.  
  
 <xref:System.Windows.Forms.MenuStrip> unione sposta le voci di menu da uno <xref:System.Windows.Forms.ToolStrip> a altro piuttosto che la clonazione, come avveniva con <xref:System.Windows.Forms.MainMenu>.  
  
## <a name="mergeaction-values"></a>Valori MergeAction  
 Per impostare l'azione di tipo merge nelle voci di menu nell'origine <xref:System.Windows.Forms.MenuStrip> utilizzando il <xref:System.Windows.Forms.MergeAction> proprietà.  
  
 La tabella seguente descrive il significato e l'utilizzo tipico delle azioni disponibili merge.  
  
|Valore MergeAction|Descrizione|Utilizzo tipico|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|(Impostazione predefinita) Aggiunge l'elemento di origine alla fine della raccolta dell'elemento di destinazione.|Aggiunta di voci di menu alla fine del menu di scelta quando viene attivato alcune parti del programma.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Aggiunge l'elemento di origine alla raccolta dell'elemento di destinazione, nel percorso specificato per il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> proprietà è impostata sull'elemento di origine.|Aggiunta di voci di menu al centro o l'inizio del menu di scelta quando viene attivato alcune parti del programma.<br /><br /> Se il valore di <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> è lo stesso per entrambe le voci di menu, vengono aggiunti in ordine inverso. Impostare <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> in modo appropriato per mantenere l'ordine originale.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Trova una corrispondenza il testo o Usa il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se viene trovata alcuna corrispondenza il testo e quindi sostituisce la voce di menu corrispondente di destinazione con la voce di menu di origine.|Sostituzione di una voce di menu di destinazione con una voce di menu di origine con lo stesso nome che esegue operazioni differenti.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Trova una corrispondenza il testo o Usa il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se viene trovata alcuna corrispondenza il testo e quindi aggiunge tutti gli elementi elenco a discesa dall'origine alla destinazione.|Creazione di una struttura di menu che inserisce o aggiunge voci di menu in un sottomenu o rimuove le voci di menu da un sottomenu. Ad esempio, è possibile aggiungere una voce di menu da un figlio MDI di una funzione main <xref:System.Windows.Forms.MenuStrip> **Salva con nome** menu.<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> Consente di passare attraverso la struttura di menu senza eseguire alcuna azione. Fornisce un modo per valutare gli elementi successivi.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Trova una corrispondenza il testo o Usa il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se viene trovata alcuna corrispondenza il testo e quindi rimuove l'elemento dalla destinazione.|Rimozione di una voce di menu dalla destinazione <xref:System.Windows.Forms.MenuStrip>.|  
  
## <a name="manual-merging"></a>Unione manuale  
 Solo <xref:System.Windows.Forms.MenuStrip> controlli partecipano il merge automatico. Per combinare gli elementi di altri controlli, ad esempio <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.StatusStrip> controlli, è necessario unirli manualmente, chiamando la <xref:System.Windows.Forms.ToolStripManager.Merge%2A> e <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> metodi nel codice in base alle esigenze.  
  
## <a name="automatic-merging"></a>Unione automatica  
 È possibile usare il merge automatico per le applicazioni MDI attivando il modulo di origine. Usare un <xref:System.Windows.Forms.MenuStrip> in un'applicazione MDI, impostare il <xref:System.Windows.Forms.Form.MainMenuStrip%2A> proprietà di destinazione <xref:System.Windows.Forms.MenuStrip> in modo che le azioni di unione eseguita sull'origine <xref:System.Windows.Forms.MenuStrip> vengono riflesse nella destinazione <xref:System.Windows.Forms.MenuStrip>.  
  
 È possibile attivare il merge automatico attivando il <xref:System.Windows.Forms.MenuStrip> sull'origine MDI. Dopo l'attivazione, l'origine <xref:System.Windows.Forms.MenuStrip> viene unito nella destinazione MDI. Quando un nuovo form diventa attivo, l'unione è ripristinato sull'ultimo modulo e attivata al momento il nuovo form. È possibile controllare questo comportamento impostando il <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> proprietà in base alle esigenze in ogni <xref:System.Windows.Forms.ToolStripItem>e impostando le <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> su ogni proprietà <xref:System.Windows.Forms.MenuStrip>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- [Controllo MenuStrip](menustrip-control-windows-forms.md)
- [Procedura: Creare un elenco di finestre MDI con MenuStrip](how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)
- [Procedura: Impostare l'unione automatica dei Menu per applicazioni MDI](how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
