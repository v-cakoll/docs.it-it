---
title: Cenni preliminari sul controllo DomainUpDown (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: bfe3e7239f77c6f1a0d9bb46a96c704653b43364
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972068"
---
# <a name="domainupdown-control-overview-windows-forms"></a>Cenni preliminari sul controllo DomainUpDown (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.DomainUpDown> controllo è essenzialmente una combinazione di una casella di testo e una coppia di pulsanti di spostamento verso l'alto o verso il basso in un elenco. Il controllo Visualizza e imposta una stringa di testo da un elenco di scelte. L'utente può selezionare la stringa, fare clic su pulsanti per spostarsi all'interno di un elenco su e giù, premendo i tasti di direzione su e giù o digitando una stringa che corrisponde a un elemento nell'elenco. Un possibile utilizzo di questo controllo è per la selezione di elementi da un elenco alfabetico dei nomi.  
  
> [!NOTE]
>  Per ordinare l'elenco, impostare il <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> proprietà `true`.  
  
 La funzione di questo controllo è molto simile alla casella di riepilogo o casella combinata, ma ha pochissimo spazio dopo circa.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le proprietà principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, e <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Il <xref:System.Windows.Forms.DomainUpDown.Items%2A> proprietà contiene l'elenco di oggetti i cui valori di testo vengono visualizzati nel controllo. Se <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> è impostata su `false`, il controllo viene completata automaticamente il testo che l'utente digita e fa corrisponda a un valore nell'elenco. Se <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> è impostata su `true`, lo scorrimento oltre l'ultimo elemento verrà visualizzata al primo elemento nell'elenco e viceversa. I metodi principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> e <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Questo controllo consente di visualizzare solo le stringhe di testo. Se si vuole un controllo che visualizza i valori numerici, usare il <xref:System.Windows.Forms.NumericUpDown> controllo. Per altre informazioni, vedere [Cenni preliminari sul controllo NumericUpDown](numericupdown-control-overview-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DomainUpDown>
- [Controllo DomainUpDown](domainupdown-control-windows-forms.md)
