---
title: Attributo mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 619c3ffbc68c8c72ea9dd6545ab8da536380483b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70206174"
---
# <a name="mcprocesscontent-attribute"></a>Attributo mc:ProcessContent
Specifica quali [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementi devono ancora essere elaborati da elementi padre pertinenti, anche se l'elemento padre diretto può essere ignorato da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore a causa della specifica dell' [attributo MC: Ignorable](mc-ignorable-attribute.md). L' `mc:ProcessContent` attributo supporta la compatibilità del markup sia per il mapping dello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] spazio dei nomi personalizzato che per il controllo delle versioni.  
  
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
|*ignorablePrefix*|Qualsiasi stringa di prefisso valida, in base alla specifica XML 1,0.|  
|*ignorableUri*|Qualsiasi URI valido per la designazione di uno spazio dei nomi, in base alla specifica XML 1,0.|  
|*ThisElementCanBeIgnored*|Elemento che può essere ignorato dalle [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] implementazioni del processore, se il tipo sottostante non può essere risolto.|  
|*contenuto*|*ThisElementCanBeIgnored* è contrassegnato come ignorable. Se il processore ignora tale elemento, *[content]* viene elaborato dall' *oggetto*.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un processore ignorerà il contenuto all'interno di un elemento ignorato. È possibile specificare un elemento specifico da `mc:ProcessContent`e un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore continuerà a elaborare il contenuto all'interno dell'elemento ignorato. Questa operazione viene in genere usata se il contenuto è annidato all'interno di diversi tag, almeno uno dei quali è ignorabile e almeno uno di questi non è ignorabile.  
  
 È possibile specificare più prefissi nell'attributo, usando un separatore di spazio, ad esempio `mc:ProcessContent="ignore:Element1 ignore:Element2"`:.  
  
 Lo `http://schemas.openxmlformats.org/markup-compatibility/2006` spazio dei nomi definisce altri elementi e attributi non documentati in questa area dell'SDK. Per ulteriori informazioni, vedere [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Vedere anche

- [Attributo mc:Ignorable](mc-ignorable-attribute.md)
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
