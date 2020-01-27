---
title: Come aggiungere un'animazione in uno stile
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 0b29648bf15f0046adcdee610f9565f7deb24972
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744888"
---
# <a name="how-to-animate-in-a-style"></a>Come aggiungere un'animazione in uno stile

Questo esempio illustra come animare le proprietà all'interno di uno stile. Quando si esegue un'animazione all'interno di uno stile, solo l'elemento Framework per il quale è definito lo stile può essere indirizzato direttamente. Per fare riferimento a un oggetto Freezable, è necessario eseguire il "punto" per difetto da una proprietà dell'elemento con stile.

Nell'esempio seguente vengono definite diverse animazioni in uno stile e applicate a un <xref:System.Windows.Controls.Button>. Quando l'utente sposta il puntatore del mouse sul pulsante, si affievolisce da opaco a parzialmente trasparente e viceversa, ripetutamente. Quando l'utente sposta il mouse fuori dal pulsante, diventa completamente opaco. Quando si fa clic sul pulsante, il colore di sfondo passa da arancione a bianco e viceversa. Poiché le <xref:System.Windows.Media.SolidColorBrush> utilizzate per disegnare il pulsante non possono essere indirizzate direttamente, è possibile accedervi tramite il delineamento dalla proprietà <xref:System.Windows.Controls.Control.Background%2A> del pulsante.

## <a name="example"></a>Esempio

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

Si noti che quando si aggiunge un'animazione all'interno di uno stile, è possibile fare riferimento a oggetti che non esistono. Si supponga, ad esempio, che lo stile usi un <xref:System.Windows.Media.SolidColorBrush> per impostare la proprietà background di un pulsante, ma a un certo punto lo stile venga sottoposto a override e lo sfondo del pulsante viene impostato con una <xref:System.Windows.Media.LinearGradientBrush>.  Il tentativo di animare il <xref:System.Windows.Media.SolidColorBrush> non genererà un'eccezione. l'animazione avrà semplicemente esito negativo.

Per ulteriori informazioni sulla sintassi di destinazione dello storyboard, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md). Per ulteriori informazioni sulle animazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md). Per ulteriori informazioni sugli stili, vedere applicazione di stili [e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).
