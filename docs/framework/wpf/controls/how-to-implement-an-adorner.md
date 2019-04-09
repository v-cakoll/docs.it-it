---
title: 'Procedura: Implementare uno strumento decorativo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: da318fee42b4628351217774de2a2225cfb21ee1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120809"
---
# <a name="how-to-implement-an-adorner"></a>Procedura: Implementare uno strumento decorativo
Questo esempio illustra un'implementazione minima dello strumento decorativo visuale.  
  
## <a name="notes-for-implementers"></a>Note per gli implementatori  
 È importante notare che gli strumenti decorativi non includono alcun comportamento di rendering inerente, pertanto è responsabilità dell'implementatore garantire il rendering di uno strumento decorativo visuale.   È un modo comune per implementare il comportamento di rendering per eseguire l'override di <xref:System.Windows.UIElement.OnRender%2A> metodo e usare uno o più <xref:System.Windows.Media.DrawingContext> oggetti per il rendering di oggetti visivi dello strumento decorativo in base alle esigenze (come illustrato in questo esempio).  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Uno strumento decorativo personalizzato viene creato mediante l'implementazione di una classe che eredita dalla classe astratta <xref:System.Windows.Documents.Adorner> classe.  Lo strumento decorativo visuale dell'esempio decora semplicemente gli angoli di un <xref:System.Windows.UIElement> con cerchi eseguendo l'override di <xref:System.Windows.UIElement.OnRender%2A> (metodo).  
  
### <a name="code"></a>Codice  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli strumenti decorativi visuali](adorners-overview.md)
