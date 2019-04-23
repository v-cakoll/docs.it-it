---
title: 'Procedura: Modificare il colore di un elemento usando eventi focus'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 744963cc543110121a777e1d4c3cdcb3cec40d9e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217640"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Procedura: Modificare il colore di un elemento usando eventi focus
In questo esempio viene illustrato come modificare il colore di un elemento quando si riceve e perde lo stato attivo tramite il <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> eventi.  
  
 In questo esempio è costituito un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file e un file code-behind.  
  
## <a name="example"></a>Esempio  
 Quanto segue [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea l'interfaccia utente, che è costituito da due <xref:System.Windows.Controls.Button> gli oggetti e i gestori eventi per il <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> eventi per il <xref:System.Windows.Controls.Button> oggetti.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Il codice seguente crea il <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> gestori eventi.  Quando la <xref:System.Windows.Controls.Button> riceve lo stato attivo, il <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene modificato e impostato su rosso.  Quando la <xref:System.Windows.Controls.Button> perde lo stato attivo della tastiera, il <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene nuovamente impostato su bianco.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'input](input-overview.md)
