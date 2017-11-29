---
title: Cenni preliminari sul componente HelpProvider (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42a788e44fde80662748e19a7244ce77bb26118f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="helpprovider-component-overview-windows-forms"></a>Cenni preliminari sul componente HelpProvider (Windows Form)
Windows Form [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) componente viene utilizzato per associare un file di Guida HTML Help 1. x (un file. chm creato con HTML Help Workshop o un file con estensione htm) con l'applicazione di Windows. È possibile fornire la Guida in diversi modi:  
  
-   Fornire la Guida sensibile al contesto per i controlli in Windows Form.  
  
-   Fornire la Guida sensibile al contesto in una particolare finestra di dialogo o controlli specifici in una finestra di dialogo.  
  
-   Aprire un file della Guida per aree specifiche, ad esempio la pagina principale di un sommario, indice o una funzione di ricerca.  
  
## <a name="using-the-help-provider"></a>Utilizzo del Provider della Guida  
 Aggiunta di un <xref:System.Windows.Forms.HelpProvider> componente al Windows Form consente agli altri controlli nel form per esporre le proprietà della Guida di <xref:System.Windows.Forms.HelpProvider> componente. Ciò consente di fornire la Guida per i controlli Windows Form. È possibile associare un file della Guida con il <xref:System.Windows.Forms.HelpProvider> componente utilizzando il <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> proprietà. Specificare il tipo di Guida fornito chiamando <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> e fornendo un valore di <xref:System.Windows.Forms.HelpNavigator> enumerazione per il controllo specificato. È possibile specificare la parola chiave o un argomento per la Guida chiamando la <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> metodo.  
  
 Facoltativamente, per associare una specifica stringa della Guida con un altro controllo, utilizzare il <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> metodo. La stringa che viene associato a un controllo con questo metodo viene visualizzata in una finestra popup quando l'utente preme il tasto F1 mentre il controllo ha lo stato attivo.  
  
 Se <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> non è stata impostata, è necessario utilizzare <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> per fornire il testo della Guida. Se si è impostato sia <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> e la stringa della Guida, la Guida basata sulla <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> avrà la precedenza.  
  
> [!NOTE]
>  Si possono verificare problemi con il percorso relativo quando si specifica il percorso del file della Guida nel <xref:System.Windows.Forms.Help.ShowHelp%2A> metodo o <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> proprietà del <xref:System.Windows.Forms.HelpProvider> controllo. Di conseguenza, assicurarsi di utilizzare il percorso file assoluto per specificare il file della Guida.  
  
## <a name="see-also"></a>Vedere anche  
 [Sistemi di Guida nelle Windows Forms Application](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
