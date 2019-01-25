---
title: 'Procedura: Definire un modello GroupBox'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: 0e1b0487629bba3550a8b6b4a31c163a7ade6a87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743723"
---
# <a name="how-to-define-a-groupbox-template"></a>Procedura: Definire un modello GroupBox
Questo esempio viene illustrato come creare un modello per un <xref:System.Windows.Controls.GroupBox> controllo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce una <xref:System.Windows.Controls.GroupBox> modello di controllo utilizzando un <xref:System.Windows.Controls.Grid> controllo per il layout. Il modello Usa un <xref:System.Windows.Controls.BorderGapMaskConverter> per definire il bordo del <xref:System.Windows.Controls.GroupBox> in modo che non nasconda la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenuto.  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.GroupBox>
- [Procedure relative al controllo GroupBox](https://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
