---
title: Cenni preliminari sul componente HelpProvider (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 9d6360358b08dc0602cbdfe352bb69caee25c7bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591978"
---
# <a name="helpprovider-component-overview-windows-forms"></a>Cenni preliminari sul componente HelpProvider (Windows Form)
I moduli di Windows [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) componente viene usato per associare un file di Guida HTML Help 1.x (un file. chm creato con HTML Help Workshop o un file con estensione htm) all'applicazione Windows. È possibile visualizzare la Guida in diversi modi:  
  
-   Fornire la Guida sensibile al contesto per i controlli in Windows Form.  
  
-   Fornire una Guida sensibile al contesto in una finestra di dialogo particolare o controlli specifici in una finestra di dialogo.  
  
-   Aprire un file della Guida per aree specifiche, ad esempio la pagina principale di un sommario, indice o una funzione di ricerca.  
  
## <a name="using-the-help-provider"></a>Utilizzo del Provider della Guida  
 Aggiunta di un <xref:System.Windows.Forms.HelpProvider> componente al Form Windows consente agli altri controlli nel form per esporre le proprietà della Guida di <xref:System.Windows.Forms.HelpProvider> componente. In questo modo è possibile fornire la Guida per i controlli sul Form Windows. È possibile associare un file della Guida in linea con il <xref:System.Windows.Forms.HelpProvider> componente usando il <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> proprietà. Si specifica il tipo di Guida in linea forniti tramite una chiamata <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> e fornendo un valore compreso il <xref:System.Windows.Forms.HelpNavigator> enumerazione per il controllo specificato. È possibile specificare la parola chiave o un argomento per la Guida chiamando la <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> (metodo).  
  
 Facoltativamente, per associare una stringa della Guida specifica a un altro controllo, usare il <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> (metodo). La stringa che viene associato a un controllo con questo metodo viene visualizzata in una finestra popup quando l'utente preme il tasto F1 mentre il controllo ha lo stato attivo.  
  
 Se <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> non è stata impostata, è necessario usare <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> per fornire il testo della Guida. Se sono stati impostati entrambi <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> e la stringa della Guida, la Guida è basata sulla <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> avrà la precedenza.  
  
> [!NOTE]
>  Si possono verificare problemi con il percorso relativo quando si specifica il percorso del file della Guida nel <xref:System.Windows.Forms.Help.ShowHelp%2A> metodo o <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> proprietà del <xref:System.Windows.Forms.HelpProvider> controllo. Di conseguenza, assicurarsi di usare il percorso file assoluto per specificare il file della Guida.  
  
## <a name="see-also"></a>Vedere anche
- [Sistemi di Guida nelle Windows Forms Application](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
