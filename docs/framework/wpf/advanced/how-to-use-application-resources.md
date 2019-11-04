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
# <a name="how-to-use-application-resources"></a>Procedura: Usare le risorse delle applicazioni
In questo esempio viene illustrato come usare le risorse delle applicazioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un file di definizione dell'applicazione (ADF). Il file di definizione dell'applicazione definisce una sezione di risorse (un valore per la proprietà <xref:System.Windows.Application.Resources%2A>). Le risorse definite a livello di applicazione sono accessibili da tutte le altre pagine che fanno parte dell'applicazione. In questo caso, la risorsa è uno stile dichiarato. Poiché uno stile completo che include un modello di controllo può essere lungo, questo esempio omette il modello di controllo definito all'interno del setter della proprietà <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> dello stile.  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 Nell'esempio seguente viene illustrata una pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che fa riferimento alla risorsa a livello di applicazione definita dall'esempio precedente. Si fa riferimento alla risorsa usando un' [estensione di markup StaticResource](staticresource-markup-extension.md) che specifica la chiave di risorsa univoca per la risorsa richiesta. Nella pagina corrente non è stata rilevata alcuna risorsa con chiave "GelButton", pertanto l'ambito di ricerca per la risorsa richiesta continua oltre la pagina corrente e nelle risorse definite a livello di applicazione.  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>Vedere anche

- [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Cenni preliminari sulla gestione di applicazioni](../app-development/application-management-overview.md)
- [Procedure relative alle proprietà](resources-how-to-topics.md)
