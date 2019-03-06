---
title: "Procedura: Modificare l'oggetto FlowDirection del contenuto a livello di codice"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359328"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a>Procedura: Modificare l'oggetto FlowDirection del contenuto a livello di codice
In questo esempio viene illustrato come modificare a livello di codice le <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà di un <xref:System.Windows.Controls.FlowDocumentReader>.  
  
## <a name="example"></a>Esempio  
 Due <xref:System.Windows.Controls.Button> vengono creati gli elementi, ognuno dei quali rappresenta uno dei valori possibili di <xref:System.Windows.FlowDirection>. Quando viene selezionato un pulsante, il valore della proprietà associata viene applicato al contenuto di un <xref:System.Windows.Controls.FlowDocumentReader> denominato `tf1`.  Il valore della proprietà viene scritto anche a un <xref:System.Windows.Controls.TextBlock> denominato `txt1`.  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a>Esempio  
 Gli eventi associati ai clic sui pulsanti definiti in precedenza vengono gestiti in un C# file code-behind.  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
