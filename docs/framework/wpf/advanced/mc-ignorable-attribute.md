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
ms.openlocfilehash: e8fa4c084ae9c775a18de06c344b2c0b439c2b1b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517361"
---
# <a name="mcignorable-attribute"></a>Attributo mc:Ignorable
Specifica quale [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefissi dello spazio dei nomi rilevati in un file di markup possono essere ignorati da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore. Il `mc:Ignorable` attributo supporta la compatibilità dei markup per il mapping dello spazio dei nomi personalizzati sia per [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] controllo delle versioni.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>Utilizzo degli attributi XAML (singolo prefisso)  
  
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
|*ignorablePrefix ignorablePrefix1, e così via.*|Qualsiasi stringa di prefisso valida, secondo la specifica XML 1.0.|  
|*ignorableUri*|Qualsiasi URI valido per la designazione di uno spazio dei nomi, secondo la specifica XML 1.0.|  
|*ThisElementCanBeIgnored*|Un elemento che può essere ignorato dagli [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] le implementazioni del processore, se il tipo sottostante non può essere risolto.|  
  
## <a name="remarks"></a>Note  
 Il `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefisso dello spazio dei nomi è la convenzione di prefisso consigliato da usare durante il mapping di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dello spazio dei nomi di compatibilità [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Gli elementi o attributi in cui la parte del prefisso del nome dell'elemento sono identificati come `mc:Ignorable` non genera errori durante l'elaborazione da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore. Se tale attributo non può essere risolta in un tipo sottostante o il costrutto di programmazione, tale elemento viene ignorato. Si noti tuttavia che gli elementi ignorati comunque potrebbero generare ulteriori errori di analisi per i requisiti di elemento aggiuntivo che può avere effetti collaterali di tale elemento non vengono elaborate. Ad esempio, un modello di contenuto di un elemento specifico potrebbe richiedere esattamente un elemento figlio, ma se l'elemento figlio specificato è stato un `mc:Ignorable` prefisso e l'elemento figlio specificato non può essere risolto in un tipo, il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] potrebbe processore Genera un errore.  
  
 `mc:Ignorable` si applica solo ai mapping dello spazio dei nomi alle stringhe dell'identificatore. `mc:Ignorable` non si applica a mapping dello spazio dei nomi negli assembly, specificare un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] dello spazio dei nomi e un assembly (o predefinito per l'eseguibile dell'assembly corrente).  
  
 Se si implementa una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore, il processore non deve generare l'analisi o la risoluzione del tipo per qualsiasi elemento o attributo che è qualificato da un prefisso che viene identificato come errori di elaborazione `mc:Ignorable`. Ma l'implementazione del processore può comunque generare eccezioni che sono il risultato secondario di un elemento riesce a caricare o essere elaborato, come illustrato nell'esempio solo elemento figlio riportato in precedenza.  
  
 Per impostazione predefinita, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore ignorerà il contenuto di un elemento ignorato. Tuttavia, è possibile specificare un attributo aggiuntivo, [attributo mc: ProcessContent](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), richiede l'elaborazione di continuo del contenuto all'interno di un elemento ignorato dall'elemento padre disponibile successivo.  
  
 Più prefissi possono essere specificati nell'attributo, usando uno o più caratteri spazio come separatore, ad esempio: `mc:Ignorable="ignore1 ignore2"`.  

 Il [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] spazio dei nomi definisce altri elementi e attributi che non sono documentati in questa area del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Per altre informazioni, vedere [specifica la compatibilità del Markup XML](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Markup.XamlReader>  
 [Attributo PresentationOptions:Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
