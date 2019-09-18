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
ms.openlocfilehash: eb9f9cc1dfdb802e340123d0d39e9c9ebaa457f0
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053755"
---
# <a name="xkey-directive"></a>Direttiva x:Key
Identifica in modo univoco gli elementi creati e a cui si fa riferimento in un dizionario definito da XAML. L'aggiunta `x:Key` di un valore a un elemento oggetto XAML è il modo più comune per identificare una risorsa in un dizionario risorse, ad esempio in <xref:System.Windows.ResourceDictionary>WPF.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>Utilizzo degli attributi XAML (specifico di WPF)  
  
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
|`stringKeyValue`|Stringa di testo da utilizzare come chiave. La stringa di testo deve essere conforme alla [Grammatica XamlName](xamlname-grammar.md).|  
|`markupExtensionUsage`|All'interno dei delimitatori {}dell'estensione di markup, un utilizzo dell'estensione di markup che fornisce un oggetto da usare come chiave. Vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 `x:Key`supporta il concetto del dizionario risorse XAML. XAML come linguaggio non definisce un'implementazione del dizionario risorse, che viene lasciata a Framework dell'interfaccia utente specifici. Per altre informazioni su come vengono implementati i dizionari risorse XAML in WPF, vedere [risorse XAML](../wpf/advanced/xaml-resources.md).  
  
 In XAML 2006 e WPF, `x:Key` è necessario fornire come attributo. È comunque possibile usare chiavi non di tipo stringa, ma questo richiede un utilizzo dell'estensione di markup per fornire il valore non stringa nella forma dell'attributo. Se si usa XAML 2009, `x:Key` può essere specificato come elemento, per supportare in modo esplicito i dizionari codificati da tipi di oggetto diversi dalle stringhe senza richiedere un'estensione di markup intermedia. Vedere la sezione "XAML 2009" in questo argomento. Il resto della sezione osservazioni si applica in modo specifico all'implementazione XAML 2006.  
  
 Il valore dell' `x:Key` attributo può essere qualsiasi stringa definita nella [Grammatica XamlName](xamlname-grammar.md) oppure può essere un oggetto valutato tramite un'estensione di markup. Per un esempio di WPF, vedere "Note sull'utilizzo di WPF".  
  
 Gli elementi figlio di un elemento padre che è <xref:System.Collections.IDictionary> un'implementazione di devono in `x:Key` genere includere un attributo che specifica un valore di chiave univoco all'interno di tale dizionario. I Framework possono implementare proprietà chiave con `x:Key` <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>alias per sostituire i tipi specifici. i tipi che definiscono tali proprietà devono essere attribuiti a.  
  
 Il codice equivalente a specificare `x:Key` è la chiave usata per l'oggetto sottostante. <xref:System.Collections.IDictionary> Ad esempio, un `x:Key` oggetto applicato al markup per una risorsa in WPF è equivalente al valore `key` del parametro di <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> quando si aggiunge la risorsa a un oggetto WPF <xref:System.Windows.ResourceDictionary> nel codice.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
 Gli oggetti figlio di un oggetto padre che è <xref:System.Collections.IDictionary> un'implementazione di, ad esempio <xref:System.Windows.ResourceDictionary>WPF, devono in genere `x:Key` includere un attributo e il valore della chiave deve essere univoco all'interno del dizionario. Esistono due eccezioni rilevanti:  
  
- Alcuni tipi WPF dichiarano una chiave implicita per l'utilizzo del dizionario. Ad esempio, un <xref:System.Windows.Style> oggetto con <xref:System.Windows.Style.TargetType%2A>un oggetto o <xref:System.Windows.DataTemplate> un oggetto <xref:System.Windows.DataTemplate.DataType%2A>con, può essere in <xref:System.Windows.ResourceDictionary> un oggetto e usare la chiave implicita.  
  
