---
title: Attributo mc:Ignorable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3be5949ee26fbb21d913a7aefe2664202c5bef38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mcignorable-attribute"></a>Attributo mc:Ignorable
Specifica quale [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefissi di spazio dei nomi rilevati in un file di markup possono essere ignorati da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore. Il `mc:Ignorable` attributo supporta la compatibilità dei markup per il mapping dello spazio dei nomi personalizzati e per [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] il controllo delle versioni.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>Utilizzo della sintassi XAML per gli attributi (prefisso singolo)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>Utilizzo della sintassi XAML per gli attributi (due prefissi)  
  
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
|*ignorablePrefix ignorablePrefix1, e così via.*|Qualsiasi stringa prefisso valido per la specifica XML 1.0.|  
|*ignorableUri*|Qualsiasi URI valido per la definizione di uno spazio dei nomi per la specifica XML 1.0.|  
|*ThisElementCanBeIgnored*|Un elemento che può essere ignorato dagli [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] le implementazioni del processore, se il tipo sottostante non può essere risolto.|  
  
## <a name="remarks"></a>Note  
 Il `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefisso dello spazio dei nomi è la convenzione di prefisso consigliato da usare durante il mapping di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibilità dello spazio dei nomi [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Gli elementi o attributi in cui la parte del prefisso del nome dell'elemento vengono identificati come `mc:Ignorable` non generano errori quando vengono elaborati da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore. Se tale attributo non può essere risolto in un costrutto di programmazione o il tipo sottostante, tale elemento viene ignorato. Si noti tuttavia che gli elementi ignorati potrebbero ancora generare ulteriori errori di analisi per altri requisiti dell'elemento che può avere effetti collaterali di tale elemento non viene elaborata. Ad esempio, un modello di contenuto di un elemento specifico potrebbe richiedere esattamente un elemento figlio, ma se l'elemento figlio specificato è stato un `mc:Ignorable` prefisso e l'elemento figlio specificato non può essere risolto in un tipo, il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] potrebbe processore Genera un errore.  
  
 `mc:Ignorable`si applica solo ai mapping dello spazio dei nomi alle stringhe dell'identificatore. `mc:Ignorable`non si applica ai mapping dello spazio dei nomi negli assembly, specificare un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] dello spazio dei nomi e un assembly (o predefinito per l'eseguibile dell'assembly corrente).  
  
 Se si implementa un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore, il processore non deve generare l'analisi o l'elaborazione di errori la risoluzione del tipo per qualsiasi elemento o attributo qualificato da un prefisso che è stato identificato come `mc:Ignorable`. Ma l'implementazione di processore può ancora generare eccezioni che sono il risultato di un elemento riesce a caricare o essere elaborati, ad esempio fornito in precedenza nell'esempio di elemento figlio di uno secondario.  
  
 Per impostazione predefinita, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore ignorerà il contenuto di un elemento ignorato. Tuttavia, è possibile specificare un attributo aggiuntivo, [mc: ProcessContent attributo](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), per richiedere l'elaborazione continua del contenuto all'interno di un elemento ignorato dall'elemento padre disponibile successivo.  
  
 Più prefissi possono essere specificati nell'attributo, utilizzando uno o più caratteri spazio come separatore, ad esempio: `mc:Ignorable="ignore1 ignore2"`.  
  
 Il [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] spazio dei nomi definisce altri elementi e attributi che non sono documentati in questa area del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Per ulteriori informazioni, vedere [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Markup.XamlReader>  
 [Attributo PresentationOptions:Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
