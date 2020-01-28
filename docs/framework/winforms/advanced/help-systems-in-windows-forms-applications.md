---
title: Sistemi della Guida
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: c97a22dbdbdcc0eb282b52e16c4ef40914b1d9e7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742238"
---
# <a name="help-systems-in-windows-forms-applications"></a>Sistemi di Guida nelle applicazioni per Windows Form
Uno degli aspetti più importanti che l'utente, come sviluppatore di applicazioni, può fornire agli utenti è un sistema di supporto competente. Questo è il punto in cui si trasformeranno quando diventeranno confuse o disorientate. La fornitura di un sistema di guida in un'applicazione basata su Windows viene eseguita facilmente tramite il [componente HelpProvider](../controls/helpprovider-component-windows-forms.md).  
  
## <a name="different-types-of-help"></a>Tipi diversi di guida  
 Il componente <xref:System.Windows.Forms.HelpProvider> di Windows Form viene usato per associare un file della Guida HTML Help 1.x, vale a dire un file .chm creato con HTML Help Workshop o un file .htm, alla propria applicazione basata su Windows. Il componente <xref:System.Windows.Forms.HelpProvider> può essere utilizzato per fornire la Guida sensibile al contesto per i controlli su Windows Forms o controlli specifici. Inoltre, il componente <xref:System.Windows.Forms.HelpProvider> può aprire un file della Guida in aree specifiche, ad esempio la pagina principale di un sommario, un indice o una funzione di ricerca. Per informazioni generali sul componente <xref:System.Windows.Forms.HelpProvider>, vedere [Cenni preliminari sul componente HelpProvider](../controls/helpprovider-component-overview-windows-forms.md). Per informazioni su come usare il componente <xref:System.Windows.Forms.HelpProvider> per visualizzare la Guida popup Windows Forms, vedere [procedura: visualizzare la Guida popup](how-to-display-pop-up-help.md). Per informazioni sull'utilizzo del componente <xref:System.Windows.Forms.ToolTip> per visualizzare la guida specifica del controllo, vedere la guida relativa ai [controlli mediante le descrizioni comandi](control-help-using-tooltips.md).  
  
 È possibile generare file HTML della guida 1. x con il workshop della Guida HTML. Per ulteriori informazioni sulla Guida HTML, vedere l'argomento "HTML Help Workshop" o l'altro argomento "HTML Help" in MSDN.  
  
## <a name="see-also"></a>Vedere anche

- [Integrazione della Guida dell'utente in Windows Form](integrating-user-help-in-windows-forms.md)
- [Componente HelpProvider](../controls/helpprovider-component-windows-forms.md)
- [Componente ToolTip](../controls/tooltip-component-windows-forms.md)
- [Panoramica sui Windows Form](../windows-forms-overview.md)
- [Windows Form](../index.md)
