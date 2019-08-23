---
title: "Procedura: Usare l'elemento Image"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: 164eee7c10d9e388c6e6ee695af479ca2d6974b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958319"
---
# <a name="how-to-use-the-image-element"></a>Procedura: Usare l'elemento Image
Questo esempio illustra come includere immagini in un'applicazione usando l' <xref:System.Windows.Controls.Image> elemento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel. In questo esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], per definire l'immagine vengono usate sia la sintassi degli attributi e che la sintassi di tag di proprietà. Per altre informazioni sulla sintassi di attributo e di proprietà, vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md). Un <xref:System.Windows.Media.Imaging.BitmapImage> viene usato per definire i dati di origine dell'immagine ed è definito in modo esplicito per l'esempio di sintassi dei tag della proprietà. Inoltre, l'oggetto <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> <xref:System.Windows.Media.Imaging.BitmapImage> di viene impostato sulla stessa <xref:System.Windows.Controls.Image>larghezza <xref:System.Windows.FrameworkElement.Width%2A> dell'oggetto di. In questo modo per il rendering dell'immagine viene usata la quantità minima di memoria.  
  
> [!NOTE]
> In generale, se si desidera specificare le dimensioni di un'immagine sottoposta a rendering, <xref:System.Windows.FrameworkElement.Width%2A> specificare solo <xref:System.Windows.FrameworkElement.Height%2A> o ma non entrambi. Se si specifica solo uno di questi oggetti, le proporzioni dell'immagine vengono mantenute. In caso contrario, l'immagine potrebbe apparire inaspettatamente allungata o distorta. Per controllare il comportamento di estensione dell'immagine, usare le <xref:System.Windows.Controls.Image.Stretch%2A> proprietà <xref:System.Windows.Controls.Image.StretchDirection%2A> e.  
  
> [!NOTE]
> Quando si specificano le dimensioni di un'immagine con <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> è necessario impostare anche o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> sulla stessa dimensione corrispondente.  
  
 La <xref:System.Windows.Controls.Image.Stretch%2A> proprietà determina il modo in cui l'origine dell'immagine viene adattata per riempire l'elemento immagine. Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Media.Stretch>.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel usando il codice.  
  
> [!NOTE]
> L' <xref:System.Windows.Media.Imaging.BitmapImage> impostazione delle proprietà deve essere eseguita <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> all' <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> interno di un blocco e.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla creazione dell'immagine](../graphics-multimedia/imaging-overview.md)
