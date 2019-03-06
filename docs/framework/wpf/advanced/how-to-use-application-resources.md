---
title: 'Procedura: Utilizzare le risorse delle applicazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: 8712f7c9c60d43cf3d0348b7c3f2f4cbee0b93b1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378886"
---
# <a name="how-to-use-application-resources"></a>Procedura: Utilizzare le risorse delle applicazioni
In questo esempio viene illustrato come usare le risorse delle applicazioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un file di definizione dell'applicazione (ADF). Il file di definizione dell'applicazione definisce una sezione di risorse (un valore per il <xref:System.Windows.Application.Resources%2A> proprietà). Le risorse definite a livello di applicazione sono accessibili da tutte le altre pagine che fanno parte dell'applicazione. In questo caso, la risorsa è uno stile dichiarato. Poiché uno stile completo che include un modello di controllo può richiedere molto tempo, in questo esempio viene omesso il modello di controllo definito all'interno di <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> setter delle proprietà dello stile.  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 L'esempio seguente mostra un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina che fa riferimento alla risorsa a livello di applicazione definita nell'esempio precedente. La risorsa viene fatto riferimento tramite un [estensione di Markup StaticResource](staticresource-markup-extension.md) che specifica la chiave di risorsa univoco per la risorsa richiesta. Nella pagina corrente non è stata rilevata alcuna risorsa con chiave "GelButton", pertanto l'ambito di ricerca per la risorsa richiesta continua oltre la pagina corrente e nelle risorse definite a livello di applicazione.  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>Vedere anche
- [Risorse XAML](xaml-resources.md)
- [Cenni preliminari sulla gestione di applicazioni](../app-development/application-management-overview.md)
- [Procedure relative alle proprietà](resources-how-to-topics.md)
