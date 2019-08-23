---
title: "Procedura: Partizionare lo spazio usando l'elemento DockPanel"
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
ms.openlocfilehash: d22a808ce3ab95e3b351408bf4cc372a335da553
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960193"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>Procedura: Partizionare lo spazio usando l'elemento DockPanel
Nell'esempio seguente viene creato un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Framework semplice utilizzando <xref:System.Windows.Controls.DockPanel> un elemento. Spazio <xref:System.Windows.Controls.DockPanel> disponibile nelle partizioni per i relativi elementi figlio.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene <xref:System.Windows.Controls.DockPanel.Dock%2A> utilizzata la proprietà, che è una proprietà associata, per ancorare due elementi <xref:System.Windows.Controls.Dock.Top> identici <xref:System.Windows.Controls.Border> all'oggetto dello spazio partizionato. Un terzo <xref:System.Windows.Controls.Border> elemento è ancorato <xref:System.Windows.Controls.Dock.Left>a, con larghezza impostata su 200 pixel. Un quarto <xref:System.Windows.Controls.Border> è ancorato all'oggetto <xref:System.Windows.Controls.Dock.Bottom> dello schermo. L'ultimo <xref:System.Windows.Controls.Border> elemento riempie automaticamente lo spazio rimanente.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> Per impostazione predefinita, l'ultimo elemento figlio <xref:System.Windows.Controls.DockPanel> di un elemento riempie lo spazio rimanente non allocato. Se non si desidera questo comportamento, impostare `LastChildFill="False"`.  
  
 L'applicazione compilata crea una nuova interfaccia utente analoga alla seguente.  
  
 ![Scenario DockPanel tipico.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DockPanel>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
