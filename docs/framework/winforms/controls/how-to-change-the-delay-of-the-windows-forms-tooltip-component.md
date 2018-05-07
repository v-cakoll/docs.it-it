---
title: 'Procedura: modificare il ritardo del componente ToolTip di Windows Form'
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
ms.openlocfilehash: 20dcd941b142daa672312edb618a1c3e4597442d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>Procedura: modificare il ritardo del componente ToolTip di Windows Form
Sono presenti più valori di ritardo che è possibile impostare per un Windows Form <xref:System.Windows.Forms.ToolTip> componente. L'unità di misura per tutte queste proprietà è millisecondi. Il <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> proprietà determina quanto tempo l'utente deve sempre puntare superiore del controllo associato per la stringa di descrizione comando da visualizzare. Il <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> proprietà imposta il numero di millisecondi necessario per le stringhe di descrizione comando successive mentre il mouse viene spostato da un controllo descrizione comandi associato a un altro. Il <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> proprietà determina la lunghezza della stringa di descrizione comandi. È possibile impostare questi valori, singolarmente o impostando il valore del <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> a; il ritardo di proprietà vengono impostate in base al valore assegnato alla proprietà di <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> proprietà. Ad esempio, quando <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> è impostata su un valore N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> è impostata su, N <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> è impostata sul valore di <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> diviso per cinque (o N/5) e <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> è impostata su un valore che rappresenta il valore di cinque volte il <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> proprietà (o 5N).  
  
### <a name="to-set-the-delay"></a>Per impostare il ritardo  
  
1.  Come illustrato in questo esempio, impostare le proprietà seguenti.  
  
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
 [Panoramica sul componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [Componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
