---
title: Controllo DomainUpDown (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: c23f374f1ec9cab6e43b12d32b97c40533ac36cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="domainupdown-control-windows-forms"></a>Controllo DomainUpDown (Windows Form)
Windows Form <xref:System.Windows.Forms.DomainUpDown> controllo simile a una combinazione di una casella di testo e una coppia di pulsanti per spostarsi verso l'alto o verso il basso all'interno di un elenco. Il controllo Visualizza e imposta una stringa di testo da un elenco di scelte. L'utente può selezionare la stringa facendo clic su e giù per spostarsi in un elenco, premendo i tasti freccia su e giù o digitando una stringa che corrisponde a un elemento nell'elenco. Un possibile utilizzo di questo controllo è per la selezione di elementi da un elenco in ordine alfabetico dei nomi. (Per ordinare l'elenco, impostare il <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> proprietà `true`.) La funzione di questo controllo è molto simile alla casella di riepilogo o casella combinata, ma richiede poco spazio.  
  
 Le proprietà principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, e <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Il <xref:System.Windows.Forms.DomainUpDown.Items%2A> proprietà contiene l'elenco di oggetti i cui valori di testo vengono visualizzati nel controllo. Se <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> è impostato su `false`, il controllo completa automaticamente il testo che l'utente digita e a esso corrispondente a un valore nell'elenco. Se <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> è impostato su `true`, lo scorrimento oltre l'ultimo elemento verrà visualizzata al primo elemento nell'elenco e viceversa. I metodi principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> e <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Questo controllo consente di visualizzare solo le stringhe di testo. Se si desidera un controllo che visualizza i valori numerici, utilizzare il <xref:System.Windows.Forms.NumericUpDown> controllo. Per ulteriori informazioni, vedere [controllo NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica sul controllo DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 Introduce i concetti generali relativi il <xref:System.Windows.Forms.DomainUpDown> controllo, che consente agli utenti di esplorare e selezionare da un elenco di stringhe di testo.  
  
 [Procedura: Aggiungere elementi ai controlli DomainUpDown di Windows Form a livello di codice](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Viene descritto come specificare le stringhe di testo il <xref:System.Windows.Forms.DomainUpDown> controllo devono essere visualizzati.  
  
 [Procedura: Rimuovere elementi dai controlli DomainUpDown di Windows Form](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Viene descritto come eliminare gli elementi di <xref:System.Windows.Forms.DomainUpDown> nel codice.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DomainUpDown>  
 Descrive la classe e fornisce i collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Descrive la classe e include collegamenti a tutti i relativi membri...  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Controlli utilizzabili in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.
