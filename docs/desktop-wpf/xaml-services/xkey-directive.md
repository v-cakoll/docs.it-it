---
title: Direttiva x:Key
ms.date: 03/30/2017
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
ms.openlocfilehash: c05f98932ceceeb1530b34a09b1923f2af1378b5
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071500"
---
# <a name="xkey-directive"></a>Direttiva x:Key
Identifica in modo univoco gli elementi creati e a cui viene fatto riferimento in un dizionario definito da XAML. L'aggiunta di un `x:Key` valore a un elemento oggetto XAML è il modo più <xref:System.Windows.ResourceDictionary>comune per identificare una risorsa in un dizionario risorse, ad esempio in un WPFWPF .  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>Utilizzo degli attributi XAML (specifico di WPF)XAML Attribute Usage (WPF-specific)  
  
```xaml  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`stringKeyValue`|Stringa di testo da utilizzare come chiave. La stringa di testo deve essere conforme alla grammatica [XamlName](xamlname-grammar.md).|  
|`markupExtensionUsage`|All'interno dei delimitatori {}dell'estensione di markup, un utilizzo dell'estensione di markup che fornisce un oggetto da utilizzare come chiave. Vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Osservazioni  
 `x:Key`supporta il concetto di dizionario risorse XAML. XAML come linguaggio non definisce un'implementazione del dizionario risorse, che viene lasciata a framework dell'interfaccia utente specifici. Per altre informazioni sull'implementazione dei dizionari risorse XAML in WPFWPF, vedere [Risorse XAML](../fundamentals/xaml-resources-define.md).  
  
 In XAML 2006 `x:Key` e WPFWPF, deve essere fornito come attributo. È comunque possibile usare chiavi non stringa, ma ciò richiede un utilizzo dell'estensione di markup per fornire il valore non stringa nel formato di attributo. Se si usa XAML 2009, `x:Key` può essere specificato come elemento, per supportare in modo esplicito i dizionari con chiave da tipi di oggetto diversi dalle stringhe senza richiedere un'estensione di markup intermedia. Vedere la sezione "XAML 2009" in questo argomento. Il resto della sezione Osservazioni si applica specificamente all'implementazione xaml 2006.  
  
 Il valore `x:Key` dell'attributo di può essere qualsiasi stringa definita nella [grammatica XamlName](xamlname-grammar.md) o può essere un oggetto valutato tramite un'estensione di markup. Vedere "Note sull'utilizzo di WPF" per un esempio da WPFWPF.  
  
 Gli elementi figlio di un <xref:System.Collections.IDictionary> elemento padre `x:Key` che è un'implementazione devono in genere includere un attributo che specifica un valore di chiave univoco all'interno di tale dizionario. I framework potrebbero implementare proprietà `x:Key` chiave con alias per sostituire in tipi specifici. i tipi che definiscono tali <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>proprietà devono essere attribuiti con .  
  
 L'equivalente del `x:Key` codice specificato è la chiave <xref:System.Collections.IDictionary>utilizzata per l'oggetto sottostante. Ad esempio, `x:Key` un oggetto che viene applicato nel markup per `key` una <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> risorsa in WPFWPF equivale <xref:System.Windows.ResourceDictionary> al valore del parametro di quando si aggiunge la risorsa a un WPFWPF nel codice.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
 Gli oggetti figlio di un <xref:System.Collections.IDictionary> oggetto padre che <xref:System.Windows.ResourceDictionary>è un'implementazione, ad esempio WPF , devono in genere includere un `x:Key` attributo e il valore della chiave deve essere univoco all'interno di tale dizionario. Ci sono due eccezioni degne di nota:  
  
- Alcuni tipi WPFWPF dichiarano una chiave implicita per l'utilizzo del dizionario. Ad esempio, <xref:System.Windows.Style> un <xref:System.Windows.Style.TargetType%2A>con <xref:System.Windows.DataTemplate> un <xref:System.Windows.DataTemplate.DataType%2A>oggetto , o <xref:System.Windows.ResourceDictionary> un con un oggetto , può trovarsi in a e utilizzare la chiave implicita.  
  
- WPFWPF supporta un concetto di dizionario risorse unito. Le chiavi possono essere condivise tra i dizionari uniti <xref:System.Windows.FrameworkContentElement.FindResource%2A>ed è possibile accedere al comportamento della chiave condivisa utilizzando . Per altre informazioni, vedere [Dizionari risorse uniti](../../framework/wpf/advanced/merged-resource-dictionaries.md).  
  
 Nell'implementazione XAML WPF complessiva e nel modello di applicazione, l'univocità della chiave non viene controllata dal compilatore di markup XAML. Al contrario, `x:Key` i valori mancanti o non univoci causano errori del parser XAML in fase di caricamento. Tuttavia, la gestione dei dizionari per WPF di Visual Studio può spesso notare tali errori nella fase di progettazione.  
  
 Si noti che nella <xref:System.Windows.ResourceDictionary> sintassi illustrata, l'oggetto è implicito nel modo in cui il processore XAML WPF produce una raccolta per popolare una <xref:System.Windows.FrameworkElement.Resources%2A> raccolta. Un <xref:System.Windows.ResourceDictionary> oggetto non viene in genere fornito in modo esplicito come elemento nel markup, anche se <xref:System.Windows.FrameworkElement.Resources%2A> può essere in alcuni casi se desiderato per chiarezza (sarebbe un elemento oggetto raccolta tra l'elemento proprietà e gli elementi all'interno che popolano il dizionario). Per informazioni sul motivo per cui un oggetto raccolta è quasi sempre un elemento implicito nel markup, vedere [Sintassi XAML in dettaglio](../../framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 Nell'implementazione XAML WPFWPF, la gestione delle <xref:System.Windows.ResourceKey> chiavi del dizionario risorse è definita dalla classe astratta. Tuttavia, il processore XAML WPF produce diversi tipi di estensione sottostanti per le chiavi in base ai relativi utilizzi. Ad esempio, la <xref:System.Windows.DataTemplate> chiave per una o qualsiasi classe derivata viene gestita separatamente e produce un oggetto distinto. <xref:System.Windows.DataTemplateKey>  
  
 Chiavi e nomi utilizzano direttive`x:Key` ed `x:Name`elementi del linguaggio diversi ( versu ) nella definizione XAML di base. Chiavi e nomi vengono utilizzati anche in diverse situazioni dalla definizione WPFWPF e l'applicazione di questi concetti. Per informazioni dettagliate, vedere Ambiti dei nomi [XAML WPF](../../framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 Come indicato in precedenza, il valore di una chiave può essere fornito tramite un'estensione di markup e può essere diverso da un valore stringa. Uno scenario WPF di esempio `x:Key` è che il valore di may essere un [ComponentResourceKey](../../framework/wpf/advanced/componentresourcekey-markup-extension.md). Alcuni controlli espongono una chiave di stile di quel tipo per una risorsa di stile personalizzata che influenza parte dell'aspetto e del comportamento di tale controllo senza sostituire completamente lo stile. Un esempio di tale <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>chiave è .  
  
 La funzionalità del dizionario unito WPFWPF introduce considerazioni aggiuntive per l'univocità della chiave e il comportamento di ricerca delle chiavi. Per altre informazioni, vedere [Dizionari risorse uniti](../../framework/wpf/advanced/merged-resource-dictionaries.md).  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 riduce la `x:Key` restrizione che viene sempre fornita nel modulo di attributo.  
  
 In WPF, è possibile utilizzare le funzionalità di XAML 2009, ma solo per XAML che non è compilato dal markup. Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.  
  
 In XAML 2009, `x:Key` è possibile specificare gli elementi tramite l'utilizzo seguente:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>Utilizzo degli elementi XAML (solo XAML 2009)  
  
```xaml  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`keyObject`|Elemento Object per l'oggetto utilizzato come `object` chiave per un determinato dizionario.|  
  