- WPF supporta un concetto di dizionario risorse Unito. Le chiavi possono essere condivise tra i dizionari uniti ed è possibile accedere al comportamento della chiave condivisa <xref:System.Windows.FrameworkContentElement.FindResource%2A>tramite. Per altre informazioni, vedere [Dizionari risorse uniti](../wpf/advanced/merged-resource-dictionaries.md).  
  
 Nell'implementazione XAML generale di WPF e nel modello applicativo, l'unicità della chiave non viene controllata dal compilatore di markup XAML. Al contrario, i valori mancanti `x:Key` o non univoci provocano errori del parser XAML in fase di caricamento. Tuttavia, la gestione dei dizionari per WPF in Visual Studio può spesso rilevare tali errori nella fase di progettazione.  
  
 Si noti che nella sintassi illustrata, <xref:System.Windows.ResourceDictionary> l'oggetto è implicito nel modo in cui il processore XAML WPF produce una <xref:System.Windows.FrameworkElement.Resources%2A> raccolta per popolare una raccolta. Un <xref:System.Windows.ResourceDictionary> oggetto non viene in genere fornito in modo esplicito come elemento nel markup, sebbene possa essere in alcuni casi se lo si desidera per maggiore chiarezza (si tratta di un <xref:System.Windows.FrameworkElement.Resources%2A> elemento oggetto della raccolta tra l'elemento Property e gli elementi all'interno di che popolano dizionario). Per informazioni sui motivi per cui un oggetto Collection è quasi sempre un elemento implicito nel markup, vedere [in dettaglio la sintassi XAML](../wpf/advanced/xaml-syntax-in-detail.md).  
  
 Nell'implementazione XAML di WPF, la gestione delle chiavi del dizionario risorse è definita dalla <xref:System.Windows.ResourceKey> classe astratta. Tuttavia, il processore XAML WPF produce tipi di estensione sottostanti diversi per le chiavi in base ai relativi utilizzi. Ad esempio, la chiave per una <xref:System.Windows.DataTemplate> classe o qualsiasi classe derivata viene gestita separatamente e produce un oggetto <xref:System.Windows.DataTemplateKey> distinto.  
  
 Le chiavi e i nomi utilizzano direttive e elementi di`x:Key` linguaggio `x:Name`diversi (rispetto a) nella definizione XAML di base. Le chiavi e i nomi vengono usati anche in situazioni diverse dalla definizione di WPF e dall'applicazione di questi concetti. Per informazioni dettagliate, vedere [NAMESCOPE XAML WPF](../wpf/advanced/wpf-xaml-namescopes.md).  
  
 Come indicato in precedenza, il valore di una chiave può essere fornito tramite un'estensione di markup e può essere diverso da un valore stringa. Uno scenario WPF di esempio è che il valore `x:Key` di può essere un [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md). Alcuni controlli espongono una chiave di stile di quel tipo per una risorsa di stile personalizzata che influenza parte dell'aspetto e del comportamento di tale controllo senza sostituire completamente lo stile. Un esempio di tale chiave è <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.  
  
 La funzionalità dizionario unito WPF introduce considerazioni aggiuntive per l'univocità delle chiavi e il comportamento di ricerca chiave. Per altre informazioni, vedere [Dizionari risorse uniti](../wpf/advanced/merged-resource-dictionaries.md).  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 attenua la restrizione che `x:Key` è sempre disponibile in forma di attributo.  
  
 In WPF è possibile usare le funzionalità XAML 2009, ma solo per il codice XAML non compilato dal markup. Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.  
  
 In XAML 2009 è possibile specificare `x:Key` gli elementi tramite l'utilizzo seguente:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>Utilizzo di elementi XAML (solo XAML 2009)  
  
```  
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
|`keyObject`|Elemento oggetto per l'oggetto usato come chiave per un dato `object` in un dizionario specializzato.|  
  
- Il contenitore/elemento padre per questo tipo di utilizzo non è riportato qui. `object`si prevede che sia un elemento figlio di un elemento oggetto che rappresenta un'implementazione del dizionario specializzata. `keyObject`si prevede che sia un'istanza dell'oggetto (o un valore di un tipo di valore) appropriato come chiave per quella specifica implementazione del dizionario speciale.  
  
- WPF non implementa i dizionari che richiedono questo utilizzo. Le chiavi oggetto sono una funzionalità generale del linguaggio XAML, probabilmente utile per alcuni scenari di dizionario personalizzati in cui la creazione del dizionario in XAML è auspicabile. Per le funzionalità WPF, ad esempio gli stili impliciti che usano chiavi non di tipo stringa per le risorse, altre tecniche per stabilire o specificare le chiavi esistono, pertanto l'uso di una chiave dell'oggetto non è necessario.  
  
- il valore di un *oggetto* può anche essere un utilizzo dell'estensione di markup nel form dell'elemento oggetto, anziché un'istanza dell'oggetto diretto.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight  
 `x:Key`per Silverlight è documentato separatamente. Per altre informazioni, vedere [spazio dei nomi XAML (x:) Funzionalità del linguaggio (Silverlight](https://go.microsoft.com/fwlink/?LinkId=199081)).  
  
## <a name="see-also"></a>Vedere anche

- [Risorse XAML](../wpf/advanced/xaml-resources.md)
- [Risorse e codice](../wpf/advanced/resources-and-code.md)
- [Estensione di markup StaticResource](../wpf/advanced/staticresource-markup-extension.md)
