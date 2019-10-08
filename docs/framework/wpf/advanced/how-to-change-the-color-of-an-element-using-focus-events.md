---
title: 'Procedura: Modificare il colore di un elemento utilizzando eventi di stato attivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 5c59dc5f2f8f26fac69933f9ef641a3a51306619
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004830"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Procedura: Modificare il colore di un elemento utilizzando eventi di stato attivo
In questo esempio viene illustrato come modificare il colore di un elemento quando si ottiene e perde lo stato attivo usando gli eventi <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus>.  
  
 Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.  
  
## <a name="example"></a>Esempio  
 Il codice XAML seguente crea l'interfaccia utente, che è costituita da due oggetti <xref:System.Windows.Controls.Button> e connette i gestori eventi per gli eventi <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> agli oggetti <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Il codice sottostante seguente consente di creare i gestori eventi <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus>.  Quando il <xref:System.Windows.Controls.Button> Ottiene lo stato attivo della tastiera, il <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene modificato in rosso.  Quando il <xref:System.Windows.Controls.Button> perde lo stato attivo della tastiera, il <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene modificato di nuovo in bianco.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'input](input-overview.md)
