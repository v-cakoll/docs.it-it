---
title: 'Procedura: creare un elemento Panel personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 2d1581ef1d0130a6952becf36d668e6a198e1ee9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-custom-panel-element"></a>Procedura: creare un elemento Panel personalizzato
## <a name="example"></a>Esempio  
 Questo esempio viene illustrato come eseguire l'override di comportamento di layout predefinito di <xref:System.Windows.Controls.Panel> elemento e creare elementi di layout personalizzati che derivano da <xref:System.Windows.Controls.Panel>.  
  
 L'esempio definisce un oggetto personalizzato semplice <xref:System.Windows.Controls.Panel> elemento denominato `PlotPanel`, che gli elementi figlio posizionati in base alle due hardcoded coordinate x e y-. In questo esempio, `x` e `y` sono impostati entrambi su `50`; pertanto, tutti gli elementi figlio sono posizionati in tale posizione su x e y assi.  
  
 Per implementare personalizzato <xref:System.Windows.Controls.Panel> comportamenti, nell'esempio viene utilizzato il <xref:System.Windows.FrameworkElement.MeasureOverride%2A> e <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi. Ogni metodo restituisce il <xref:System.Windows.Size> dati necessari per il posizionamento e il rendering degli elementi figlio.  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Panel>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Creare un campione di pannello personalizzato di disposizione del contenuto](http://go.microsoft.com/fwlink/?LinkID=159979)
