---
title: Unione delle voci di menu nel controllo MenuStrip
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 9fc2b40ef23d72db51853c124095b734a7646cda
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739048"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Unione delle voci di menu nel controllo MenuStrip Windows Form
Se si dispone di un'applicazione con interfaccia a documenti multipli (MDI), è possibile unire voci di menu o menu interi dal form figlio nei menu del form padre.  
  
 In questo argomento vengono descritti i concetti di base associati all'Unione delle voci di menu in un'applicazione MDI.  
  
## <a name="general-concepts"></a>Concetti generali  
 Le procedure di Unione coinvolgono sia una destinazione sia un controllo del codice sorgente:  
  
- La destinazione è il controllo <xref:System.Windows.Forms.MenuStrip> sul form principale o MDI padre in cui si uniscono le voci di menu.  
  
- L'origine è il controllo <xref:System.Windows.Forms.MenuStrip> sul form figlio MDI che contiene le voci di menu che si desidera unire nel menu di destinazione.  
  
 La proprietà <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> identifica la voce di menu il cui elenco a discesa viene popolato con i titoli degli elementi figlio MDI del form padre MDI corrente. Ad esempio, in genere si elencano elementi figlio MDI attualmente aperti nel menu **finestra** .  
  
 La proprietà <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> identifica le voci di menu provenienti da un <xref:System.Windows.Forms.MenuStrip> in un form figlio MDI.  
  
 È possibile unire le voci di menu in modo manuale o automatico. Le voci di menu si uniscono nello stesso modo per entrambi i metodi, ma il merge viene attivato in modo diverso, come illustrato nelle sezioni "Unione manuale" e "Unione automatica" più avanti in questo argomento. Nell'Unione manuale e automatica, ogni azione di merge influiscono sull'azione di unione successiva.  
  
 <xref:System.Windows.Forms.MenuStrip> Unione sposta le voci di menu da una <xref:System.Windows.Forms.ToolStrip> a un'altra anziché clonarle, come nel caso di <xref:System.Windows.Forms.MainMenu>.  
  
## <a name="mergeaction-values"></a>Valori MergeAction  
 Per impostare l'azione di Unione sulle voci di menu del <xref:System.Windows.Forms.MenuStrip> di origine, utilizzare la proprietà <xref:System.Windows.Forms.MergeAction>.  
  
 Nella tabella seguente viene descritto il significato e l'utilizzo tipico delle azioni di merge disponibili.  
  
|Valore MergeAction|Descrizione|Utilizzo tipico|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|Predefinita Aggiunge l'elemento di origine alla fine della raccolta dell'elemento di destinazione.|Aggiunta di voci di menu alla fine del menu quando viene attivata una parte del programma.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Aggiunge l'elemento di origine alla raccolta dell'elemento di destinazione, nel percorso specificato dalla proprietà <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> impostata sull'elemento di origine.|Aggiunta di voci di menu al centro o all'inizio del menu quando viene attivata una parte del programma.<br /><br /> Se il valore di <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> è identico per entrambe le voci di menu, viene aggiunto in ordine inverso. Impostare <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> in modo appropriato per mantenere l'ordine originale.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Trova una corrispondenza di testo oppure utilizza il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se non viene trovata alcuna corrispondenza di testo, quindi sostituisce la voce di menu di destinazione corrispondente con la voce di menu di origine.|Sostituzione di una voce di menu di destinazione con una voce di menu di origine con lo stesso nome che esegue un'operazione differente.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Trova una corrispondenza di testo oppure utilizza il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se non viene trovata alcuna corrispondenza di testo, quindi aggiunge tutti gli elementi a discesa dall'origine alla destinazione.|Compilazione di una struttura di menu che inserisce o aggiunge voci di menu in un sottomenu o rimuove le voci di menu da un sottomenu. Ad esempio, è possibile aggiungere una voce di menu da un figlio MDI a un menu principale <xref:System.Windows.Forms.MenuStrip>**Salva con nome** .<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> consente di spostarsi nella struttura dei menu senza eseguire alcuna azione. Fornisce un modo per valutare gli elementi successivi.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Trova una corrispondenza di testo oppure utilizza il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se non viene trovata alcuna corrispondenza di testo, quindi rimuove l'elemento dalla destinazione.|Rimozione di una voce di menu dalla <xref:System.Windows.Forms.MenuStrip>di destinazione.|  
  
## <a name="manual-merging"></a>Unione manuale  
 Solo i controlli <xref:System.Windows.Forms.MenuStrip> partecipano all'Unione automatica. Per combinare gli elementi di altri controlli, ad esempio <xref:System.Windows.Forms.ToolStrip> e controlli <xref:System.Windows.Forms.StatusStrip>, è necessario unirli manualmente, chiamando i metodi di <xref:System.Windows.Forms.ToolStripManager.Merge%2A> e <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> nel codice in base alle esigenze.  
  
## <a name="automatic-merging"></a>Unione automatica  
 È possibile utilizzare l'Unione automatica per le applicazioni MDI attivando il modulo di origine. Per usare un <xref:System.Windows.Forms.MenuStrip> in un'applicazione MDI, impostare la proprietà <xref:System.Windows.Forms.Form.MainMenuStrip%2A> sul <xref:System.Windows.Forms.MenuStrip> di destinazione in modo che le azioni di unione eseguite sul <xref:System.Windows.Forms.MenuStrip> di origine vengano riflesse nella <xref:System.Windows.Forms.MenuStrip>di destinazione.  
  
 È possibile attivare l'Unione automatica attivando il <xref:System.Windows.Forms.MenuStrip> sull'origine MDI. Al momento dell'attivazione, il <xref:System.Windows.Forms.MenuStrip> di origine viene unito alla destinazione MDI. Quando un nuovo form diventa attivo, l'Unione viene ripristinata nell'ultimo form e attivata nel nuovo form. È possibile controllare questo comportamento impostando la proprietà <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> in base alle esigenze in ogni <xref:System.Windows.Forms.ToolStripItem>e impostando la proprietà <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> in ogni <xref:System.Windows.Forms.MenuStrip>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- [Controllo MenuStrip](menustrip-control-windows-forms.md)
- [Procedura: Creare un elenco di finestre MDI con MenuStrip](how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)
- [Procedura: Impostare l'unione automatica dei menu per applicazioni MDI](how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
