---
title: "Procedura: Creare testo con un'ombreggiatura"
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 0fe64e4e9e7aadbd30a38743647251f9fa49ba95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960435"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="aac07-102">Procedura: Creare testo con un'ombreggiatura</span><span class="sxs-lookup"><span data-stu-id="aac07-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="aac07-103">Gli esempi inclusi in questa sezione mostrano come creare un effetto di ombreggiatura per il testo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="aac07-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aac07-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="aac07-104">Example</span></span>  
 <span data-ttu-id="aac07-105">L' <xref:System.Windows.Media.Effects.DropShadowEffect> oggetto consente di creare un'ampia gamma di effetti ombreggiatura per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="aac07-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="aac07-106">Nell'esempio seguente viene illustrato un effetto di ombreggiatura applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="aac07-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="aac07-107">Poiché in questo caso l'ombreggiatura è sfumata, il colore dell'ombreggiatura sarà sfocato.</span><span class="sxs-lookup"><span data-stu-id="aac07-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![Ombreggiatura del testo con &#61; morbidezza 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg) 
  
 <span data-ttu-id="aac07-109">È possibile controllare la larghezza di un'ombreggiatura impostando <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> la proprietà.</span><span class="sxs-lookup"><span data-stu-id="aac07-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="aac07-110">Il valore `4.0` indica una larghezza ombreggiata di 4 pixel.</span><span class="sxs-lookup"><span data-stu-id="aac07-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="aac07-111">È possibile controllare la morbidezza o la sfocatura di un'ombreggiatura modificando <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> la proprietà.</span><span class="sxs-lookup"><span data-stu-id="aac07-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="aac07-112">Un valore `0.0` indica che non è presente alcuna sfocatura.</span><span class="sxs-lookup"><span data-stu-id="aac07-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="aac07-113">Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura sfumata.</span><span class="sxs-lookup"><span data-stu-id="aac07-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> <span data-ttu-id="aac07-114">Questi effetti di ombreggiatura non passano attraverso [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] la pipeline di rendering del testo.</span><span class="sxs-lookup"><span data-stu-id="aac07-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="aac07-115">Di conseguenza, ClearType è disabilitato quando si usano questi effetti.</span><span class="sxs-lookup"><span data-stu-id="aac07-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="aac07-116">Nell'esempio seguente viene illustrato un effetto di ombreggiatura piena applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="aac07-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="aac07-117">In questo caso, l'ombreggiatura non è sfocata.</span><span class="sxs-lookup"><span data-stu-id="aac07-117">In this case, the shadow is not blurred.</span></span>  
  
 ![Ombreggiatura del testo con &#61; morbidezza 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg) 
  
 <span data-ttu-id="aac07-119">È possibile creare un'ombreggiatura rigida impostando <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> la `0.0`proprietà su, che indica che non viene utilizzata alcuna sfocatura.</span><span class="sxs-lookup"><span data-stu-id="aac07-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="aac07-120">È possibile controllare la direzione dell'ombreggiatura modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="aac07-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="aac07-121">Impostare il valore direzionale di questa proprietà su un grado compreso `0` tra `360`e.</span><span class="sxs-lookup"><span data-stu-id="aac07-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="aac07-122">Nella figura seguente vengono mostrati i valori direzionali <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> dell'impostazione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="aac07-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![Impostazione del grado DropShadow dell'ombreggiatura](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="aac07-124">Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura piena.</span><span class="sxs-lookup"><span data-stu-id="aac07-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="aac07-125">Uso di un effetto di sfocatura</span><span class="sxs-lookup"><span data-stu-id="aac07-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="aac07-126">Un <xref:System.Windows.Media.Effects.BlurBitmapEffect> oggetto può essere usato per creare un effetto simile all'ombreggiatura che può essere posizionato dietro un oggetto di testo.</span><span class="sxs-lookup"><span data-stu-id="aac07-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="aac07-127">Un effetto bitmap di sfocatura applicato al testo consente di sfocare il testo in tutte le direzioni in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="aac07-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="aac07-128">L'esempio seguente illustra un effetto di sfocatura applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="aac07-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![Ombreggiatura del testo con BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="aac07-130">Nell'esempio di codice seguente viene illustrato come creare un effetto di sfocatura.</span><span class="sxs-lookup"><span data-stu-id="aac07-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="aac07-131">Uso di una trasformazione di traslazione</span><span class="sxs-lookup"><span data-stu-id="aac07-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="aac07-132">Un <xref:System.Windows.Media.TranslateTransform> oggetto può essere usato per creare un effetto simile all'ombreggiatura che può essere posizionato dietro un oggetto di testo.</span><span class="sxs-lookup"><span data-stu-id="aac07-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="aac07-133">Nell'esempio di codice seguente viene <xref:System.Windows.Media.TranslateTransform> usato un oggetto per eseguire l'offset del testo.</span><span class="sxs-lookup"><span data-stu-id="aac07-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="aac07-134">In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="aac07-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![Ombreggiatura del testo con TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)    
  
 <span data-ttu-id="aac07-136">Nell'esempio di codice seguente viene illustrato come creare una trasformazione per un effetto di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="aac07-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
