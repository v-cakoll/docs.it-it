---
title: 'Procedura: Definire e fare riferimento a una risorsa'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 80be1460906100072e6263c967c213df7968c705
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776506"
---
# <a name="how-to-define-and-reference-a-resource"></a>Procedura: Definire e fare riferimento a una risorsa

In questo esempio viene illustrato come definire una risorsa e farvi riferimento utilizzando un attributo in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].

## <a name="example"></a>Esempio

L'esempio seguente definisce due tipi di risorse: un <xref:System.Windows.Media.SolidColorBrush> risorse e diversi <xref:System.Windows.Style> le risorse. Il <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` consente di specificare il valore di varie proprietà che richiedono un <xref:System.Windows.Media.Brush> tipo valore. Il <xref:System.Windows.Style> le risorse `PageBackground`, `TitleText` e `Label` ognuna un particolare tipo di controllo di destinazione. Gli stili di impostano un'ampia gamma di proprietà sui controlli di destinazione, quando tale risorsa di stile viene fatto riferimento dalla chiave di risorsa e viene usato per impostare il <xref:System.Windows.FrameworkElement.Style%2A> proprietà di diversi elementi di controllo specifici definiti [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

Si noti che una delle proprietà all'interno dei metodi di impostazione del `Label` stile fa anche riferimento il `MyBrush` risorsa definita in precedenza. Questa è una tecnica comune, ma è importante ricordare che le risorse vengono analizzate e immessi in un dizionario risorse nell'ordine in cui sono specificati. Le risorse sono richieste anche l'ordine trovato all'interno del dizionario, se si usa la [estensione di Markup StaticResource](staticresource-markup-extension.md) fare riferimento a esse all'interno di un'altra risorsa. Assicurarsi che qualsiasi risorsa di cui si fa riferimento è definita in precedenza all'interno dell'insieme di risorse rispetto a quella in cui viene richiesta tale risorsa. Se necessario, è possibile ovviare l'ordine di creazione strict dei riferimenti alle risorse usando un [estensione di Markup DynamicResource](dynamicresource-markup-extension.md) per fare riferimento alla risorsa in fase di esecuzione, ma è necessario essere consapevoli che questo DynamicResource tecnica ha conseguenze sulle prestazioni. Per informazioni dettagliate, vedere [risorse XAML](xaml-resources.md).

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>Vedere anche

- [Risorse XAML](xaml-resources.md)
- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
