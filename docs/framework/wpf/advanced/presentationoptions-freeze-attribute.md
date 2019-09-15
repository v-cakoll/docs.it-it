---
title: Attributo PresentationOptions:Freeze
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991433"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="adfb1-102">Attributo PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="adfb1-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="adfb1-103">Imposta lo <xref:System.Windows.Freezable.IsFrozen%2A> `true` stato su sull'elemento contenitore <xref:System.Windows.Freezable> .</span><span class="sxs-lookup"><span data-stu-id="adfb1-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="adfb1-104">Il comportamento predefinito per <xref:System.Windows.Freezable> un oggetto `PresentationOptions:Freeze` senza l'attributo specificato <xref:System.Windows.Freezable.IsFrozen%2A> è `false` che è in fase di caricamento e dipende <xref:System.Windows.Freezable> dal comportamento generale in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="adfb1-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="adfb1-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="adfb1-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="adfb1-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="adfb1-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="adfb1-107">Prefisso dello spazio dei nomi XML, che può essere qualsiasi stringa di prefisso valida, in base alla specifica XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="adfb1-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="adfb1-108">Il prefisso `PresentationOptions` viene usato per scopi di identificazione in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="adfb1-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="adfb1-109">Elemento che crea un'istanza di qualsiasi classe derivata <xref:System.Windows.Freezable>di.</span><span class="sxs-lookup"><span data-stu-id="adfb1-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adfb1-110">Note</span><span class="sxs-lookup"><span data-stu-id="adfb1-110">Remarks</span></span>  
 <span data-ttu-id="adfb1-111">L' `Freeze` attributo è l'unico attributo o altro elemento `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` di programmazione definito nello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="adfb1-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="adfb1-112">L' `Freeze` attributo esiste in questo particolare spazio dei nomi specifico, in modo che possa essere designato come ignorabile, usando l' [attributo MC: Ignorable](mc-ignorable-attribute.md) come parte delle dichiarazioni degli elementi radice.</span><span class="sxs-lookup"><span data-stu-id="adfb1-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="adfb1-113">Il motivo per `Freeze` cui deve essere possibile ignorare è il fatto che non tutte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] le implementazioni del processore sono in grado <xref:System.Windows.Freezable> di bloccare un oggetto in fase di caricamento. questa funzionalità [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non fa parte della specifica.</span><span class="sxs-lookup"><span data-stu-id="adfb1-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="adfb1-114">La possibilità di elaborare l' `Freeze` attributo è incorporata in modo specifico [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nel processore che [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elabora le applicazioni compilate.</span><span class="sxs-lookup"><span data-stu-id="adfb1-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="adfb1-115">L'attributo non è supportato da alcuna classe e la sintassi dell'attributo non è estendibile o modificabile.</span><span class="sxs-lookup"><span data-stu-id="adfb1-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="adfb1-116">Se si implementa un processore personalizzato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , è possibile scegliere di eseguire il blocco del comportamento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] del processore durante l'elaborazione `Freeze` dell'attributo <xref:System.Windows.Freezable> sugli elementi in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="adfb1-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="adfb1-117">Qualsiasi valore per l' `Freeze` attributo diverso da `true` (senza distinzione tra maiuscole e minuscole) genera un errore in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="adfb1-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="adfb1-118">(Specificando `Freeze` l'attributo `false` come non è un errore, ma è già l'impostazione predefinita, pertanto l' `false` impostazione di su non esegue alcuna operazione).</span><span class="sxs-lookup"><span data-stu-id="adfb1-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adfb1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adfb1-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="adfb1-120">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="adfb1-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="adfb1-121">Attributo mc:Ignorable</span><span class="sxs-lookup"><span data-stu-id="adfb1-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
