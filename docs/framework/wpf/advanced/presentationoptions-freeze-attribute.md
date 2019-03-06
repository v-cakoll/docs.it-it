---
title: Attributo PresentationOptions:Freeze
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: 3ff4a3221392d6b247d0a486e4e1f0406f539362
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378861"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="eca8f-102">Attributo PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="eca8f-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="eca8f-103">Imposta il <xref:System.Windows.Freezable.IsFrozen%2A> torni allo stato `true` nel contenitore <xref:System.Windows.Freezable> elemento.</span><span class="sxs-lookup"><span data-stu-id="eca8f-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="eca8f-104">Il comportamento predefinito per un <xref:System.Windows.Freezable> senza il `PresentationOptions:Freeze` attributo specificato è quello <xref:System.Windows.Freezable.IsFrozen%2A> viene `false` al tempo di caricamento e dipendente in generale <xref:System.Windows.Freezable> comportamento in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="eca8f-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="eca8f-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="eca8f-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="eca8f-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="eca8f-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="eca8f-107">Un prefisso di spazio dei nomi XML, che può essere qualsiasi stringa di prefisso valida, secondo la specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="eca8f-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="eca8f-108">Il prefisso `PresentationOptions` viene usato per scopi di identificazione in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="eca8f-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="eca8f-109">Un elemento che crea un'istanza di una classe derivata di <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="eca8f-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eca8f-110">Note</span><span class="sxs-lookup"><span data-stu-id="eca8f-110">Remarks</span></span>  
 <span data-ttu-id="eca8f-111">Il `Freeze` attributo è l'unico attributo o altri elementi di programmazione definito nel `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="eca8f-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="eca8f-112">Il `Freeze` attributo è presente in questo spazio dei nomi speciale in particolare in modo che può essere definito come ignorable, usando [mc: attributo Ignorable](mc-ignorable-attribute.md) come parte di dichiarazioni dell'elemento radice.</span><span class="sxs-lookup"><span data-stu-id="eca8f-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="eca8f-113">Il motivo che `Freeze` deve essere in grado di essere ignorabile è perché non tutti i [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] le implementazioni del processore sono in grado di bloccare un <xref:System.Windows.Freezable> in fase di caricamento; questa funzionalità non è in parte il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specifica.</span><span class="sxs-lookup"><span data-stu-id="eca8f-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="eca8f-114">La possibilità di elaborare il `Freeze` attributo è stato compilato appositamente per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore che elabora [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per le applicazioni compilate.</span><span class="sxs-lookup"><span data-stu-id="eca8f-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="eca8f-115">L'attributo non è supportato da qualsiasi classe, e la sintassi di attributo non è estendibile o modificabile.</span><span class="sxs-lookup"><span data-stu-id="eca8f-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="eca8f-116">Se si implementa il proprio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore è possibile scegliere per il comportamento di blocco in parallelo il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore durante l'elaborazione il `Freeze` attributo <xref:System.Windows.Freezable> elementi in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="eca8f-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="eca8f-117">Qualsiasi valore per il `Freeze` attributo diverso da `true` (non maiuscole / minuscole) genera un errore in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="eca8f-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="eca8f-118">(Specificare il `Freeze` dell'attributo come `false` non è un errore, ma che è già l'impostazione predefinita, pertanto l'impostazione `false` non esegue alcuna operazione).</span><span class="sxs-lookup"><span data-stu-id="eca8f-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca8f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eca8f-119">See also</span></span>
- <xref:System.Windows.Freezable>
- [<span data-ttu-id="eca8f-120">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="eca8f-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="eca8f-121">Attributo mc:Ignorable</span><span class="sxs-lookup"><span data-stu-id="eca8f-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
