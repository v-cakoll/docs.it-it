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
ms.openlocfilehash: 83d674e3fb7ff7e715b75c635b891cd4e9703a21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972055"
---
# <a name="domainupdown-control-windows-forms"></a>Controllo DomainUpDown (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.DomainUpDown> controllo Cerca, ad esempio una combinazione di una casella di testo e una coppia di pulsanti di spostamento verso l'alto o verso il basso in un elenco. Il controllo Visualizza e imposta una stringa di testo da un elenco di scelte. L'utente può selezionare la stringa, fare clic su pulsanti per spostarsi all'interno di un elenco su e giù, premendo i tasti di direzione su e giù o digitando una stringa che corrisponde a un elemento nell'elenco. Un possibile utilizzo di questo controllo è per la selezione di elementi da un elenco alfabetico dei nomi. (Per ordinare l'elenco, impostare il <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> proprietà `true`.) La funzione di questo controllo è molto simile alla casella di riepilogo o casella combinata, ma ha pochissimo spazio dopo circa.  
  
 Le proprietà principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, e <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Il <xref:System.Windows.Forms.DomainUpDown.Items%2A> proprietà contiene l'elenco di oggetti i cui valori di testo vengono visualizzati nel controllo. Se <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> è impostata su `false`, il controllo viene completata automaticamente il testo che l'utente digita e fa corrisponda a un valore nell'elenco. Se <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> è impostata su `true`, lo scorrimento oltre l'ultimo elemento verrà visualizzata al primo elemento nell'elenco e viceversa. I metodi principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> e <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Questo controllo consente di visualizzare solo le stringhe di testo. Se si vuole un controllo che visualizza i valori numerici, usare il <xref:System.Windows.Forms.NumericUpDown> controllo. Per altre informazioni, vedere [controllo NumericUpDown](numericupdown-control-windows-forms.md) .  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica sul controllo DomainUpDown](domainupdown-control-overview-windows-forms.md)  
 Introduce i concetti generali del <xref:System.Windows.Forms.DomainUpDown> controllo, che consente agli utenti di esplorare e selezionare da un elenco di stringhe di testo.  
  
 [Procedura: Aggiungere elementi ai controlli DomainUpDown di Windows Form a livello di codice](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Viene descritto come specificare le stringhe di testo di <xref:System.Windows.Forms.DomainUpDown> controllo devono essere visualizzati.  
  
 [Procedura: Rimuovere elementi dai controlli DomainUpDown di Windows Form](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Viene descritto come eliminare elementi dal <xref:System.Windows.Forms.DomainUpDown> nel codice.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DomainUpDown>  
 Descrive la classe e fornisce i collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Descrive la classe e include collegamenti a tutti i relativi membri...  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Controlli utilizzabili in Windows Form](controls-to-use-on-windows-forms.md)  
 Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.
