---
title: 'Procedura: Usare le risorse delle applicazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: 4305c49c4322d164e2481c1508dda7c038c14694
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544157"
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="e5e3a-102">Procedura: Usare le risorse delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="e5e3a-102">How to: Use Application Resources</span></span>
<span data-ttu-id="e5e3a-103">In questo esempio viene illustrato come usare le risorse delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e5e3a-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5e3a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5e3a-104">Example</span></span>  
 <span data-ttu-id="e5e3a-105">L'esempio seguente mostra un file di definizione dell'applicazione (ADF).</span><span class="sxs-lookup"><span data-stu-id="e5e3a-105">The following example shows an application definition file.</span></span> <span data-ttu-id="e5e3a-106">File di definizione dell'applicazione definisce una sezione delle risorse (un valore per il <xref:System.Windows.Application.Resources%2A> proprietà).</span><span class="sxs-lookup"><span data-stu-id="e5e3a-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="e5e3a-107">Le risorse definite a livello di applicazione sono accessibili da tutte le altre pagine che fanno parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5e3a-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="e5e3a-108">In questo caso, la risorsa è uno stile dichiarato.</span><span class="sxs-lookup"><span data-stu-id="e5e3a-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="e5e3a-109">Poiché uno stile completo che include un modello di controllo può richiedere molto tempo, in questo esempio viene omesso il modello di controllo in cui è definito il <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> setter di proprietà dello stile.</span><span class="sxs-lookup"><span data-stu-id="e5e3a-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="e5e3a-110">Nell'esempio seguente un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina che fa riferimento alla risorsa a livello di applicazione definita nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="e5e3a-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="e5e3a-111">La risorsa viene fatto riferimento utilizzando un [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) che specifica la chiave di risorsa univoca per la risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="e5e3a-111">The resource is referenced by using a     [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="e5e3a-112">Nella pagina corrente non è stata rilevata alcuna risorsa con chiave "GelButton", pertanto l'ambito di ricerca per la risorsa richiesta continua oltre la pagina corrente e nelle risorse definite a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5e3a-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="e5e3a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5e3a-113">See Also</span></span>  
 [<span data-ttu-id="e5e3a-114">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="e5e3a-114">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="e5e3a-115">Cenni preliminari sulla gestione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="e5e3a-115">Application Management Overview</span></span>](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [<span data-ttu-id="e5e3a-116">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="e5e3a-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
