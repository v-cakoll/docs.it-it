---
title: Modificare il ritardo del componente della descrizione comando
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746583"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>Procedura: Modifica del ritardo del componente ToolTip di Windows Form
Sono disponibili più valori di ritardo che è possibile impostare per un componente Windows Forms <xref:System.Windows.Forms.ToolTip>. L'unità di misura per tutte queste proprietà è in millisecondi. La proprietà <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> determina per quanto tempo l'utente deve puntare al controllo associato affinché venga visualizzata la stringa della descrizione comando. La proprietà <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> imposta il numero di millisecondi necessari per la visualizzazione delle stringhe di descrizione comando successive quando il mouse passa da un controllo associato alla descrizione comando a un altro. La proprietà <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> determina il periodo di tempo in cui viene visualizzata la stringa della descrizione comando. È possibile impostare questi valori singolarmente oppure impostando il valore della proprietà <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>; le altre proprietà delay vengono impostate in base al valore assegnato alla proprietà <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>. Se, ad esempio, <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> è impostato su un valore N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> è impostato su N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> viene impostato sul valore di <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> diviso per cinque (o N/5) e <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> viene impostato su un valore cinque volte superiore al valore della proprietà <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> (o 5N).  
  
### <a name="to-set-the-delay"></a>Per impostare il ritardo  
  
1. Impostare le proprietà seguenti, come illustrato in questo esempio.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul componente ToolTip](tooltip-component-overview-windows-forms.md)
- [Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [Componente ToolTip](tooltip-component-windows-forms.md)
