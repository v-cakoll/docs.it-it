---
title: Eventi nei controlli di Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e568dd7fadea8af399a63aa95347f368b4e13a54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="events-in-windows-forms-controls"></a>Eventi nei controlli di Windows Form
Un controllo Windows Form eredita più di 60 eventi da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Queste includono la <xref:System.Windows.Forms.Control.Paint> evento che determina un controllo da disegnare, eventi correlati alla visualizzazione di una finestra, ad esempio il <xref:System.Windows.Forms.Control.Resize> e <xref:System.Windows.Forms.Control.Layout> eventi ed eventi di mouse e tastiera basso livello. Alcuni eventi di basso livello sono sintetizzati da <xref:System.Windows.Forms.Control> nella semantici eventi, ad esempio <xref:System.Windows.Forms.Control.Click> e <xref:System.Windows.Forms.Control.DoubleClick>. Per informazioni dettagliate sugli eventi ereditati, vedere <xref:System.Windows.Forms.Control>.  
  
 Se è necessario eseguire l'override del controllo personalizzato sulle funzionalità di eventi ereditati, eseguire l'override del metodo `On`*EventName* ereditato anziché associare un delegato. Se non si ha familiarità con il modello di eventi in .NET Framework, vedere [Generazione di eventi da un componente](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).  
  
## <a name="see-also"></a>Vedere anche  
 [Override del metodo OnPaint](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [Gestione dell'input dell'utente](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [Definizione di un evento](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [Eventi](../../../../docs/standard/events/index.md)
