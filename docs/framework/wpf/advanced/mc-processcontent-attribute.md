---
title: Attributo mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: bcf55668bdc70902e346c401549a88f6ccb9072e
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095125"
---
# <a name="mcprocesscontent-attribute"></a>Attributo mc:ProcessContent
Specifica quali elementi di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] devono ancora avere contenuto elaborato da elementi padre pertinenti, anche se l'elemento padre diretto può essere ignorato da un processore di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] a causa della specifica dell' [attributo MC: Ignorable](mc-ignorable-attribute.md). L'attributo `mc:ProcessContent` supporta la compatibilità del markup sia per il mapping dello spazio dei nomi personalizzato che per il controllo delle versioni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
## <a name="xaml-attribute-usage"></a>Utilizzo della sintassi XAML per attributi  
  
```xaml  
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
  
## <a name="xaml-values"></a>Valor XAML  
  
|||  
|-|-|  
|*ignorablePrefix*|Qualsiasi stringa di prefisso valida, in base alla specifica XML 1,0.|  
|*ignorableUri*|Qualsiasi URI valido per la designazione di uno spazio dei nomi, in base alla specifica XML 1,0.|  
|*ThisElementCanBeIgnored*|Elemento che può essere ignorato dalle implementazioni del processore [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], se non è possibile risolvere il tipo sottostante.|  
|*contenuto*|*ThisElementCanBeIgnored* è contrassegnato come ignorable. Se il processore ignora tale elemento, *[content]* viene elaborato dall' *oggetto*.|  
  
## <a name="remarks"></a>Osservazioni  
 Per impostazione predefinita, un processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ignorerà il contenuto all'interno di un elemento ignorato. È possibile specificare un elemento specifico per `mc:ProcessContent`e un processore di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] continuerà a elaborare il contenuto all'interno dell'elemento ignorato. Questa operazione viene in genere usata se il contenuto è annidato all'interno di diversi tag, almeno uno dei quali è ignorabile e almeno uno di questi non è ignorabile.  
  
 È possibile specificare più prefissi nell'attributo, usando un separatore di spazio, ad esempio: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 Lo spazio dei nomi `http://schemas.openxmlformats.org/markup-compatibility/2006` definisce altri elementi e attributi non documentati in questa area dell'SDK. Per ulteriori informazioni, vedere [XML Markup Compatibility Specification](https://docs.microsoft.com/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>Vedere anche

- [Attributo mc:Ignorable](mc-ignorable-attribute.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
