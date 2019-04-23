---
title: 'Procedura: Ottenere o impostare un valore Dock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: fb6c8a7d62aa09a6e1d82cb4079d1425a7f39f8c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160739"
---
# <a name="how-to-get-or-set-a-dock-value"></a>Procedura: Ottenere o impostare un valore Dock
Nell'esempio seguente viene illustrato come assegnare un <xref:System.Windows.Controls.Dock> valore per un oggetto. L'esempio Usa la <xref:System.Windows.Controls.DockPanel.GetDock%2A> e <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodi <xref:System.Windows.Controls.DockPanel>.  
  
## <a name="example"></a>Esempio  
 L'esempio crea un'istanza del <xref:System.Windows.Controls.TextBlock> elemento `txt1`e assegna un <xref:System.Windows.Controls.Dock> pari a `Top` utilizzando il <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodo di <xref:System.Windows.Controls.DockPanel>. Aggiunge quindi il valore del <xref:System.Windows.Controls.Dock> proprietà per il <xref:System.Windows.Controls.TextBlock.Text%2A> del <xref:System.Windows.Controls.TextBlock> elemento usando la <xref:System.Windows.Controls.DockPanel.GetDock%2A> (metodo). Infine, l'esempio aggiunge il <xref:System.Windows.Controls.TextBlock> elemento padre <xref:System.Windows.Controls.DockPanel>, `dp1`.  
  
 [!code-csharp[DockPanelSetDock#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
