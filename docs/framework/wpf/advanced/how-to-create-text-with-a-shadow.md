---
title: 'Procedura: Creare testo con ombreggiatura'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: c3e8135372ce4a092552c812cd971cb70bc49bf3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186853"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="2f52b-102">Procedura: Creare testo con ombreggiatura</span><span class="sxs-lookup"><span data-stu-id="2f52b-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="2f52b-103">Gli esempi inclusi in questa sezione mostrano come creare un effetto di ombreggiatura per il testo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="2f52b-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f52b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f52b-104">Example</span></span>  
 <span data-ttu-id="2f52b-105">L'oggetto <xref:System.Windows.Media.Effects.DropShadowEffect> consente di creare una varietà [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] di effetti di ombreggiatura per gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="2f52b-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="2f52b-106">Nell'esempio seguente viene illustrato un effetto di ombreggiatura applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="2f52b-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="2f52b-107">Poiché in questo caso l'ombreggiatura è sfumata, il colore dell'ombreggiatura sarà sfocato.</span><span class="sxs-lookup"><span data-stu-id="2f52b-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![Ombreggiatura del testo con &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg)
  
 <span data-ttu-id="2f52b-109">È possibile controllare la larghezza di <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> un'ombreggiatura impostando la proprietà .</span><span class="sxs-lookup"><span data-stu-id="2f52b-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="2f52b-110">Il valore `4.0` di indica una larghezza di ombreggiatura di 4 pixel.</span><span class="sxs-lookup"><span data-stu-id="2f52b-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="2f52b-111">È possibile controllare la morbidezza, o sfocatura, di un'ombra modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2f52b-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="2f52b-112">Il valore `0.0` di indica nessuna sfocatura.</span><span class="sxs-lookup"><span data-stu-id="2f52b-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="2f52b-113">Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura sfumata.</span><span class="sxs-lookup"><span data-stu-id="2f52b-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> <span data-ttu-id="2f52b-114">Questi effetti di ombreggiatura [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] non passano attraverso la pipeline di rendering del testo.</span><span class="sxs-lookup"><span data-stu-id="2f52b-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="2f52b-115">Di conseguenza, ClearType è disabilitato quando si usano questi effetti.</span><span class="sxs-lookup"><span data-stu-id="2f52b-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="2f52b-116">Nell'esempio seguente viene illustrato un effetto di ombreggiatura piena applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="2f52b-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="2f52b-117">In questo caso, l'ombreggiatura non è sfocata.</span><span class="sxs-lookup"><span data-stu-id="2f52b-117">In this case, the shadow is not blurred.</span></span>  
  
 ![Ombreggiatura del testo con morbidezza &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg)
  
 <span data-ttu-id="2f52b-119">È possibile creare un'ombreggiatura rigida impostando la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> proprietà su `0.0`, che indica che non viene utilizzata alcuna sfocatura.</span><span class="sxs-lookup"><span data-stu-id="2f52b-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="2f52b-120">È possibile controllare la direzione <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> dell'ombreggiatura modificando la proprietà .</span><span class="sxs-lookup"><span data-stu-id="2f52b-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="2f52b-121">Impostare il valore direzionale di `0` `360`questa proprietà su un grado compreso tra e .</span><span class="sxs-lookup"><span data-stu-id="2f52b-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="2f52b-122">Nella figura seguente vengono illustrati <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> i valori direzionali dell'impostazione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2f52b-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![Impostazione del grado DropShadow dell'ombreggiatura](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="2f52b-124">Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura piena.</span><span class="sxs-lookup"><span data-stu-id="2f52b-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="2f52b-125">Uso di un effetto di sfocatura</span><span class="sxs-lookup"><span data-stu-id="2f52b-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="2f52b-126">Un <xref:System.Windows.Media.Effects.BlurBitmapEffect> può essere utilizzato per creare un effetto simile a un'ombreggiatura che può essere posizionato dietro un oggetto di testo.</span><span class="sxs-lookup"><span data-stu-id="2f52b-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="2f52b-127">Un effetto bitmap di sfocatura applicato al testo consente di sfocare il testo in tutte le direzioni in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="2f52b-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="2f52b-128">L'esempio seguente illustra un effetto di sfocatura applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="2f52b-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![Ombreggiatura del testo con BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="2f52b-130">Nell'esempio di codice seguente viene illustrato come creare un effetto di sfocatura.</span><span class="sxs-lookup"><span data-stu-id="2f52b-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="2f52b-131">Uso di una trasformazione di traslazione</span><span class="sxs-lookup"><span data-stu-id="2f52b-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="2f52b-132">Un <xref:System.Windows.Media.TranslateTransform> può essere utilizzato per creare un effetto simile a un'ombreggiatura che può essere posizionato dietro un oggetto di testo.</span><span class="sxs-lookup"><span data-stu-id="2f52b-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="2f52b-133">Nell'esempio di <xref:System.Windows.Media.TranslateTransform> codice riportato di seguito viene illustrato come utilizzare un oggetto per eseguire l'offset del testo.</span><span class="sxs-lookup"><span data-stu-id="2f52b-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="2f52b-134">In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="2f52b-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![Ombreggiatura del testo con TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)
  
 <span data-ttu-id="2f52b-136">Nell'esempio di codice seguente viene illustrato come creare una trasformazione per un effetto di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="2f52b-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
