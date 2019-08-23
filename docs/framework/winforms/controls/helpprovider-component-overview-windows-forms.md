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
ms.openlocfilehash: cefc590bb3011b282392504a78ac5c393c58493e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965688"
---
# <a name="helpprovider-component-overview-windows-forms"></a>Cenni preliminari sul componente HelpProvider (Windows Form)
Il componente Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) viene utilizzato per associare un file della Guida HTML della guida 1. x (un file con estensione chm, prodotto con l'Help Workshop HTML o un file con estensione htm) all'applicazione Windows. È possibile fornire supporto in diversi modi:  
  
- Fornire la Guida sensibile al contesto per i controlli Windows Forms.  
  
- Fornire la Guida sensibile al contesto per una particolare finestra di dialogo o controlli specifici in una finestra di dialogo.  
  
- Aprire un file della Guida in aree specifiche, ad esempio la pagina principale di un sommario, l'indice o una funzione di ricerca.  
  
## <a name="using-the-help-provider"></a>Uso del provider della Guida  
 L'aggiunta <xref:System.Windows.Forms.HelpProvider> di un componente al Windows Form consente agli altri controlli nel form di esporre le proprietà <xref:System.Windows.Forms.HelpProvider> della guida del componente. In questo modo è possibile fornire la guida per i controlli in Windows Form. È possibile associare un file <xref:System.Windows.Forms.HelpProvider> della Guida al componente utilizzando la <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> proprietà. È possibile specificare il tipo di Guida fornito chiamando <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> e fornendo un valore <xref:System.Windows.Forms.HelpNavigator> dall'enumerazione per il controllo specificato. È possibile specificare la parola chiave o l'argomento per la <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> Guida chiamando il metodo.  
  
 Facoltativamente, per associare una stringa della Guida specifica a un altro controllo, <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> utilizzare il metodo. La stringa associata a un controllo utilizzando questo metodo viene visualizzata in una finestra popup quando l'utente preme il tasto F1 mentre il controllo ha lo stato attivo.  
  
 Se <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> non è stato impostato, è necessario usare <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> per fornire il testo della guida. Se sono stati impostati sia <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> che la stringa della guida, la Guida <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> basata su avrà la precedenza.  
  
> [!NOTE]
> È possibile che si verifichino problemi usando il percorso relativo quando si specifica il percorso del file <xref:System.Windows.Forms.Help.ShowHelp%2A> della Guida <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> nel metodo o <xref:System.Windows.Forms.HelpProvider> nella proprietà del controllo. Assicurarsi quindi di usare il percorso file assoluto per specificare il file della guida.  
  
## <a name="see-also"></a>Vedere anche

- [Sistemi di Guida nelle Windows Forms Application](../advanced/help-systems-in-windows-forms-applications.md)
