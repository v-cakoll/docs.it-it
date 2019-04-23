---
title: 'Procedura: Scegliere tra StackPanel e DockPanel'
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
ms.openlocfilehash: 8338421dfb1bea856c15edf9d324cec955584f9f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206967"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a>Procedura: Scegliere tra StackPanel e DockPanel
In questo esempio viene illustrato come scegliere tra l'uso di un <xref:System.Windows.Controls.StackPanel> o un <xref:System.Windows.Controls.DockPanel> quando lo stack del contenuto in un <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Esempio  
 Anche se è possibile usare <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.StackPanel> per stack di elementi figlio, i due controlli non producono sempre gli stessi risultati. Ad esempio, l'ordine in cui si posizionano gli elementi figlio possa influire sulle dimensioni degli elementi figlio in una <xref:System.Windows.Controls.DockPanel> ma non in un <xref:System.Windows.Controls.StackPanel>. Questo comportamento diverso si verifica in quanto <xref:System.Windows.Controls.StackPanel> misure nella direzione dello stack in corrispondenza <xref:System.Double>.<xref:System.Double.PositiveInfinity>; tuttavia, <xref:System.Windows.Controls.DockPanel> misura solo le dimensioni disponibili.  
  
 Nell'esempio seguente illustra questa differenza fondamentale tra <xref:System.Windows.Controls.DockPanel> e <xref:System.Windows.Controls.StackPanel>.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