- Il contenitore/padre per questo tipo di utilizzo non è illustrato qui. `object`è previsto che sia un elemento figlio di un elemento oggetto che rappresenta un'implementazione specializzata del dizionario. `keyObject`ci si aspetta che sia un'istanza dell'oggetto (o un valore di un tipo di valore) appropriata come chiave per quella particolare implementazione del dizionario specializzato.  
  
- WPFWPF non implementa dizionari che richiedono questo utilizzo. Chiavi oggetto è più una funzionalità generale del linguaggio XAML, possibilmente utile per alcuni scenari di dizionario personalizzato in cui è auspicabile la creazione del dizionario in XAML. Per le funzionalità WPFWPF, ad esempio gli stili impliciti che usano chiavi non stringa per le risorse, esistono altre tecniche per stabilire o specificare le chiavi, pertanto l'uso di una chiave dell'oggetto non è necessario.  
  
- `keyObject`potrebbe anche essere un utilizzo dell'estensione di markup nel formato dell'elemento oggetto, anziché un'istanza diretta dell'oggetto.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight  
 `x:Key`per Silverlight è documentato separatamente. Per altre informazioni, vedere [Spazio dei nomi XAML (x:) Funzionalità del linguaggio (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>Vedere anche

- [Risorse XAML](../fundamentals/xaml-resources-define.md)
- [Risorse e codice](../../framework/wpf/advanced/resources-and-code.md)
- [Estensione del markup StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md)
