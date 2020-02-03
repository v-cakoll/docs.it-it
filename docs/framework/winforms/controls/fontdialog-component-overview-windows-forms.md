---
title: Cenni preliminari sul componente FontDialog
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745698"
---
# <a name="fontdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente FontDialog (Windows Form)
Il componente Windows Forms <xref:System.Windows.Forms.FontDialog> è una finestra di dialogo preconfigurata, ovvero la finestra di dialogo **tipo di carattere** Windows standard utilizzata per esporre i tipi di carattere attualmente installati nel sistema. Utilizzarlo all'interno dell'applicazione basata su Windows come soluzione semplice per la selezione dei tipi di carattere anziché configurare la propria finestra di dialogo.  
  
 Per impostazione predefinita, nella finestra di dialogo vengono visualizzate le caselle di riepilogo per tipo di carattere, stile del carattere e dimensioni; caselle di controllo per gli effetti quali l'attacco e la sottolineatura; elenco a discesa per lo script; e un esempio di come verrà visualizzato il tipo di carattere. (Lo script fa riferimento a script di caratteri diversi disponibili per un tipo di carattere specifico, ad esempio ebraico o giapponese). Per visualizzare la finestra di dialogo tipo di carattere, chiamare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Il componente dispone di una serie di proprietà che ne configurano l'aspetto. Le proprietà che impostano le selezioni della finestra di dialogo sono <xref:System.Windows.Forms.FontDialog.Font%2A> e <xref:System.Windows.Forms.FontDialog.Color%2A>. La proprietà <xref:System.Windows.Forms.FontDialog.Font%2A> imposta il tipo di carattere, lo stile, le dimensioni, lo script e gli effetti; ad esempio, `Arial, 10pt, style=Italic, Strikeout`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FontDialog>
- [Componente FontDialog](fontdialog-component-windows-forms.md)
