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
ms.openlocfilehash: df0b3fe53cb8f284fc6e2d79a9b2cea86318d701
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459910"
---
# <a name="xtype-markup-extension"></a>Estensione del markup x:Type
Fornisce l'oggetto <xref:System.Type> CLR che rappresenta il tipo sottostante per un tipo XAML specificato.  
  
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
|`prefix`|Parametro facoltativo. Prefisso che esegue il mapping di uno spazio dei nomi XAML non predefinito. Spesso non è necessario specificare un prefisso. Vedere la sezione Osservazioni.|  
|`typeNameValue`|Obbligatorio. Nome del tipo risolvibile nello spazio dei nomi XAML predefinito corrente. o il prefisso mappato specificato se viene specificato `prefix`.|  
  
## <a name="remarks"></a>Note  
 L'estensione di markup `x:Type` dispone di una funzione analoga all'operatore C# `typeof()` in o all'operatore `GetType` in Microsoft Visual Basic.  
  
 Il `x:Type` estensione di markup fornisce un comportamento di conversione da stringa per le proprietà che accettano il tipo <xref:System.Type>. L'input è un tipo XAML. La relazione tra il tipo XAML di input e il <xref:System.Type> CLR di output è che il <xref:System.Type> di output è il <xref:System.Xaml.XamlType.UnderlyingType%2A> della <xref:System.Xaml.XamlType>di input, dopo aver cercato i <xref:System.Xaml.XamlType> necessari in base al contesto dello schema XAML e al servizio <xref:System.Windows.Markup.IXamlTypeResolver> fornito dal contesto.  
  
 In .NET Framework servizi XAML, la gestione di questa estensione di markup viene definita dalla classe <xref:System.Windows.Markup.TypeExtension>.  
  
 Nelle implementazioni di Framework specifiche alcune proprietà che accettano <xref:System.Type> come valore possono accettare direttamente il nome del tipo (il valore stringa del tipo `Name`). Tuttavia, l'implementazione di questo comportamento è uno scenario complesso. Per esempi, vedere la sezione "Note sull'utilizzo di WPF" riportata di seguito.  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `x:Type` viene assegnato come valore <xref:System.Windows.Markup.TypeExtension.TypeName%2A> della classe dell'estensione <xref:System.Windows.Markup.TypeExtension> sottostante. Nel contesto dello schema XAML predefinito per .NET Framework servizi XAML, che è basato sui tipi CLR, il valore di questo attributo è l'<xref:System.Reflection.MemberInfo.Name%2A> del tipo desiderato o contiene che <xref:System.Reflection.MemberInfo.Name%2A> preceduto da un prefisso per un mapping dello spazio dei nomi XAML non predefinito.  
  
 È possibile utilizzare l'estensione di markup `x:Type` nella sintassi dell'elemento oggetto. In questo caso, è necessario specificare il valore della proprietà <xref:System.Windows.Markup.TypeExtension.TypeName%2A> per inizializzare correttamente l'estensione.  
  
 L'estensione di markup `x:Type` può essere usata anche come attributo dettagliato; Questo utilizzo non è tuttavia tipico: `<object property="{x:Type TypeName=typeNameValue}" .../>`  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>Mapping di tipi e spazi dei nomi XAML predefiniti  
 Lo spazio dei nomi XAML predefinito per la programmazione WPF contiene la maggior parte dei tipi XAML necessari per gli scenari XAML tipici. Pertanto, è spesso possibile evitare i prefissi quando si fa riferimento a valori di tipo XAML. Potrebbe essere necessario eseguire il mapping di un prefisso se si fa riferimento a un tipo da un assembly personalizzato o per i tipi presenti in un assembly WPF, ma provenienti da uno spazio dei nomi CLR di cui non è stato eseguito il mapping allo spazio dei nomi XAML predefinito. Per ulteriori informazioni sui prefissi, gli spazi dei nomi XAML e il mapping di spazi dei nomi CLR, vedere [spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Proprietà del tipo che supportano typeName-As-String  
 WPF supporta tecniche che consentono di specificare il valore di alcune proprietà di tipo <xref:System.Type> senza richiedere l'utilizzo di un'estensione di markup `x:Type`. In alternativa, è possibile specificare il valore come stringa che assegna un nome al tipo. Esempi di questo esempio sono <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> e <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. Il supporto di questo comportamento non viene fornito tramite convertitori di tipi o estensioni di markup. Al contrario, si tratta di un comportamento di rinvio implementato tramite <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight supporta una convenzione simile. In realtà, Silverlight non supporta attualmente `{x:Type}` nel supporto del linguaggio XAML e non accetta `{x:Type}` utilizzi al di fuori di alcune circostanze destinate a supportare la migrazione XAML WPF-Silverlight. Pertanto, il comportamento di typeName come stringa è incorporato a tutti i tipi di valutazione delle proprietà native di Silverlight, in cui un <xref:System.Type> è il valore.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 fornisce supporto aggiuntivo per i tipi generici e modifica il comportamento della funzionalità di `x:TypeArguments` e `x:Type` per fornire questo supporto.  
  
- `x:TypeArguments` e l'elemento oggetto associato per la creazione di un'istanza di un oggetto generico possono trovarsi su elementi diversi dalla radice. Per ulteriori informazioni, vedere la sezione "XAML 2009" della [direttiva x:TypeArguments](x-typearguments-directive.md).  
  
- XAML 2009 supporta una sintassi per specificare il vincolo di un tipo generico nel markup. Questo può essere usato da `x:TypeArguments`, da `x:Type`o dalle due funzionalità in combinazione.  
  
- L'implementazione XAML di WPF quando si elabora XAML 2009 per Load aggiunge anche questa funzionalità al comportamento di conversione implicita del tipo per determinate proprietà del Framework che usano il tipo <xref:System.Type>.  
  
 In WPF è possibile usare le funzionalità XAML 2009, ma solo per XAML separato (XAML non compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Style>
- [Applicazione di stili e modelli](../wpf/controls/styling-and-templating.md)
- [Cenni preliminari su XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
