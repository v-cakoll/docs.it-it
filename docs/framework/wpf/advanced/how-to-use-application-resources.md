---
title: 'Procedura: Usare le risorse delle applicazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: e4114466fa8016f8e31100d7a37038b0abfdccca
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460261"
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="a4720-102">Procedura: Usare le risorse delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="a4720-102">How to: Use Application Resources</span></span>
<span data-ttu-id="a4720-103">In questo esempio viene illustrato come usare le risorse delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a4720-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4720-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4720-104">Example</span></span>  
 <span data-ttu-id="a4720-105">L'esempio seguente mostra un file di definizione dell'applicazione (ADF).</span><span class="sxs-lookup"><span data-stu-id="a4720-105">The following example shows an application definition file.</span></span> <span data-ttu-id="a4720-106">Il file di definizione dell'applicazione definisce una sezione di risorse (un valore per la proprietà <xref:System.Windows.Application.Resources%2A>).</span><span class="sxs-lookup"><span data-stu-id="a4720-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="a4720-107">Le risorse definite a livello di applicazione sono accessibili da tutte le altre pagine che fanno parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a4720-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="a4720-108">In questo caso, la risorsa è uno stile dichiarato.</span><span class="sxs-lookup"><span data-stu-id="a4720-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="a4720-109">Poiché uno stile completo che include un modello di controllo può essere lungo, questo esempio omette il modello di controllo definito all'interno del setter della proprietà <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> dello stile.</span><span class="sxs-lookup"><span data-stu-id="a4720-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="a4720-110">Nell'esempio seguente viene illustrata una pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che fa riferimento alla risorsa a livello di applicazione definita dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="a4720-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="a4720-111">Si fa riferimento alla risorsa usando un' [estensione di markup StaticResource](staticresource-markup-extension.md) che specifica la chiave di risorsa univoca per la risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="a4720-111">The resource is referenced by using a     [StaticResource Markup Extension](staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="a4720-112">Nella pagina corrente non è stata rilevata alcuna risorsa con chiave "GelButton", pertanto l'ambito di ricerca per la risorsa richiesta continua oltre la pagina corrente e nelle risorse definite a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="a4720-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="a4720-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4720-113">See also</span></span>

- [<span data-ttu-id="a4720-114">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="a4720-114">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="a4720-115">Cenni preliminari sulla gestione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="a4720-115">Application Management Overview</span></span>](../app-development/application-management-overview.md)
- [<span data-ttu-id="a4720-116">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="a4720-116">How-to Topics</span></span>](resources-how-to-topics.md)
