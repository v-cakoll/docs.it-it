---
title: "Procedura: Eseguire l'override del metodo Panel OnRender"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: 23c3353e130585ed83726816a467ca73f6aa9152
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666712"
---
# <a name="how-to-override-the-panel-onrender-method"></a>Procedura: Eseguire l'override del metodo Panel OnRender
In questo esempio viene illustrato come eseguire <xref:System.Windows.Controls.Panel.OnRender%2A> l'override <xref:System.Windows.Controls.Panel> del metodo di per aggiungere effetti grafici personalizzati a un elemento di layout.  
  
## <a name="example"></a>Esempio  
 Usare il <xref:System.Windows.Controls.Panel.OnRender%2A> metodo per aggiungere effetti grafici a un elemento Panel sottoposto a rendering. Ad esempio, è possibile usare questo metodo per aggiungere effetti bordo o sfondo personalizzati. Un <xref:System.Windows.Media.DrawingContext> oggetto viene passato come argomento, che fornisce metodi per disegnare forme, testo, immagini o video. Di conseguenza, questo metodo è utile per la personalizzazione di un oggetto Panel.  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Panel>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Procedure relative alle proprietà](panel-how-to-topics.md)
