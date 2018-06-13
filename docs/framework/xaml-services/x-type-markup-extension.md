---
title: Estensione del markup x:Type
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: d3731a5249788b509c48623d8fa2284541f996ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563120"
---
# <a name="xtype-markup-extension"></a>Estensione del markup x:Type
CLR fornisce <xref:System.Type> oggetto che rappresenta il tipo sottostante per un tipo XAML specificato.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`prefix`|Facoltativo. Un prefisso che esegue il mapping di uno spazio dei nomi XAML non predefinito. Specifica un prefisso è spesso non necessaria. Vedere la sezione Osservazioni.|  
|`typeNameValue`|Obbligatorio. Un nome di tipo risolvibile in nomi XAML predefinito corrente; o specificato mappati prefisso se `prefix` viene fornito.|  
  
## <a name="remarks"></a>Note  
 Il `x:Type` estensione di markup è una funzione simile per il `typeof()` operatore in c# o `GetType` operatore in Microsoft Visual Basic.  
  
 Il `x:Type` estensione di markup fornisce un comportamento di conversione da stringa per le proprietà che accettano il tipo <xref:System.Type>. L'input è un tipo XAML. La relazione tra il tipo di sintassi XAML per gli input e output CLR <xref:System.Type> è che l'output <xref:System.Type> è il <xref:System.Xaml.XamlType.UnderlyingType%2A> dell'input <xref:System.Xaml.XamlType>, dopo avere cercato necessari <xref:System.Xaml.XamlType> basato sul contesto dello schema XAML e il <xref:System.Windows.Markup.IXamlTypeResolver>servizio fornisce il contesto.  
  
 Nei servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per la <xref:System.Windows.Markup.TypeExtension> classe.  
  
 In implementazioni framework specifiche, alcune proprietà che accettano <xref:System.Type> come un valore può accettare direttamente il nome del tipo (il valore di stringa del tipo `Name`). Tuttavia, l'implementazione di questo comportamento è uno scenario complesso. Per esempi, vedere la sezione "Note sull'utilizzo di WPF" di seguito.  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `x:Type` viene assegnato come valore <xref:System.Windows.Markup.TypeExtension.TypeName%2A> della classe dell'estensione <xref:System.Windows.Markup.TypeExtension> sottostante. Nel contesto dello schema XAML predefinito per i servizi XAML di .NET Framework, che è basato su tipi CLR, il valore di questo attributo può essere il <xref:System.Reflection.MemberInfo.Name%2A> del tipo desiderato, o che contiene <xref:System.Reflection.MemberInfo.Name%2A> preceduto da un prefisso per uno spazio dei nomi XAML non predefinito. mapping.  
  
 Il `x:Type` estensione di markup può essere utilizzato nella sintassi dell'elemento oggetto. In questo caso, se si specifica il valore di <xref:System.Windows.Markup.TypeExtension.TypeName%2A> proprietà è necessaria per inizializzare correttamente l'estensione.  
  
 Il `x:Type` estensione di markup può essere utilizzate anche come attributo dettagliato, tuttavia questo utilizzo non è tipico: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>Namespace XAML e Mapping dei tipi predefiniti  
 Spazio dei nomi XAML predefinito per la programmazione WPF contiene la maggior parte dei tipi di XAML, che è necessario per gli scenari tipici di XAML; Pertanto, è spesso possibile evitare i prefissi degli spazi quando si fa riferimento a valori di tipo XAML. Potrebbe essere necessario eseguire il mapping di un prefisso se si fa riferimento a un tipo da un assembly personalizzato o per i tipi presenti in un assembly WPF, ma sono compresi tra uno spazio dei nomi CLR che non è stato eseguito il mapping allo spazio dei nomi XAML predefinito. Per ulteriori informazioni sui prefissi di spazi dei nomi XAML e spazi dei nomi CLR di mapping, vedere [spazi dei nomi XAML e Mapping Namespace per XAML WPF](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Proprietà di tale supporto Typename come stringa di tipo  
 WPF supporta tecniche che consentono di specificare il valore di alcune proprietà del tipo <xref:System.Type> senza richiedere un `x:Type` utilizzo dell'estensione di markup. In alternativa, è possibile specificare il valore sotto forma di stringa che corrisponde al nome del tipo. Esempi di questo approccio sono <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> e <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. Supporto per questo comportamento non viene fornito tramite le estensioni di markup o convertitori di tipi. Al contrario, si tratta di un comportamento di rinvio implementato mediante <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight supporta una convenzione simile. In effetti, Silverlight attualmente non supporta `{x:Type}` nel supporto del linguaggio XAML e non accetta `{x:Type}` utilizzi di fuori di alcune condizioni che servono per supportare la migrazione di XAML di WPF e Silverlight. Pertanto, il comportamento di stringa come typename è incorporato in tutte le valutazioni delle proprietà native Silverlight in cui un <xref:System.Type> è il valore.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 fornisce supporto aggiuntivo per tipi generici e modifica il comportamento della funzionalità di `x:TypeArguments` e `x:Type` per fornire questo supporto.  
  
-   `x:TypeArguments` e può essere l'elemento oggetto associato per un'istanza di oggetto generico su elementi diversi dalla radice. Per ulteriori informazioni, vedere la sezione "XAML 2009" di [direttiva X:TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
-   XAML 2009 supporta una sintassi per specificare il vincolo del tipo generico nel markup. Può essere utilizzato da `x:TypeArguments`, da `x:Type`, o dalle due funzionalità in combinazione.  
  
-   Implementazione XAML di WPF durante l'elaborazione di XAML 2009 per il caricamento aggiunge anche questa funzionalità per il comportamento di conversione implicita del tipo per determinate proprietà del framework che utilizzano tipo <xref:System.Type>.  
  
 In WPF, è possibile utilizzare le funzionalità di XAML 2009, ma solo per XAML separato (XAML non compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Style>  
 [Applicazione di stili e modelli](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Cenni preliminari su XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Estensioni di markup e XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
