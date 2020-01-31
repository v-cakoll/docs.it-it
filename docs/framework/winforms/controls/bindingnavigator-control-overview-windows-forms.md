---
title: Panoramica del controllo BindingNavigator
ms.date: 03/30/2017
f1_keywords:
- DataNavigator
helpviewer_keywords:
- BindingNavigator control [Windows Forms], about BindingNavigator control
- records [Windows Forms], navigating on a form
- data [Windows Forms], navigating
- data navigation
ms.assetid: 4423eede-f8d1-4d02-822f-5bf8432680d0
ms.openlocfilehash: c2747a6801d4aa9cfde4227ffd5c29ca1de78d48
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744108"
---
# <a name="bindingnavigator-control-overview-windows-forms"></a>Panoramica del controllo BindingNavigator (Windows Form)
È possibile usare il controllo <xref:System.Windows.Forms.BindingNavigator> per fornire agli utenti un metodo standard per la ricerca e la modifica dei dati in un Windows Form. <xref:System.Windows.Forms.BindingNavigator> viene spesso usato con il componente <xref:System.Windows.Forms.BindingSource> per consentire agli utenti di spostarsi tra i vari record di dati in un form e apportare modifiche ai record.  
  
## <a name="how-the-bindingnavigator-works"></a>Funzionamento di BindingNavigator  

 Il controllo <xref:System.Windows.Forms.BindingNavigator> è composto da un <xref:System.Windows.Forms.ToolStrip> con una serie di oggetti <xref:System.Windows.Forms.ToolStripItem> per la maggior parte delle azioni correlate ai dati: aggiunta, eliminazione ed esplorazione. Per impostazione predefinita, il controllo <xref:System.Windows.Forms.BindingNavigator> contiene questi pulsanti standard. Lo screenshot seguente mostra il controllo <xref:System.Windows.Forms.BindingNavigator> in un modulo:
  
 ![Screenshot che mostra il controllo BindingNavigator.](./media/bindingnavigator-control-overview-windows-forms/bindingnavigator-control-form.gif)  
  
 La tabella seguente elenca i vari controlli con le relative funzioni.  
  
|Control|Funzione|  
|-------------|--------------|  
|Pulsante <xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A>|Inserisce una nuova riga nell'origine dati sottostante.|  
|Pulsante <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A>|Elimina la riga corrente dall'origine dati sottostante.|  
|Pulsante <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A>|Passa al primo elemento nell'origine dati sottostante.|  
|Pulsante <xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A>|Passa all'ultimo elemento nell'origine dati sottostante.|  
|Pulsante <xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A>|Passa all'elemento successivo nell'origine dati sottostante.|  
|Pulsante <xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A>|Passa all'elemento precedente nell'origine dati sottostante.|  
|Casella di testo <xref:System.Windows.Forms.BindingNavigator.PositionItem%2A>|Restituisce la posizione corrente nell'origine dati sottostante.|  
|Casella di testo <xref:System.Windows.Forms.BindingNavigator.CountItem%2A>|Restituisce il numero totale di elementi nell'origine dati sottostante.|  
  
 A ogni controllo contenuto nell'insieme corrisponde un membro del componente <xref:System.Windows.Forms.BindingSource> che fornisce la stessa funzionalità a livello di codice. Il pulsante <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A>, ad esempio, corrisponde al metodo <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> del componente <xref:System.Windows.Forms.BindingSource>, il pulsante <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> corrisponde al metodo <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> e così via.  
  
 Se i pulsanti predefiniti non sono adatti per l'applicazione in fase di sviluppo oppure se sono necessari altri pulsanti per supportare altri tipi di funzionalità, è possibile fornire pulsanti <xref:System.Windows.Forms.ToolStrip> personalizzati. Vedere anche [Procedura: Aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator Windows Forms](load-save-and-cancel-bindingnavigator.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- [Controllo BindingNavigator](bindingnavigator-control-windows-forms.md)
