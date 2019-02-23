---
title: 'Procedura: Definire un modello GroupBox'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: 6294a52d5914b52d191b564330f904e6a865c283
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745198"
---
# <a name="how-to-define-a-groupbox-template"></a>Procedura: Definire un modello GroupBox
Questo esempio viene illustrato come creare un modello per un <xref:System.Windows.Controls.GroupBox> controllo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce una <xref:System.Windows.Controls.GroupBox> modello di controllo utilizzando un <xref:System.Windows.Controls.Grid> controllo per il layout. Il modello Usa un <xref:System.Windows.Controls.BorderGapMaskConverter> per definire il bordo del <xref:System.Windows.Controls.GroupBox> in modo che non nasconda la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenuto.  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.GroupBox>
- [Procedura: Creare un controllo GroupBox](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))
