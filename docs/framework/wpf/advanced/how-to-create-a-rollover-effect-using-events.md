---
title: 'Procedura: Creare un effetto di attivazione utilizzando gli eventi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 87740a215136863199d962a2704cf691f27fc3bc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369097"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Procedura: Creare un effetto di attivazione utilizzando gli eventi
In questo esempio viene illustrato come modificare il colore di un elemento quando il puntatore del mouse entra o esce dall'area occupata dall'elemento.  
  
 In questo esempio è costituito un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file e un file code-behind.  
  
> [!NOTE]
>  In questo esempio viene illustrato come utilizzare gli eventi, ma il modo consigliato per ottenere lo stesso effetto è usare un <xref:System.Windows.Trigger> in uno stile. Per altre informazioni, vedere [Applicazione di stili e modelli](../controls/styling-and-templating.md).  
  
## <a name="example"></a>Esempio  
 Quanto segue [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea l'interfaccia utente, che è costituito <xref:System.Windows.Controls.Border> intorno a un <xref:System.Windows.Controls.TextBlock>e associa il <xref:System.Windows.Input.Mouse.MouseEnter> e <xref:System.Windows.UIElement.MouseLeave> gestori eventi per il <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Il codice seguente crea il <xref:System.Windows.UIElement.MouseEnter> e <xref:System.Windows.UIElement.MouseLeave> gestori eventi.  Quando il puntatore del mouse entra la <xref:System.Windows.Controls.Border>, lo sfondo del <xref:System.Windows.Controls.Border> viene modificato e impostato su rosso.  Quando il puntatore del mouse lascia il <xref:System.Windows.Controls.Border>, lo sfondo del <xref:System.Windows.Controls.Border> viene nuovamente impostato su bianco.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
