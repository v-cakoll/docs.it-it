---
title: "Procedure dettagliate: creazione di un pulsante personalizzato a cui è stata aggiunta un'animazione"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ece907b23772504990ef334f446d7b6072f5d44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="cef49-102">Procedure dettagliate: creazione di un pulsante personalizzato a cui è stata aggiunta un'animazione</span><span class="sxs-lookup"><span data-stu-id="cef49-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="cef49-103">Come suggerisce il nome, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] è ideale per offrire un'esperienza di presentazione avanzata per i clienti.</span><span class="sxs-lookup"><span data-stu-id="cef49-103">As its name suggests, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="cef49-104">Queste procedure viene illustrato come personalizzare l'aspetto e comportamento di un pulsante (animazioni incluse).</span><span class="sxs-lookup"><span data-stu-id="cef49-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="cef49-105">Questa personalizzazione viene eseguita utilizzando uno stile e il modello in modo che è possibile applicare facilmente questo pulsante personalizzato a tutti i pulsanti nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cef49-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="cef49-106">Nella figura seguente mostra il pulsante personalizzato che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="cef49-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="cef49-107">![Pulsante personalizzato che verrà creato](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="cef49-107">![The customized button that you will create](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="cef49-108">La grafica vettoriale che costituiscono l'aspetto del pulsante viene creata utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cef49-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="cef49-109">è simile a HTML, ma è più potente ed estendibile.</span><span class="sxs-lookup"><span data-stu-id="cef49-109"> is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<span data-ttu-id="cef49-110">possono essere digitati manualmente utilizzando Microsoft Visual Studio o blocco note oppure è possibile utilizzare uno strumento di progettazione visiva quale Microsoft Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="cef49-110"> can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="cef49-111">Expression Blend funziona creando sottostante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] codice, pertanto entrambi i metodi creano la grafica stesso.</span><span class="sxs-lookup"><span data-stu-id="cef49-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cef49-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="cef49-112">In This Section</span></span>  
 [<span data-ttu-id="cef49-113">Creare un pulsante usando Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="cef49-113">Create a Button by Using Microsoft Expression Blend</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="cef49-114">Viene illustrato come creare i pulsanti con un comportamento personalizzato utilizzando le funzionalità della finestra di progettazione di Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="cef49-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="cef49-115">Creare un pulsante usando XAML</span><span class="sxs-lookup"><span data-stu-id="cef49-115">Create a Button by Using XAML</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="cef49-116">Di seguito viene illustrato come creare pulsanti con un comportamento personalizzato utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cef49-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cef49-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="cef49-117">Related Sections</span></span>  
 [<span data-ttu-id="cef49-118">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="cef49-118">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 <span data-ttu-id="cef49-119">Viene descritto come stili e modelli possono essere utilizzati per determinare l'aspetto e il comportamento dei controlli.</span><span class="sxs-lookup"><span data-stu-id="cef49-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="cef49-120">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="cef49-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="cef49-121">Viene descritto come gli oggetti possono essere animati utilizzando il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sistema di animazione e temporizzazione.</span><span class="sxs-lookup"><span data-stu-id="cef49-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="cef49-122">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="cef49-122">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="cef49-123">Viene descritto come utilizzare gli oggetti pennello, disegnare con colori a tinta unita, gradienti lineari e radiali.</span><span class="sxs-lookup"><span data-stu-id="cef49-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="cef49-124">Panoramica sugli effetti bitmap</span><span class="sxs-lookup"><span data-stu-id="cef49-124">Bitmap Effects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="cef49-125">Vengono descritti gli effetti bitmap supportati da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] e viene spiegato come applicarli.</span><span class="sxs-lookup"><span data-stu-id="cef49-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
