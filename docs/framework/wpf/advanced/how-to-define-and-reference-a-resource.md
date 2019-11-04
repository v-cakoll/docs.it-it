---
title: 'Procedura: definire e fare riferimento a una risorsa'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 89471c45aabd9f3415c45a2e8af41d1a52900324
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460170"
---
# <a name="how-to-define-and-reference-a-resource"></a>Procedura: definire e fare riferimento a una risorsa

Questo esempio illustra come definire una risorsa e farvi riferimento usando un attributo in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].

## <a name="example"></a>Esempio

Nell'esempio seguente vengono definiti due tipi di risorse: una risorsa <xref:System.Windows.Media.SolidColorBrush> e diverse risorse <xref:System.Windows.Style>. La risorsa <xref:System.Windows.Media.SolidColorBrush> `MyBrush` viene utilizzata per fornire il valore di diverse proprietà che accettano un valore di tipo <xref:System.Windows.Media.Brush>. Le risorse <xref:System.Windows.Style> `PageBackground`, `TitleText` e `Label` ciascuna destinazione di un particolare tipo di controllo. Gli stili consentono di impostare una varietà di proprietà diverse sui controlli di destinazione, quando tale risorsa viene utilizzata come riferimento dalla chiave di risorsa e viene utilizzata per impostare la proprietà <xref:System.Windows.FrameworkElement.Style%2A> di diversi elementi di controllo specifici definiti in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

Si noti che una delle proprietà all'interno dei setter dello stile `Label` fa riferimento anche alla risorsa `MyBrush` definita in precedenza. Si tratta di una tecnica comune, ma è importante ricordare che le risorse vengono analizzate e immesse in un dizionario risorse nell'ordine in cui vengono fornite. Le risorse vengono inoltre richieste dall'ordine trovato all'interno del dizionario se si usa l' [estensione di markup StaticResource](staticresource-markup-extension.md) per farvi riferimento da un'altra risorsa. Assicurarsi che tutte le risorse a cui si fa riferimento siano definite in precedenza all'interno della raccolta di risorse rispetto a quella in cui viene richiesta la risorsa. Se necessario, è possibile aggirare l'ordine di creazione rigoroso dei riferimenti alle risorse utilizzando un' [estensione di markup DynamicResource](dynamicresource-markup-extension.md) per fare riferimento alla risorsa in fase di esecuzione, ma è necessario tenere presente che questa tecnica DynamicResource presenta prestazioni conseguenze. Per informazioni dettagliate, vedere [risorse XAML](xaml-resources.md).

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>Vedere anche

- [Risorse XAML](xaml-resources.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
