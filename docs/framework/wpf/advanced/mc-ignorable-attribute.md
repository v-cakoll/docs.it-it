---
title: Attributo mc:Ignorable
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: 40c1a8513608728a84b6b605f9ad18603123ea2e
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401538"
---
# <a name="mcignorable-attribute"></a>Attributo mc:Ignorable
Specifica quali [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefissi di spazio dei nomi rilevati in un file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup possono essere ignorati da un processore. L' `mc:Ignorable` attributo supporta la compatibilità del markup sia per il mapping dello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] spazio dei nomi personalizzato che per il controllo delle versioni.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>Utilizzo degli attributi XAML (prefisso singolo)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>Utilizzo degli attributi XAML (due prefissi)  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|*ignorablePrefix, ignorablePrefix1, etc.*|Qualsiasi stringa di prefisso valida, in base alla specifica XML 1,0.|  
|*ignorableUri*|Qualsiasi URI valido per la designazione di uno spazio dei nomi, in base alla specifica XML 1,0.|  
|*ThisElementCanBeIgnored*|Elemento che può essere ignorato dalle [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] implementazioni del processore, se il tipo sottostante non può essere risolto.|  
  
## <a name="remarks"></a>Note  
 Il `mc` [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]prefisso dello spazio dei nomi è la convenzione di prefisso consigliata da usare per il mapping dello spazio dei nomi Compatibility. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]  
  
 Gli elementi o gli attributi in `mc:Ignorable` cui viene identificata la parte prefisso del nome dell'elemento non generano errori quando vengono elaborati da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore. Se tale attributo non può essere risolto in un tipo o un costrutto di programmazione sottostante, l'elemento viene ignorato. Si noti tuttavia che gli elementi ignorati possono comunque generare errori di analisi aggiuntivi per ulteriori requisiti degli elementi che sono effetti collaterali dell'elemento non elaborato. Ad esempio, un modello di contenuto dell'elemento specifico potrebbe richiedere esattamente un elemento figlio, ma se l'elemento figlio specificato si `mc:Ignorable` trovava in un prefisso e non è stato possibile risolvere l'elemento figlio specificato in un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tipo, il processore potrebbe genera un errore.  
  
 `mc:Ignorable`si applica solo ai mapping dello spazio dei nomi alle stringhe identificatore. `mc:Ignorable`non si applica ai mapping dello spazio dei nomi negli assembly, che specificano uno spazio dei nomi CLR e un assembly (o l'eseguibile predefinito come assembly).  
  
 Se si implementa un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore, l'implementazione del processore non deve generare errori di analisi o elaborazione sulla risoluzione del tipo per qualsiasi elemento o attributo qualificato da un prefisso identificato come. `mc:Ignorable` Tuttavia, l'implementazione del processore può comunque generare eccezioni che sono un risultato secondario di un errore di caricamento o elaborazione di un elemento, ad esempio un elemento figlio di esempio specificato in precedenza.  
  
 Per impostazione predefinita, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un processore ignorerà il contenuto all'interno di un elemento ignorato. Tuttavia, è possibile specificare un attributo aggiuntivo, [MC: ProcessContent](mc-processcontent-attribute.md), per richiedere l'elaborazione continua del contenuto all'interno di un elemento ignorato dal successivo elemento padre disponibile.  
  
 È possibile specificare più prefissi nell'attributo, usando uno o più caratteri di spazio vuoto come separatore, ad esempio: `mc:Ignorable="ignore1 ignore2"`.  

 Lo [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] spazio dei nomi definisce altri elementi e attributi che non sono documentati in questa [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]area di. Per ulteriori informazioni, vedere [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Markup.XamlReader>
- [Attributo PresentationOptions:Freeze](presentationoptions-freeze-attribute.md)
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Documenti in WPF](documents-in-wpf.md)
