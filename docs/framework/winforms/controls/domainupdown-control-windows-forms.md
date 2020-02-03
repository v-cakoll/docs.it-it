---
title: Controllo DomainUpDown
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745832"
---
# <a name="domainupdown-control-windows-forms"></a>Controllo DomainUpDown (Windows Form)
Il controllo Windows Forms <xref:System.Windows.Forms.DomainUpDown> ha un aspetto simile a una casella di testo e a una coppia di pulsanti per spostarsi verso l'alto o verso il basso di un elenco. Il controllo Visualizza e imposta una stringa di testo da un elenco di scelte. L'utente può selezionare la stringa facendo clic sui pulsanti su e giù per spostarsi in un elenco, premendo i tasti freccia su e giù oppure digitando una stringa corrispondente a un elemento dell'elenco. Un possibile utilizzo di questo controllo è la selezione di elementi da un elenco di nomi ordinati in ordine alfabetico. Per ordinare l'elenco, impostare la proprietà <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> su `true`. La funzione di questo controllo è molto simile alla casella di riepilogo o casella combinata, ma occupa molto spazio.  
  
 Le proprietà chiave del controllo sono <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>e <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. La proprietà <xref:System.Windows.Forms.DomainUpDown.Items%2A> contiene l'elenco di oggetti i cui valori di testo vengono visualizzati nel controllo. Se <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> è impostato su `false`, il controllo completa automaticamente il testo che l'utente digita e ne corrisponde a un valore nell'elenco. Se <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> è impostato su `true`, lo scorrimento oltre l'ultimo elemento consente di passare al primo elemento dell'elenco e viceversa. I metodi principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> e <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Questo controllo consente di visualizzare solo le stringhe di testo. Se si vuole un controllo che Visualizza i valori numerici, usare il controllo <xref:System.Windows.Forms.NumericUpDown>. Per ulteriori informazioni, vedere [controllo NumericUpDown](numericupdown-control-windows-forms.md) .  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica sul controllo DomainUpDown](domainupdown-control-overview-windows-forms.md)  
 Introduce i concetti generali del controllo <xref:System.Windows.Forms.DomainUpDown>, che consente agli utenti di esplorare e selezionare da un elenco di stringhe di testo.  
  
 [Procedura: Aggiungere elementi ai controlli DomainUpDown di Windows Form a livello di codice](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Viene descritto come specificare le stringhe di testo che devono essere visualizzate dal controllo <xref:System.Windows.Forms.DomainUpDown>.  
  
 [Procedura: Rimuovere elementi dai controlli DomainUpDown di Windows Form](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Viene descritto come eliminare elementi dal controllo <xref:System.Windows.Forms.DomainUpDown> nel codice.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Windows.Forms.DomainUpDown>  
 Descrive la classe e fornisce i collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Descrive questa classe e contiene collegamenti a tutti i relativi membri.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Controlli utilizzabili in Windows Form](controls-to-use-on-windows-forms.md)  
 Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.
