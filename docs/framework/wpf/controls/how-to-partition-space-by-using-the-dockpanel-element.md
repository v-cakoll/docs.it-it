---
title: "Procedura: partizionare lo spazio utilizzando l'elemento DockPanel"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: 6b10fbcd14236f9259dc5772e7f8763c1602d0fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553884"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>Procedura: partizionare lo spazio utilizzando l'elemento DockPanel
Nell'esempio seguente viene creato un semplice [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework utilizzando un <xref:System.Windows.Controls.DockPanel> elemento. Il <xref:System.Windows.Controls.DockPanel> partiziona lo spazio disponibile per i relativi elementi figlio.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà, che è una proprietà associata, per ancorare due identici <xref:System.Windows.Controls.Border> gli elementi in corrispondenza di <xref:System.Windows.Controls.Dock.Top> dello spazio partizionato. Una terza <xref:System.Windows.Controls.Border> per l'elemento è ancorato il <xref:System.Windows.Controls.Dock.Left>, con larghezza impostata su 200 pixel. Un quarto <xref:System.Windows.Controls.Border> è ancorato il <xref:System.Windows.Controls.Dock.Bottom> dello schermo. L'ultimo <xref:System.Windows.Controls.Border> elemento riempie automaticamente lo spazio rimanente.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  Per impostazione predefinita, l'ultimo elemento figlio di un <xref:System.Windows.Controls.DockPanel> elemento riempie il rimanente spazio non allocato. Se non si desidera questo comportamento, impostare `LastChildFill="False"`.  
  
 L'applicazione compilata crea una nuova interfaccia utente analoga alla seguente.  
  
 ![Scenario DockPanel tipico.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.DockPanel>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
