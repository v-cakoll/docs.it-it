---
title: 'Procedura: scegliere tra StackPanel e DockPanel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
ms.openlocfilehash: c9bfb8d29051a9cfa61d3fcb93b8bb9a68d14e00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a>Procedura: scegliere tra StackPanel e DockPanel
In questo esempio viene illustrato come scegliere tra l'utilizzo di un <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel> per lo stack di contenuto in un <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Esempio  
 Anche se è possibile utilizzare <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.StackPanel> per stack di elementi figlio, i due controlli non producono sempre gli stessi risultati. Ad esempio, l'ordine che si posizionano gli elementi figlio può influenzare le dimensioni degli elementi figlio in un <xref:System.Windows.Controls.DockPanel> ma non in un <xref:System.Windows.Controls.StackPanel>. Si verifica un comportamento diverso perché <xref:System.Windows.Controls.StackPanel> misura la direzione dello stack in corrispondenza <xref:System.Double>.<xref:System.Double.PositiveInfinity>; tuttavia, <xref:System.Windows.Controls.DockPanel> misura solo le dimensioni disponibili.  
  
 Nell'esempio seguente viene illustrata questa differenza fondamentale tra <xref:System.Windows.Controls.DockPanel> e <xref:System.Windows.Controls.StackPanel>.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.DockPanel>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
