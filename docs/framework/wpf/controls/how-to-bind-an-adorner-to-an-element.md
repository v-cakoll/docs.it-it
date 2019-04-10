---
title: 'Procedura: Associare uno strumento decorativo a un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: b6909fec466c2b31a7f4156c43b21a0c724f0217
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307288"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>Procedura: Associare uno strumento decorativo a un elemento
Questo esempio illustra come associare programmaticamente uno strumento decorativo a un oggetto specificato <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Esempio  
 Per associare uno strumento decorativo a un determinato <xref:System.Windows.UIElement>, seguire questa procedura:  
  
1. Chiamare il `static` metodo <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per ottenere un <xref:System.Windows.Documents.AdornerLayer> dell'oggetto per il <xref:System.Windows.UIElement> da decorare. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> risale la struttura ad albero visuale, iniziando in corrispondenza di oggetto specificato **UIElement**e restituisce il primo livello dello strumento decorativo trovato. (se non viene trovato alcun livello dello strumento decorativo, il metodo restituisce null).  
  
2. Chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo a cui associare lo strumento decorativo visuale di destinazione **UIElement**.  
  
 Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) a un <xref:System.Windows.Controls.TextBox> denominate *myTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli strumenti decorativi visuali](adorners-overview.md)
