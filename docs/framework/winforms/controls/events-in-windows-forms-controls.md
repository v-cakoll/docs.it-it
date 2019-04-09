---
title: Eventi nei controlli di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 41ad95de7a65dbd0cb3a0d1af8f5c8cb00c1ccdd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215891"
---
# <a name="events-in-windows-forms-controls"></a>Eventi nei controlli di Windows Form
Un controllo Windows Form eredita più di sessanta eventi da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Sono inclusi i <xref:System.Windows.Forms.Control.Paint> evento, che fa sì che un controllo da disegnare, gli eventi correlati alla visualizzazione di finestre, ad esempio il <xref:System.Windows.Forms.Control.Resize> e <xref:System.Windows.Forms.Control.Layout> eventi ed eventi di mouse e tastiera a basso livello. Alcuni eventi di basso livello sono sintetizzati da <xref:System.Windows.Forms.Control> in eventi semantici, ad esempio <xref:System.Windows.Forms.Control.Click> e <xref:System.Windows.Forms.Control.DoubleClick>. Per informazioni dettagliate sugli eventi ereditati, vedere <xref:System.Windows.Forms.Control>.  
  
 Se è necessario eseguire l'override del controllo personalizzato sulle funzionalità di eventi ereditati, eseguire l'override del metodo `On`*EventName* ereditato anziché associare un delegato. Se non si ha familiarità con il modello di eventi in .NET Framework, vedere [Generazione di eventi da un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
## <a name="see-also"></a>Vedere anche

- [Override del metodo OnPaint](overriding-the-onpaint-method.md)
- [Gestione dell'input dell'utente](handling-user-input.md)
- [Definizione di un evento](defining-an-event-in-windows-forms-controls.md)
- [Eventi](../../../standard/events/index.md)
