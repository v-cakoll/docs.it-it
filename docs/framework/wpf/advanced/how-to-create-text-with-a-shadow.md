---
title: 'Procedura: Creare testo con ombreggiatura'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31bbc3da54c10304e52f93d38365a8d9ed005505
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="c7f97-102">Procedura: Creare testo con ombreggiatura</span><span class="sxs-lookup"><span data-stu-id="c7f97-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="c7f97-103">Gli esempi inclusi in questa sezione mostrano come creare un effetto di ombreggiatura per il testo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="c7f97-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7f97-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7f97-104">Example</span></span>  
 <span data-ttu-id="c7f97-105">Il <xref:System.Windows.Media.Effects.DropShadowEffect> oggetto consente di creare una varietà di effetti di ombreggiatura per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] oggetti.</span><span class="sxs-lookup"><span data-stu-id="c7f97-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="c7f97-106">Nell'esempio seguente viene illustrato un effetto di ombreggiatura applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="c7f97-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="c7f97-107">Poiché in questo caso l'ombreggiatura è sfumata, il colore dell'ombreggiatura sarà sfocato.</span><span class="sxs-lookup"><span data-stu-id="c7f97-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 <span data-ttu-id="c7f97-108">![Ombreggiatura del testo con Softness &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")</span><span class="sxs-lookup"><span data-stu-id="c7f97-108">![Text shadow with Softness &#61; 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")</span></span>  
<span data-ttu-id="c7f97-109">Esempio di testo con un'ombreggiatura sfumata</span><span class="sxs-lookup"><span data-stu-id="c7f97-109">Example of text with a soft shadow</span></span>  
  
 <span data-ttu-id="c7f97-110">È possibile controllare la larghezza dell'ombreggiatura impostando il <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c7f97-110">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="c7f97-111">Il valore `4.0` indica la larghezza dell'ombreggiatura di 4 pixel.</span><span class="sxs-lookup"><span data-stu-id="c7f97-111">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="c7f97-112">È possibile controllare la sfumatura, o sfocatura, di un'ombreggiatura modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c7f97-112">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="c7f97-113">Il valore `0.0` non indica nessuna sfocatura.</span><span class="sxs-lookup"><span data-stu-id="c7f97-113">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="c7f97-114">Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura sfumata.</span><span class="sxs-lookup"><span data-stu-id="c7f97-114">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  <span data-ttu-id="c7f97-115">Questi effetti di ombreggiatura passa attraverso il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] pipeline di rendering del testo.</span><span class="sxs-lookup"><span data-stu-id="c7f97-115">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="c7f97-116">Di conseguenza, ClearType è disabilitato quando si usano questi effetti.</span><span class="sxs-lookup"><span data-stu-id="c7f97-116">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="c7f97-117">Nell'esempio seguente viene illustrato un effetto di ombreggiatura piena applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="c7f97-117">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="c7f97-118">In questo caso, l'ombreggiatura non è sfocata.</span><span class="sxs-lookup"><span data-stu-id="c7f97-118">In this case, the shadow is not blurred.</span></span>  
  
 <span data-ttu-id="c7f97-119">![Ombreggiatura del testo con Softness &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")</span><span class="sxs-lookup"><span data-stu-id="c7f97-119">![Text shadow with Softness &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")</span></span>  
<span data-ttu-id="c7f97-120">Esempio di testo con un'ombreggiatura piena</span><span class="sxs-lookup"><span data-stu-id="c7f97-120">Example of text with a hard shadow</span></span>  
  
 <span data-ttu-id="c7f97-121">È possibile creare un'ombreggiatura impostando il <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> proprietà `0.0`, che indica che è utilizzata nessuna sfocatura.</span><span class="sxs-lookup"><span data-stu-id="c7f97-121">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="c7f97-122">È possibile controllare la direzione dell'ombreggiatura modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c7f97-122">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="c7f97-123">Impostare il valore direzionale di questa proprietà su un livello tra `0` e `360`.</span><span class="sxs-lookup"><span data-stu-id="c7f97-123">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="c7f97-124">La figura seguente mostra i valori di direzionale il <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> l'impostazione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c7f97-124">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 <span data-ttu-id="c7f97-125">![Impostazione del grado DropShadow dell'ombreggiatura](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")</span><span class="sxs-lookup"><span data-stu-id="c7f97-125">![DropShadow degree setting of shadow](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")</span></span>  
<span data-ttu-id="c7f97-126">Diagramma di direzione DropShadow</span><span class="sxs-lookup"><span data-stu-id="c7f97-126">DropShadow Direction diagram</span></span>  
  
 <span data-ttu-id="c7f97-127">Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura piena.</span><span class="sxs-lookup"><span data-stu-id="c7f97-127">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="c7f97-128">Uso di un effetto di sfocatura</span><span class="sxs-lookup"><span data-stu-id="c7f97-128">Using a Blur Effect</span></span>  
 <span data-ttu-id="c7f97-129">Oggetto <xref:System.Windows.Media.Effects.BlurBitmapEffect> può essere utilizzato per creare un effetto di ombreggiatura simile che può essere posizionato dietro un oggetto testo.</span><span class="sxs-lookup"><span data-stu-id="c7f97-129">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="c7f97-130">Un effetto bitmap di sfocatura applicato al testo consente di sfocare il testo in tutte le direzioni in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="c7f97-130">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="c7f97-131">L'esempio seguente illustra un effetto di sfocatura applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="c7f97-131">The following example shows a blur effect applied to text.</span></span>  
  
 <span data-ttu-id="c7f97-132">![Ombreggiatura del testo con BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")</span><span class="sxs-lookup"><span data-stu-id="c7f97-132">![Text shadow using a BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")</span></span>  
<span data-ttu-id="c7f97-133">Esempio di testo con un effetto di sfocatura</span><span class="sxs-lookup"><span data-stu-id="c7f97-133">Example of text with a blur effect</span></span>  
  
 <span data-ttu-id="c7f97-134">Nell'esempio di codice seguente viene illustrato come creare un effetto di sfocatura.</span><span class="sxs-lookup"><span data-stu-id="c7f97-134">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="c7f97-135">Uso di una trasformazione di traslazione</span><span class="sxs-lookup"><span data-stu-id="c7f97-135">Using a Translate Transform</span></span>  
 <span data-ttu-id="c7f97-136">Oggetto <xref:System.Windows.Media.TranslateTransform> può essere utilizzato per creare un effetto di ombreggiatura simile che può essere posizionato dietro un oggetto testo.</span><span class="sxs-lookup"><span data-stu-id="c7f97-136">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="c7f97-137">Nell'esempio di codice viene illustrato come utilizzare un <xref:System.Windows.Media.TranslateTransform> per spostare il testo.</span><span class="sxs-lookup"><span data-stu-id="c7f97-137">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="c7f97-138">In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="c7f97-138">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 <span data-ttu-id="c7f97-139">![Ombreggiatura del testo con TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")</span><span class="sxs-lookup"><span data-stu-id="c7f97-139">![Text shadow using a TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")</span></span>  
<span data-ttu-id="c7f97-140">Esempio di testo che usa una trasformazione per un effetto di ombreggiatura</span><span class="sxs-lookup"><span data-stu-id="c7f97-140">Example of text using a transform for a shadow effect</span></span>  
  
 <span data-ttu-id="c7f97-141">Nell'esempio di codice seguente viene illustrato come creare una trasformazione per un effetto di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="c7f97-141">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
