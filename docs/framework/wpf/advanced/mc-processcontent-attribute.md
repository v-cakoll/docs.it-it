---
title: Attributo mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: a9af18d1fac9101a75ac16918adf8e86ef7d2ba4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357378"
---
# <a name="mcprocesscontent-attribute"></a>Attributo mc:ProcessContent
Specifica quale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementi ancora il contenuto sarà elaborato da elementi padre pertinente, anche se l'elemento padre immediato può essere ignorato da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore a causa di specificando [mc: attributo Ignorable](mc-ignorable-attribute.md) . Il `mc:ProcessContent` attributo supporta la compatibilità dei markup per il mapping dello spazio dei nomi personalizzati sia per [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] controllo delle versioni.  
  
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
|*ignorablePrefix*|Qualsiasi stringa di prefisso valida, secondo la specifica XML 1.0.|  
|*ignorableUri*|Qualsiasi URI valido per la designazione di uno spazio dei nomi, secondo la specifica XML 1.0.|  
|*ThisElementCanBeIgnored*|Un elemento che può essere ignorato dagli [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] le implementazioni del processore, se il tipo sottostante non può essere risolto.|  
|*[contenuto]*|*ThisElementCanBeIgnored* è contrassegnato come può essere ignorato. Se il processore ignora questo elemento, *[contenuto]* viene elaborato dal *oggetto*.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore ignorerà il contenuto di un elemento ignorato. È possibile specificare un elemento specifico dal `mc:ProcessContent`e un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore continuerà a elaborare il contenuto all'interno dell'elemento ignorato. Ciò in genere vengono usato se il contenuto è annidato all'interno dei tag diversi, almeno uno dei quali è possibile ignorare e almeno uno dei quali non è possibile ignorare.  
  
 Più prefissi possono essere specificati nell'attributo, mediante uno spazio separatore, ad esempio: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 Il [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] spazio dei nomi definisce altri elementi e attributi che non sono documentati in questa area del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Per altre informazioni, vedere [specifica la compatibilità del Markup XML](https://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Vedere anche
- [Attributo mc:Ignorable](mc-ignorable-attribute.md)
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
