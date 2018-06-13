---
title: Estensione del markup ColorConvertedBitmap
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: 9b39e30cbe4e0bedc88c859f013b4d7175f7eb1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538910"
---
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="8438b-102">Estensione del markup ColorConvertedBitmap</span><span class="sxs-lookup"><span data-stu-id="8438b-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="8438b-103">Fornisce un modo per specificare una bitmap di origine che non dispone di un profilo incorporato.</span><span class="sxs-lookup"><span data-stu-id="8438b-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="8438b-104">Colore contesti / specificati dai profili [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], come l'origine dell'immagine [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8438b-104">Color contexts / profiles are specified by [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], as is the image source [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="8438b-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="8438b-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="8438b-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="8438b-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="8438b-107">Il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] di bitmap senza profilo.</span><span class="sxs-lookup"><span data-stu-id="8438b-107">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="8438b-108">Il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] di configurazione del profilo di origine.</span><span class="sxs-lookup"><span data-stu-id="8438b-108">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="8438b-109">Il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] di configurazione del profilo di destinazione</span><span class="sxs-lookup"><span data-stu-id="8438b-109">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8438b-110">Note</span><span class="sxs-lookup"><span data-stu-id="8438b-110">Remarks</span></span>  
 <span data-ttu-id="8438b-111">Questa estensione di markup deve compilare un set correlato di valori di proprietà di origine dell'immagine, ad esempio <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="8438b-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="8438b-112">La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="8438b-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="8438b-113">`ColorConvertedBitmap` (o `ColorConvertedBitmapExtension`) non può essere utilizzato nella sintassi degli elementi di proprietà, poiché i valori possono essere impostati solo come valori sul costruttore iniziale, ovvero la stringa dopo l'identificatore dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="8438b-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="8438b-114">`ColorConvertedBitmap` è un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="8438b-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="8438b-115">Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà.</span><span class="sxs-lookup"><span data-stu-id="8438b-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="8438b-116">Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="8438b-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="8438b-117">Per altre informazioni, vedere [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="8438b-117">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8438b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8438b-118">See Also</span></span>  
 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>  
 [<span data-ttu-id="8438b-119">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="8438b-119">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="8438b-120">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="8438b-120">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
