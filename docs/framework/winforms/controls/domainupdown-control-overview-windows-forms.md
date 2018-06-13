---
title: Cenni preliminari sul controllo DomainUpDown (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 21d28caf490b008570cbd6280afff3114b0f4bfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526989"
---
# <a name="domainupdown-control-overview-windows-forms"></a>Cenni preliminari sul controllo DomainUpDown (Windows Form)
Windows Form <xref:System.Windows.Forms.DomainUpDown> del controllo è essenzialmente una combinazione di una casella di testo e una coppia di pulsanti per spostarsi verso l'alto o verso il basso all'interno di un elenco. Il controllo Visualizza e imposta una stringa di testo da un elenco di scelte. L'utente può selezionare la stringa facendo clic su e giù per spostarsi in un elenco, premendo i tasti freccia su e giù o digitando una stringa che corrisponde a un elemento nell'elenco. Un possibile utilizzo di questo controllo è per la selezione di elementi da un elenco in ordine alfabetico dei nomi.  
  
> [!NOTE]
>  Per ordinare l'elenco, impostare il <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> proprietà `true`.  
  
 La funzione di questo controllo è molto simile alla casella di riepilogo o casella combinata, ma richiede poco spazio.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le proprietà principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, e <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Il <xref:System.Windows.Forms.DomainUpDown.Items%2A> proprietà contiene l'elenco di oggetti i cui valori di testo vengono visualizzati nel controllo. Se <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> è impostato su `false`, il controllo completa automaticamente il testo che l'utente digita e a esso corrispondente a un valore nell'elenco. Se <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> è impostato su `true`, lo scorrimento oltre l'ultimo elemento verrà visualizzata al primo elemento nell'elenco e viceversa. I metodi principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> e <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Questo controllo consente di visualizzare solo le stringhe di testo. Se si desidera un controllo che visualizza i valori numerici, utilizzare il <xref:System.Windows.Forms.NumericUpDown> controllo. Per ulteriori informazioni, vedere [Cenni preliminari sul controllo NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DomainUpDown>  
 [Controllo DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
