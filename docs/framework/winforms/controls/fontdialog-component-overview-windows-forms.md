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
ms.openlocfilehash: 26bfb561c1050438b78c4ae0a3e6e8da32458cdd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725038"
---
# <a name="fontdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente FontDialog (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.FontDialog> componente è una finestra di dialogo preconfigurata, ovvero il Windows standard **Font** finestra di dialogo utilizzata per esporre i tipi di carattere attualmente installati nel sistema. Usarlo all'interno dell'applicazione basata su Windows come una soluzione semplice per la selezione del tipo di carattere anziché configurare una propria finestra di dialogo.  
  
 Per impostazione predefinita, la finestra di dialogo Mostra le caselle di riepilogo per tipo di carattere, stile e dimensioni. ad esempio caselle di controllo per gli effetti barrato e sottolineato; un elenco di riepilogo a discesa per Script. e un esempio del modo in cui verrà visualizzato il tipo di carattere. (Lo script fa riferimento agli script di caratteri diversi che sono disponibili per un determinato tipo di carattere, ad esempio, giapponese o ebraica.) Per visualizzare la finestra di dialogo tipo di carattere, chiamare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo).  
  
## <a name="key-properties"></a>Proprietà chiave  
 Il componente ha numerose proprietà che consentono di configurare l'aspetto del controllo. Le proprietà impostare le selezioni di finestra di dialogo sono <xref:System.Windows.Forms.FontDialog.Font%2A> e <xref:System.Windows.Forms.FontDialog.Color%2A>. Il <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà imposta il tipo di carattere, stile, dimensione, script ed effetti; ad esempio, `Arial, 10pt, style=Italic, Strikeout`.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.FontDialog>
- [Componente FontDialog](fontdialog-component-windows-forms.md)
