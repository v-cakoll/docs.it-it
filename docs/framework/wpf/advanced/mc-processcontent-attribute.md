---
title: Attributo mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 2e93734b8ab4aefca080736db3a512f272625271
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545253"
---
# <a name="mcprocesscontent-attribute"></a>Attributo mc:ProcessContent
Specifica quale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementi dovrebbero disporre ancora elaborato il contenuto da elementi padre rilevanti, anche se l'elemento padre immediato può essere ignorato da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore a causa dell'impostazione [mc: attributo Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) . Il `mc:ProcessContent` attributo supporta la compatibilità dei markup per il mapping dello spazio dei nomi personalizzati e per [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] il controllo delle versioni.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|*ignorablePrefix*|Qualsiasi stringa prefisso valido per la specifica XML 1.0.|  
|*ignorableUri*|Qualsiasi URI valido per la definizione di uno spazio dei nomi per la specifica XML 1.0.|  
|*ThisElementCanBeIgnored*|Un elemento che può essere ignorato dagli [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] le implementazioni del processore, se il tipo sottostante non può essere risolto.|  
|*[contenuto]*|*ThisElementCanBeIgnored* è contrassegnato come ignorable. Se il processore ignora tale elemento, *[contenuto]* viene elaborato da *oggetto*.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore ignorerà il contenuto di un elemento ignorato. È possibile specificare un elemento specifico da `mc:ProcessContent`e un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore continuerà a elaborare il contenuto all'interno dell'elemento ignorato. Questo viene in genere utilizzato se il contenuto viene nidificato all'interno di altri tag, almeno uno dei quali è ignorable e almeno uno dei quali non lo sia.  
  
 Più prefissi possono essere specificati nell'attributo, utilizzando un separatore, ad esempio: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 Il [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] spazio dei nomi definisce altri elementi e attributi che non sono documentati in questa area del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Per ulteriori informazioni, vedere [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Vedere anche  
 [Attributo mc:Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
