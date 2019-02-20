---
title: Eventi nei controlli di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 56de08f039fd4dee9dcc5a1b3f86cc0e8e577b43
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "56442438"
---
# <a name="events-in-windows-forms-controls"></a>Eventi nei controlli di Windows Form
Un controllo Windows Form eredita più di sessanta eventi da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Sono inclusi i <xref:System.Windows.Forms.Control.Paint> evento, che fa sì che un controllo da disegnare, gli eventi correlati alla visualizzazione di finestre, ad esempio il <xref:System.Windows.Forms.Control.Resize> e <xref:System.Windows.Forms.Control.Layout> eventi ed eventi di mouse e tastiera a basso livello. Alcuni eventi di basso livello sono sintetizzati da <xref:System.Windows.Forms.Control> in eventi semantici, ad esempio <xref:System.Windows.Forms.Control.Click> e <xref:System.Windows.Forms.Control.DoubleClick>. Per informazioni dettagliate sugli eventi ereditati, vedere <xref:System.Windows.Forms.Control>.  
  
 Se è necessario eseguire l'override del controllo personalizzato sulle funzionalità di eventi ereditati, eseguire l'override del metodo `On`*EventName* ereditato anziché associare un delegato. Se non si ha familiarità con il modello di eventi in .NET Framework, vedere [Generazione di eventi da un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
## <a name="see-also"></a>Vedere anche
- [Override del metodo OnPaint](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)
- [Gestione dell'input dell'utente](../../../../docs/framework/winforms/controls/handling-user-input.md)
- [Definizione di un evento](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
- [Eventi](../../../../docs/standard/events/index.md)
