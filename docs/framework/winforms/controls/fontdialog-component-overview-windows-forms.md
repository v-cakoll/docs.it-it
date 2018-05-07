---
title: Cenni preliminari sul componente FontDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 3a4707ffe471161988d0526ce0908b37299f3e07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="fontdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente FontDialog (Windows Form)
Windows Form <xref:System.Windows.Forms.FontDialog> componente è una finestra di dialogo preconfigurata che è lo standard di Windows **carattere** la finestra di dialogo utilizzata per esporre i tipi di carattere attualmente installati nel sistema. Utilizzarlo all'interno dell'applicazione basate su Windows come semplice soluzione per la selezione del carattere anziché configurare la propria finestra di dialogo.  
  
 Per impostazione predefinita, la finestra di dialogo Mostra le caselle di riepilogo per tipo di carattere, stile e dimensioni. ad esempio caselle di controllo per gli effetti barrato e sottolineato; un elenco di riepilogo a discesa per Script. e un esempio del modo in cui verrà visualizzato il tipo di carattere. (Script fa riferimento agli script di caratteri diversi che sono disponibili per un determinato tipo di carattere, ad esempio, ebraico o giapponese.) Per visualizzare la finestra di dialogo tipo di carattere, chiamare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Il componente dispone di un numero di proprietà che consentono di configurare l'aspetto. Le proprietà impostare le selezioni la finestra di dialogo sono <xref:System.Windows.Forms.FontDialog.Font%2A> e <xref:System.Windows.Forms.FontDialog.Color%2A>. Il <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà imposta il tipo di carattere, stile, dimensione, script ed effetti; ad esempio, `Arial, 10pt, style=Italic, Strikeout`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.FontDialog>  
 [Componente FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
