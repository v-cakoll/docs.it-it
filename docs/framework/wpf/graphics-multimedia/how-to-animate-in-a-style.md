---
title: Come aggiungere un'animazione in uno stile (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: a455bbfb9defbcf83f7e490f60031917a3b41779
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46516730"
---
# <a name="how-to-animate-in-a-style"></a>Come aggiungere un'animazione in uno stile

In questo esempio illustra come animare le proprietà all'interno di uno stile. Quando si anima all'interno di uno stile, solo l'elemento del framework per cui è definito lo stile può essere assegnato direttamente. Per un oggetto freezable di destinazione, è necessario "punto verso il basso" da una proprietà dell'elemento con stile.

Nell'esempio seguente vengono definite all'interno di uno stile e applicate alla diverse animazioni una <xref:System.Windows.Controls.Button>. Quando l'utente sposta il puntatore del mouse su esso, viene applicata la dissolvenza da opaco per semitrasparente e anche in questo caso, più volte. Quando l'utente sposta il mouse dal pulsante, questo diventa completamente opaco. Quando si fa clic sul pulsante, il colore di sfondo cambia da arancione su bianco e viceversa. Poiché il <xref:System.Windows.Media.SolidColorBrush> utilizzato per disegnare il pulsante non può essere assegnato direttamente, è possibile accedervi partendo verso il basso del pulsante <xref:System.Windows.Controls.Control.Background%2A> proprietà.

## <a name="example"></a>Esempio

[!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

Si noti che quando si anima all'interno di uno stile, è possibile per gli oggetti di destinazione che non esistono. Ad esempio, si supponga che utilizza lo stile di un <xref:System.Windows.Media.SolidColorBrush> per impostare proprietà dello sfondo del pulsante, ma a un certo punto lo stile viene sottoposto a override e lo sfondo del pulsante viene impostato con un <xref:System.Windows.Media.LinearGradientBrush>.  Tentativo di aggiungere un'animazione di <xref:System.Windows.Media.SolidColorBrush> non genererà un'eccezione; l'animazione non verrà semplicemente eseguite automaticamente.

Per altre informazioni sulla sintassi di destinazione per storyboard, vedere la [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md). Per altre informazioni sulle animazioni, vedere la [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Per altre informazioni sugli stili, vedere la [stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).
