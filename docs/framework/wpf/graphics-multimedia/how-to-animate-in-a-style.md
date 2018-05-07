---
title: "Procedura: aggiungere un'animazione in uno stile"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: e0741a869ab81875aaa25340de851ef939e11a6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-in-a-style"></a>Procedura: aggiungere un'animazione in uno stile
In questo esempio viene illustrato come aggiungere un'animazione a una proprietà all'interno di uno stile. Quando l'animazione all'interno di uno stile, solo l'elemento del framework per cui viene definito lo stile è possibile assegnare direttamente. Per un oggetto freezable di destinazione, è necessario "punto verso il basso" da una proprietà dell'elemento con stile.  
  
 Nell'esempio seguente, numerose animazioni vengono definite all'interno di uno stile e applicate a un <xref:System.Windows.Controls.Button>. Quando l'utente sposta il puntatore del mouse su di esso, di dissolvenza da opaco a semitrasparente e nuovamente, più volte. Quando l'utente sposta il mouse dal pulsante, questo diventa completamente opaco. Quando si fa clic sul pulsante, il colore di sfondo cambia da arancione bianco e nuovamente. Poiché il <xref:System.Windows.Media.SolidColorBrush> usato per disegnare il pulsante non può essere utilizzato direttamente come destinazione, è possibile accedervi partendo verso il basso del pulsante <xref:System.Windows.Controls.Control.Background%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 Si noti che quando l'animazione all'interno di uno stile, è possibile per gli oggetti di destinazione che non sono presenti. Ad esempio, si supponga che lo stile utilizzi un <xref:System.Windows.Media.SolidColorBrush> per impostare proprietà di sfondo del pulsante, ma al momento lo stile è sottoposto a override e lo sfondo del pulsante viene impostato con un <xref:System.Windows.Media.LinearGradientBrush>.  Tentativo di aggiungere un'animazione di <xref:System.Windows.Media.SolidColorBrush> non genererà un'eccezione; l'animazione semplicemente un esito negativo.  
  
 Per ulteriori informazioni sulla sintassi di destinazione per storyboard, vedere il [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md). Per ulteriori informazioni sull'animazione, vedere il [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Per ulteriori informazioni sugli stili, vedere il [stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).
