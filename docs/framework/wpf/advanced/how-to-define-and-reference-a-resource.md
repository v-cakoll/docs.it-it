---
title: 'Procedura: definire e fare riferimento a una risorsa'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: e33c86b03d8b18113f3a15b3ab251753958ff5b2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646515"
---
# <a name="how-to-define-and-reference-a-resource"></a>Procedura: definire e fare riferimento a una risorsa

In questo esempio viene illustrato come definire una [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]risorsa e farvi riferimento utilizzando un attributo in .

## <a name="example"></a>Esempio

Nell'esempio seguente vengono definiti due <xref:System.Windows.Media.SolidColorBrush> tipi di <xref:System.Windows.Style> risorse: una risorsa e diverse risorse. La <xref:System.Windows.Media.SolidColorBrush> `MyBrush` risorsa viene utilizzata per fornire il valore <xref:System.Windows.Media.Brush> di diverse proprietà che accettano ciascuna un valore di tipo. Le <xref:System.Windows.Style> `PageBackground`risorse `TitleText` `Label` e ognuna di destinazione di un determinato tipo di controllo. Gli stili impostano una varietà di proprietà diverse sui controlli di destinazione, quando tale <xref:System.Windows.FrameworkElement.Style%2A> risorsa di stile fa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]riferimento alla chiave di risorsa e viene utilizzata per impostare la proprietà di diversi elementi di controllo specifici definiti in .

Si noti che una delle proprietà `Label` all'interno `MyBrush` dei setter dello stile fa riferimento anche alla risorsa definita in precedenza. Si tratta di una tecnica comune, ma è importante ricordare che le risorse vengono analizzate e immesse in un dizionario risorse nell'ordine in cui vengono fornite. Le risorse vengono richieste anche dall'ordine trovato all'interno del dizionario se si utilizza l'estensione di [markup StaticResource](staticresource-markup-extension.md) per farvi riferimento dall'interno di un'altra risorsa. Assicurarsi che qualsiasi risorsa a cui si fa riferimento sia definita in precedenza all'interno della raccolta di risorse rispetto alla posizione in cui tale risorsa viene quindi richiesta. Se necessario, è possibile aggirare l'ordine di creazione rigoroso dei riferimenti alle risorse usando [un'estensione](dynamicresource-markup-extension.md) di markup DynamicResource per fare riferimento alla risorsa in fase di esecuzione, ma è necessario tenere presente che questa tecnica DynamicResource ha conseguenze sulle prestazioni. Per informazioni dettagliate, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>Vedere anche

- [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
