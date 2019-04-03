---
title: Cenni preliminari sul controllo BindingNavigator (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- DataNavigator
helpviewer_keywords:
- BindingNavigator control [Windows Forms], about BindingNavigator control
- records [Windows Forms], navigating on a form
- data [Windows Forms], navigating
- data navigation
ms.assetid: 4423eede-f8d1-4d02-822f-5bf8432680d0
ms.openlocfilehash: b6413c8481a021afa34b7de228df14c109a50889
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834231"
---
# <a name="bindingnavigator-control-overview-windows-forms"></a>Cenni preliminari sul controllo BindingNavigator (Windows Form)
È possibile usare il controllo <xref:System.Windows.Forms.BindingNavigator> per fornire agli utenti un metodo standard per la ricerca e la modifica dei dati in un Windows Form. <xref:System.Windows.Forms.BindingNavigator> viene spesso usato con il componente <xref:System.Windows.Forms.BindingSource> per consentire agli utenti di spostarsi tra i vari record di dati in un form e apportare modifiche ai record.  
  
## <a name="how-the-bindingnavigator-works"></a>Funzionamento di BindingNavigator  

 Il controllo <xref:System.Windows.Forms.BindingNavigator> è composto da un <xref:System.Windows.Forms.ToolStrip> con una serie di oggetti <xref:System.Windows.Forms.ToolStripItem> per la maggior parte delle azioni correlate ai dati: aggiunta, eliminazione ed esplorazione. Per impostazione predefinita, il controllo <xref:System.Windows.Forms.BindingNavigator> contiene questi pulsanti standard. La schermata seguente mostra il <xref:System.Windows.Forms.BindingNavigator> controllo in un form:
  
 ![Screenshot che mostra il controllo BindingNavigator.](./media/bindingnavigator-control-overview-windows-forms/bindingnavigator-control-form.gif)  
  
 La tabella seguente elenca i vari controlli con le relative funzioni.  
  
|Control|Funzione|  
|-------------|--------------|  
|<xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> Pulsante|Inserisce una nuova riga nell'origine dati sottostante.|  
|<xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> Pulsante|Elimina la riga corrente dall'origine dati sottostante.|  
|<xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> Pulsante|Passa al primo elemento nell'origine dati sottostante.|  
|<xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> Pulsante|Passa all'ultimo elemento nell'origine dati sottostante.|  
|<xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A> Pulsante|Passa all'elemento successivo nell'origine dati sottostante.|  
|<xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A> Pulsante|Passa all'elemento precedente nell'origine dati sottostante.|  
|Casella di testo <xref:System.Windows.Forms.BindingNavigator.PositionItem%2A>|Restituisce la posizione corrente nell'origine dati sottostante.|  
|Casella di testo <xref:System.Windows.Forms.BindingNavigator.CountItem%2A>|Restituisce il numero totale di elementi nell'origine dati sottostante.|  
  
 A ogni controllo contenuto nell'insieme corrisponde un membro del componente <xref:System.Windows.Forms.BindingSource> che fornisce la stessa funzionalità a livello di codice. Il pulsante <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A>, ad esempio, corrisponde al metodo <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> del componente <xref:System.Windows.Forms.BindingSource>, il pulsante <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> corrisponde al metodo <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> e così via.  
  
 Se i pulsanti predefiniti non sono adatti per l'applicazione in fase di sviluppo oppure se sono necessari altri pulsanti per supportare altri tipi di funzionalità, è possibile fornire pulsanti <xref:System.Windows.Forms.ToolStrip> personalizzati. Vedere anche [come: Aggiungere carica, Salva e Annulla i pulsanti per i Windows Form controllo BindingNavigator](load-save-and-cancel-bindingnavigator.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- [Controllo BindingNavigator](bindingnavigator-control-windows-forms.md)
