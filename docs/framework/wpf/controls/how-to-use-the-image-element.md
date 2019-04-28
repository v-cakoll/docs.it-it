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
ms.openlocfilehash: 967159894e25721bdf380f851712e91d76088f87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696270"
---
# <a name="how-to-use-the-image-element"></a><span data-ttu-id="c1c85-102">Procedura: Usare l'elemento Image</span><span class="sxs-lookup"><span data-stu-id="c1c85-102">How to: Use the Image Element</span></span>
<span data-ttu-id="c1c85-103">Questo esempio illustra come includere immagini in un'applicazione usando il <xref:System.Windows.Controls.Image> elemento.</span><span class="sxs-lookup"><span data-stu-id="c1c85-103">This example shows how to include images in an application by using the <xref:System.Windows.Controls.Image> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1c85-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1c85-104">Example</span></span>  
 <span data-ttu-id="c1c85-105">L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel.</span><span class="sxs-lookup"><span data-stu-id="c1c85-105">The following example shows how to render an image 200 pixels wide.</span></span> <span data-ttu-id="c1c85-106">In questo esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], per definire l'immagine vengono usate sia la sintassi degli attributi e che la sintassi di tag di proprietà.</span><span class="sxs-lookup"><span data-stu-id="c1c85-106">In this [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example, both attribute syntax and property tag syntax are used to define the image.</span></span> <span data-ttu-id="c1c85-107">Per altre informazioni sulla sintassi di attributo e di proprietà, vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c1c85-107">For more information on attribute syntax and property syntax, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span> <span data-ttu-id="c1c85-108">Oggetto <xref:System.Windows.Media.Imaging.BitmapImage> viene usato per definire i dati di origine dell'immagine e viene definito in modo esplicito per l'esempio di sintassi di tag di proprietà.</span><span class="sxs-lookup"><span data-stu-id="c1c85-108">A <xref:System.Windows.Media.Imaging.BitmapImage> is used to define the image's source data and is explicitly defined for the property tag syntax example.</span></span> <span data-ttu-id="c1c85-109">Inoltre, il <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> del <xref:System.Windows.Media.Imaging.BitmapImage> è impostato per la stessa larghezza il <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Controls.Image>.</span><span class="sxs-lookup"><span data-stu-id="c1c85-109">In addition, the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> of the <xref:System.Windows.Media.Imaging.BitmapImage> is set to the same width as the <xref:System.Windows.FrameworkElement.Width%2A> of the <xref:System.Windows.Controls.Image>.</span></span> <span data-ttu-id="c1c85-110">In questo modo per il rendering dell'immagine viene usata la quantità minima di memoria.</span><span class="sxs-lookup"><span data-stu-id="c1c85-110">This is done to ensure that the minimum amount of memory is used rendering the image.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1c85-111">In generale, se si desidera specificare le dimensioni di un'immagine di rendering, specificare solo il <xref:System.Windows.FrameworkElement.Width%2A> o il <xref:System.Windows.FrameworkElement.Height%2A> ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="c1c85-111">In general, if you want to specify the size of a rendered image, specify only the <xref:System.Windows.FrameworkElement.Width%2A> or the <xref:System.Windows.FrameworkElement.Height%2A> but not both.</span></span> <span data-ttu-id="c1c85-112">Se si specifica solo uno di questi oggetti, le proporzioni dell'immagine vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="c1c85-112">If you only specify one, the image's aspect ratio is preserved.</span></span> <span data-ttu-id="c1c85-113">In caso contrario, l'immagine potrebbe apparire inaspettatamente allungata o distorta.</span><span class="sxs-lookup"><span data-stu-id="c1c85-113">Otherwise, the image may unexpectedly appear stretched or warped.</span></span> <span data-ttu-id="c1c85-114">Per controllare l'immagine del comportamento di adattamento, usare il <xref:System.Windows.Controls.Image.Stretch%2A> e <xref:System.Windows.Controls.Image.StretchDirection%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c1c85-114">To control the image's stretching behavior, use the <xref:System.Windows.Controls.Image.Stretch%2A> and <xref:System.Windows.Controls.Image.StretchDirection%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1c85-115">Quando si specifica la dimensione di un'immagine con uno <xref:System.Windows.FrameworkElement.Width%2A> oppure <xref:System.Windows.FrameworkElement.Height%2A>, è necessario impostare anche uno <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> alla rispettiva dimensione stessa.</span><span class="sxs-lookup"><span data-stu-id="c1c85-115">When you specify the size of an image with either <xref:System.Windows.FrameworkElement.Width%2A> or <xref:System.Windows.FrameworkElement.Height%2A>, you should also set either <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> or <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> to the same respective size.</span></span>  
  
 <span data-ttu-id="c1c85-116">Il <xref:System.Windows.Controls.Image.Stretch%2A> proprietà determina come l'origine dell'immagine viene adattata per riempire l'elemento image.</span><span class="sxs-lookup"><span data-stu-id="c1c85-116">The <xref:System.Windows.Controls.Image.Stretch%2A> property determines how the image source is stretched to fill the image element.</span></span> <span data-ttu-id="c1c85-117">Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Media.Stretch>.</span><span class="sxs-lookup"><span data-stu-id="c1c85-117">For more information, see the <xref:System.Windows.Media.Stretch> enumeration.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="c1c85-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1c85-118">Example</span></span>  
 <span data-ttu-id="c1c85-119">L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel usando il codice.</span><span class="sxs-lookup"><span data-stu-id="c1c85-119">The following example shows how to render an image 200 pixels wide using code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1c85-120">L'impostazione <xref:System.Windows.Media.Imaging.BitmapImage> delle proprietà devono essere eseguite all'interno di un <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> e <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> blocco.</span><span class="sxs-lookup"><span data-stu-id="c1c85-120">Setting <xref:System.Windows.Media.Imaging.BitmapImage> properties must be done within a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> and <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> block.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="c1c85-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1c85-121">See also</span></span>

- [<span data-ttu-id="c1c85-122">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="c1c85-122">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
