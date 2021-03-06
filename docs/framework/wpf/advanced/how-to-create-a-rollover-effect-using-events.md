---
title: 'Procedura: creare un effetto di attivazione utilizzando gli eventi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: ccdc8aeb26b538814b2f9020e1e3a5b311fa5a99
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460167"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Procedura: creare un effetto di attivazione utilizzando gli eventi
Questo esempio Mostra come modificare il colore di un elemento quando il puntatore del mouse entra e lascia l'area occupata dall'elemento.  
  
 Questo esempio è costituito da un file di [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.  
  
> [!NOTE]
> In questo esempio viene illustrato come utilizzare gli eventi, ma il metodo consigliato per ottenere questo risultato consiste nell'utilizzare un <xref:System.Windows.Trigger> in uno stile. Per altre informazioni, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
## <a name="example"></a>Esempio  
 Il codice XAML seguente crea l'interfaccia utente, che è costituita da <xref:System.Windows.Controls.Border> intorno a una <xref:System.Windows.Controls.TextBlock>e connette i gestori eventi di <xref:System.Windows.Input.Mouse.MouseEnter> e <xref:System.Windows.UIElement.MouseLeave> al <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Il codice sottostante seguente crea i gestori eventi <xref:System.Windows.UIElement.MouseEnter> e <xref:System.Windows.UIElement.MouseLeave>.  Quando il puntatore del mouse entra nel <xref:System.Windows.Controls.Border>, lo sfondo del <xref:System.Windows.Controls.Border> viene modificato in rosso.  Quando il puntatore del mouse esce dalla <xref:System.Windows.Controls.Border>, lo sfondo del <xref:System.Windows.Controls.Border> viene modificato di nuovo in bianco.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
