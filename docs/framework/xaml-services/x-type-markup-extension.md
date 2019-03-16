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
ms.openlocfilehash: 86e5619774cc1512e39fa2fb50f4c0ba5f1d074c
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58042089"
---
# <a name="xtype-markup-extension"></a>Estensione del markup x:Type
Fornisce Common Language Runtime <xref:System.Type> oggetto che rappresenta il tipo sottostante per un tipo XAML specificato.  
  
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
|`prefix`|Facoltativo. Un prefisso che esegue il mapping di uno spazio dei nomi XAML non predefinito. Specifica un prefisso è frequentemente non necessaria. Vedere la sezione Osservazioni.|  
|`typeNameValue`|Obbligatorio. Nome di un tipo risolvibile in nomi XAML predefinito corrente; o specificato mappati prefisso se `prefix` fornito.|  
  
## <a name="remarks"></a>Note  
 Il `x:Type` estensione di markup è una funzione simile al `typeof()` operatore in c# o `GetType` operatore in Microsoft Visual Basic.  
  
 Il `x:Type` estensione di markup fornisca un comportamento di conversione da stringa per le proprietà che accettano il tipo <xref:System.Type>. L'input è un tipo XAML. La relazione tra il tipo XAML di input e output di CLR <xref:System.Type> è che l'output <xref:System.Type> è la <xref:System.Xaml.XamlType.UnderlyingType%2A> dell'input <xref:System.Xaml.XamlType>, dopo aver cercato le necessarie <xref:System.Xaml.XamlType> basata sul contesto dello schema XAML e la <xref:System.Windows.Markup.IXamlTypeResolver>service fornisce il contesto.  
  
 Nei servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.Markup.TypeExtension> classe.  
  
 Nelle implementazioni su framework specifici, alcune proprietà che accettano <xref:System.Type> come un valore possibile accettare il nome del tipo direttamente (il valore di stringa del tipo `Name`). Tuttavia, che implementa questo comportamento è uno scenario complesso. Per esempi, vedere la sezione "Note di utilizzo WPF" di seguito.  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `x:Type` viene assegnato come valore <xref:System.Windows.Markup.TypeExtension.TypeName%2A> della classe dell'estensione <xref:System.Windows.Markup.TypeExtension> sottostante. Sotto il contesto dello schema XAML predefinito per i servizi XAML di .NET Framework, che si basa sui tipi CLR, il valore di questo attributo è il <xref:System.Reflection.MemberInfo.Name%2A> del tipo desiderato, o che contiene <xref:System.Reflection.MemberInfo.Name%2A> preceduto da un prefisso per uno spazio dei nomi XAML non predefinito esecuzione del mapping.  
  
 Il `x:Type` estensione di markup può essere utilizzata nella sintassi degli elementi oggetto. In questo caso, specificando il valore di <xref:System.Windows.Markup.TypeExtension.TypeName%2A> proprietà è obbligatoria per inizializzare correttamente l'estensione.  
  
 Il `x:Type` estensione di markup può essere usato anche come attributo dettagliato; tuttavia questo utilizzo non è tipico: `<object property="{x:Type TypeName=typeNameValue}" .../>`  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>Namespace XAML e Mapping dei tipi predefiniti  
 Lo spazio dei nomi XAML predefinito per la programmazione WPF contiene la maggior parte dei tipi XAML che è necessario per scenari tipici di XAML; Pertanto, è spesso possibile evitare i prefissi degli spazi quando si fa riferimento a valori di tipi XAML. Si potrebbe essere necessario eseguire il mapping di un prefisso se si fa riferimento a un tipo da un assembly personalizzato o per i tipi presenti in un assembly WPF, ma sono compresi tra uno spazio dei nomi CLR che non è stato eseguito il mapping allo spazio dei nomi XAML predefinito. Per altre informazioni sui prefissi degli spazi dei nomi XAML e spazi dei nomi CLR di mapping, vedere [spazi dei nomi XAML e Mapping Namespace per XAML WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Tipo di proprietà di tale supporto Typename come stringa  
 WPF supporta le tecniche che consentono di specificare il valore di alcune proprietà di tipo <xref:System.Type> senza richiedere un `x:Type` utilizzo dell'estensione di markup. In alternativa, è possibile specificare il valore sotto forma di stringa che denomina il tipo. Esempi di questo approccio sono <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> e <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. Supporto per questo comportamento non viene fornito tramite le estensioni di markup o convertitori di tipi. Al contrario, si tratta di un comportamento di differimento implementato tramite <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight supporta una convenzione simile. In effetti, Silverlight non supporta attualmente `{x:Type}` dal supporto di linguaggio XAML e non accetta `{x:Type}` utilizzi di fuori di alcune condizioni che sono progettate per supportare la migrazione di XAML di WPF e Silverlight. Pertanto, il comportamento del tipo typename come stringa è incorporato in tutte le valutazioni delle proprietà native Silverlight in cui un <xref:System.Type> è il valore.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 fornisce ulteriore supporto per tipi generici e il comportamento della funzionalità di modifica `x:TypeArguments` e `x:Type` per fornire questo supporto.  
  
-   `x:TypeArguments` e può essere l'elemento oggetto associato per la creazione di un'istanza di oggetto generico negli elementi diversa dalla quella radice. Per altre informazioni, vedere la sezione "XAML 2009" di [X:TypeArguments Directive](x-typearguments-directive.md).  
  
-   XAML 2009 supporta una sintassi per la specifica di vincolo di un tipo generico nel markup. Questo può essere usato da `x:TypeArguments`, da `x:Type`, oppure le due funzionalità nella combinazione.  
  
-   Implementazione WPF XAML durante l'elaborazione di XAML 2009 per carico aggiunge anche questa funzionalità per il comportamento di conversione implicita del tipo per determinate proprietà del framework che usano il tipo <xref:System.Type>.  
  
 In WPF, è possibile usare le funzionalità di XAML 2009, ma solo per XAML loose (XAML non è compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Style>
- [Applicazione di stili e modelli](../wpf/controls/styling-and-templating.md)
- [Cenni preliminari su XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
