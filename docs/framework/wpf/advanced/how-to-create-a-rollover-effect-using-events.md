---
title: 'Procedura: Creare un effetto di attivazione usando gli eventi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960379"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Procedura: Creare un effetto di attivazione usando gli eventi
Questo esempio Mostra come modificare il colore di un elemento quando il puntatore del mouse entra e lascia l'area occupata dall'elemento.  
  
 Questo esempio è costituito [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] da un file e da un file code-behind.  
  
> [!NOTE]
> Questo esempio illustra come usare gli eventi, ma la modalità consigliata per ottenere questo risultato consiste nell'usare un <xref:System.Windows.Trigger> oggetto in uno stile. Per altre informazioni, vedere [Applicazione di stili e modelli](../controls/styling-and-templating.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] seguente viene creata l'interfaccia utente che <xref:System.Windows.Controls.Border> è costituita <xref:System.Windows.Controls.TextBlock>da un oggetto e i <xref:System.Windows.Input.Mouse.MouseEnter> gestori <xref:System.Windows.UIElement.MouseLeave> eventi e vengono collegati a <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Il codice sottostante seguente consente di <xref:System.Windows.UIElement.MouseEnter> creare <xref:System.Windows.UIElement.MouseLeave> i gestori eventi e.  Quando il puntatore del mouse entra <xref:System.Windows.Controls.Border>in, lo sfondo <xref:System.Windows.Controls.Border> di viene modificato in rosso.  Quando il puntatore del mouse esce <xref:System.Windows.Controls.Border>dall'oggetto, lo sfondo <xref:System.Windows.Controls.Border> di viene modificato di nuovo in bianco.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
