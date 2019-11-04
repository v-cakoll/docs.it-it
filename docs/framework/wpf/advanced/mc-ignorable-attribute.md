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
ms.openlocfilehash: d8fdeec8784c9a44c9b272a0a5a8b9c56ace5230
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458823"
---
# <a name="mcignorable-attribute"></a>Attributo mc:Ignorable
Specifica quali prefissi di spazio dei nomi [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] rilevati in un file di markup possono essere ignorati da un processore di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. L'attributo `mc:Ignorable` supporta la compatibilità del markup sia per il mapping dello spazio dei nomi personalizzato che per il controllo delle versioni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
## <a name="xaml-attribute-usage-single-prefix"></a>Utilizzo degli attributi XAML (prefisso singolo)  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>Utilizzo degli attributi XAML (due prefissi)  
  
```xaml  
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
|*ignorablePrefix, ignorablePrefix1 e così via.*|Qualsiasi stringa di prefisso valida, in base alla specifica XML 1,0.|  
|*ignorableUri*|Qualsiasi URI valido per la designazione di uno spazio dei nomi, in base alla specifica XML 1,0.|  
|*ThisElementCanBeIgnored*|Elemento che può essere ignorato dalle implementazioni del processore [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], se non è possibile risolvere il tipo sottostante.|  
  
## <a name="remarks"></a>Note  
 Il prefisso dello spazio dei nomi `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] è la convenzione di prefisso consigliata da usare per il mapping dello spazio dei nomi di compatibilità [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] `http://schemas.openxmlformats.org/markup-compatibility/2006`.  
  
 Gli elementi o gli attributi in cui la parte prefisso del nome dell'elemento sono identificati come `mc:Ignorable` non genereranno errori quando vengono elaborati da un processore di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Se tale attributo non può essere risolto in un tipo o un costrutto di programmazione sottostante, l'elemento viene ignorato. Si noti tuttavia che gli elementi ignorati possono comunque generare errori di analisi aggiuntivi per ulteriori requisiti degli elementi che sono effetti collaterali dell'elemento non elaborato. Ad esempio, un particolare modello di contenuto dell'elemento potrebbe richiedere esattamente un elemento figlio, ma se l'elemento figlio specificato si trovava in un prefisso `mc:Ignorable` e non è stato possibile risolvere l'elemento figlio specificato in un tipo, il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] potrebbe generare un errore.  
  
 `mc:Ignorable` si applica solo ai mapping dello spazio dei nomi alle stringhe identificatore. `mc:Ignorable` non si applica ai mapping dello spazio dei nomi negli assembly, che specificano uno spazio dei nomi CLR e un assembly (oppure il valore predefinito per l'eseguibile corrente come assembly).  
  
 Se si implementa un processore di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], l'implementazione del processore non deve generare errori di analisi o elaborazione sulla risoluzione del tipo per qualsiasi elemento o attributo qualificato da un prefisso identificato come `mc:Ignorable`. Tuttavia, l'implementazione del processore può comunque generare eccezioni che sono un risultato secondario di un errore di caricamento o elaborazione di un elemento, ad esempio un elemento figlio di esempio specificato in precedenza.  
  
 Per impostazione predefinita, un processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ignorerà il contenuto all'interno di un elemento ignorato. Tuttavia, è possibile specificare un attributo aggiuntivo, [MC: ProcessContent](mc-processcontent-attribute.md), per richiedere l'elaborazione continua del contenuto all'interno di un elemento ignorato dal successivo elemento padre disponibile.  
  
 È possibile specificare più prefissi nell'attributo, usando uno o più caratteri di spazio vuoto come separatore, ad esempio: `mc:Ignorable="ignore1 ignore2"`.  

 Lo spazio dei nomi `http://schemas.openxmlformats.org/markup-compatibility/2006` definisce altri elementi e attributi non documentati in questa area dell'SDK. Per ulteriori informazioni, vedere [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Markup.XamlReader>
- [Attributo PresentationOptions:Freeze](presentationoptions-freeze-attribute.md)
- [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Documenti in WPF](documents-in-wpf.md)
