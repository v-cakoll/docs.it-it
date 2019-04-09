---
title: "Procedura: Usare le risorse dell'applicazione"
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: 70dff8089c4da70fdc61247a0c604cf7ee85d02b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088203"
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="6d0d4-102">Procedura: Usare le risorse dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6d0d4-102">How to: Use Application Resources</span></span>
<span data-ttu-id="6d0d4-103">In questo esempio viene illustrato come usare le risorse delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6d0d4-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d0d4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d0d4-104">Example</span></span>  
 <span data-ttu-id="6d0d4-105">L'esempio seguente mostra un file di definizione dell'applicazione (ADF).</span><span class="sxs-lookup"><span data-stu-id="6d0d4-105">The following example shows an application definition file.</span></span> <span data-ttu-id="6d0d4-106">Il file di definizione dell'applicazione definisce una sezione di risorse (un valore per il <xref:System.Windows.Application.Resources%2A> proprietà).</span><span class="sxs-lookup"><span data-stu-id="6d0d4-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="6d0d4-107">Le risorse definite a livello di applicazione sono accessibili da tutte le altre pagine che fanno parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6d0d4-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="6d0d4-108">In questo caso, la risorsa è uno stile dichiarato.</span><span class="sxs-lookup"><span data-stu-id="6d0d4-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="6d0d4-109">Poiché uno stile completo che include un modello di controllo può richiedere molto tempo, in questo esempio viene omesso il modello di controllo definito all'interno di <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> setter delle proprietà dello stile.</span><span class="sxs-lookup"><span data-stu-id="6d0d4-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="6d0d4-110">L'esempio seguente mostra un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina che fa riferimento alla risorsa a livello di applicazione definita nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="6d0d4-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="6d0d4-111">La risorsa viene fatto riferimento tramite un [estensione di Markup StaticResource](staticresource-markup-extension.md) che specifica la chiave di risorsa univoco per la risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="6d0d4-111">The resource is referenced by using a     [StaticResource Markup Extension](staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="6d0d4-112">Nella pagina corrente non è stata rilevata alcuna risorsa con chiave "GelButton", pertanto l'ambito di ricerca per la risorsa richiesta continua oltre la pagina corrente e nelle risorse definite a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="6d0d4-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="6d0d4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d0d4-113">See also</span></span>

- [<span data-ttu-id="6d0d4-114">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="6d0d4-114">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="6d0d4-115">Cenni preliminari sulla gestione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6d0d4-115">Application Management Overview</span></span>](../app-development/application-management-overview.md)
- [<span data-ttu-id="6d0d4-116">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="6d0d4-116">How-to Topics</span></span>](resources-how-to-topics.md)
