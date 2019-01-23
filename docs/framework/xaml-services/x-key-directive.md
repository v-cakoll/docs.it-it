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
ms.openlocfilehash: 23c483daed0156dd29134b255e9da2f7922980ba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492782"
---
# <a name="xkey-directive"></a>Direttiva x:Key
Identifica in modo univoco gli elementi che vengono creati e a cui fa riferimento un dizionario definito XAML. Aggiunta di un `x:Key` valore da un elemento oggetto XAML è il modo più comune per identificare una risorsa in un dizionario risorse, ad esempio in un controllo WPF <xref:System.Windows.ResourceDictionary>.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>Utilizzo degli attributi XAML (specifico per WPF)  
  
```  
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
|`stringKeyValue`|Una stringa di testo da utilizzare come chiave. La stringa di testo deve essere conforme per il [grammatica XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md).|  
|`markupExtensionUsage`|All'interno dei delimitatori di estensione di markup {}, un utilizzo dell'estensione di markup che fornisce un oggetto da utilizzare come chiave. Vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 `x:Key` supporta il concetto di dizionario risorse XAML. XAML come linguaggio non definisce un'implementazione di dizionario risorse, ciò è lasciata a Framework specifici dell'interfaccia utente. Per altre informazioni su come vengono implementati i dizionari risorse XAML in WPF, vedere [risorse XAML](../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 In XAML 2006 e WPF, `x:Key` deve essere fornito come un attributo. È comunque possibile usare le chiavi, ma ciò richiede un utilizzo dell'estensione di markup per fornire il valore non stringa in forma di attributo. Se si utilizza XAML 2009, `x:Key` può essere specificato come un elemento, per supportare in modo esplicito dizionari adattati dai tipi di oggetti diversi da stringhe senza richiedere un'estensione di markup intermedia. Vedere la sezione "XAML 2009" in questo argomento. Il resto della sezione Osservazioni si applica in modo specifico per l'implementazione XAML 2006.  
  
 Il valore dell'attributo `x:Key` può essere qualsiasi stringa definita nella [grammatica XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md) o può essere un oggetto valutato tramite un'estensione di markup. Per un esempio di WPF, vedere "Note di utilizzo WPF".  
  
 Elementi figlio di un elemento padre che è un' <xref:System.Collections.IDictionary> implementazione deve in genere includere un `x:Key` attributo che specifica un valore di chiave univoco in tale dizionario. I framework potrebbero implementare le proprietà della chiave di alias per sostituire `x:Key` sui particolari tipi; tipi che definiscono proprietà quali dovrebbero essere attribuiti con <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 L'equivalente della specifica codice `x:Key` è la chiave utilizzata per l'oggetto sottostante <xref:System.Collections.IDictionary>. Ad esempio, un `x:Key` applicato nel markup per una risorsa in WPF è equivalente al valore della `key` parametro di <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> quando si aggiunge la risorsa a un WPF <xref:System.Windows.ResourceDictionary> nel codice.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Gli oggetti figlio di un elemento padre dell'oggetto che rappresenta un' <xref:System.Collections.IDictionary> implementazione, ad esempio l'applicazione WPF <xref:System.Windows.ResourceDictionary>, in genere necessario includere un `x:Key` attributo e il valore della chiave deve essere univoco in tale dizionario. Esistono due importanti eccezioni:  
  
-   Alcuni tipi WPF dichiarano una chiave implicita per l'utilizzo del dizionario. Ad esempio, un <xref:System.Windows.Style> con un <xref:System.Windows.Style.TargetType%2A>, o una <xref:System.Windows.DataTemplate> con un <xref:System.Windows.DataTemplate.DataType%2A>, possono trovarsi in un <xref:System.Windows.ResourceDictionary> e usare la chiave implicita.  
  
-   WPF supporta un concetto di dizionario risorse unito. Le chiavi possono essere condivisi tra i dizionari uniti e il comportamento principale condiviso è possibile accedere tramite <xref:System.Windows.FrameworkContentElement.FindResource%2A>. Per altre informazioni, vedere [Dizionari risorse uniti](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).  
  
 Nel WPF XAML implementazione e l'applicazione modello generale, l'univocità delle chiavi non viene controllata dal compilatore di markup XAML. Al contrario, mancanti o non univoci `x:Key` valori causano errori del parser XAML in fase di caricamento. Tuttavia, la gestione di Visual Studio di dizionari per WPF può spesso riscontrare tali errori in fase di progettazione.  
  
 Si noti che nella sintassi illustrata, la <xref:System.Windows.ResourceDictionary> oggetto è implicita nel modo in cui il processore XAML WPF produce una raccolta per popolare un <xref:System.Windows.FrameworkElement.Resources%2A> raccolta. Oggetto <xref:System.Windows.ResourceDictionary> non viene in genere fornito in modo esplicito come un elemento nel markup, benché ciò sia possibile in alcuni casi se si desidera per maggiore chiarezza (sarebbe un elemento dell'oggetto collection tra i <xref:System.Windows.FrameworkElement.Resources%2A> property (elemento) e gli elementi all'interno che popola la dizionario). Per informazioni sui motivi per cui un oggetto della raccolta è quasi sempre un elemento implicito nel markup, vedere [XAML descrizione dettagliata della sintassi](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 Nell'implementazione WPF XAML, la gestione di chiavi del dizionario risorse è definita dal <xref:System.Windows.ResourceKey> classe astratta. Tuttavia il processore XAML WPF produce diversi tipi di estensione sottostanti per le chiavi in base al loro utilizzo. Ad esempio, la chiave per un <xref:System.Windows.DataTemplate> o qualsiasi classe derivata viene gestita separatamente e produce un distinct <xref:System.Windows.DataTemplateKey> oggetto.  
  
 Chiavi e nomi utilizzano direttive diversi e gli elementi del linguaggio (`x:Key` rispetto a `x:Name`) nella definizione XAML di base. Le chiavi e i nomi vengono utilizzati anche in situazioni diverse dalla definizione WPF e dall'applicazione di questi concetti. Per informazioni dettagliate, vedere [NameScope XAML WPF](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 Come affermato in precedenza, il valore di una chiave può essere fornito tramite un'estensione di markup e può essere diverso da un valore di stringa. Un scenario WPF di esempio che è il valore della `x:Key` può essere un [ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md). Determinati controlli espongono una chiave di stile del tipo per una risorsa di stile personalizzata che influenza in parte l'aspetto e il comportamento del controllo senza sostituirne totalmente lo stile. Un esempio di questo tipo di chiave è <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.  
  
 Le funzionalità di dizionario unito WPF introducono considerazioni aggiuntive per l'univocità delle chiavi e il comportamento di ricerca della chiave. Per altre informazioni, vedere [Dizionari risorse uniti](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 rilassa la restrizione che `x:Key` venga fornito sempre in forma di attributo.  
  
 In WPF, è possibile usare le funzionalità di XAML 2009, ma solo per XAML non è compilato dal markup. Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.  
  
 In XAML 2009, è possibile specificare `x:Key` elementi tramite la sintassi seguente:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>Utilizzo di un elemento XAML (solo XAML 2009)  
  
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
|`keyObject`|Elemento dell'oggetto per l'oggetto che viene usato come chiave per un determinato `object` in un dizionario specializzato.|  
  
-   Il contenitore/elemento padre per questo tipo di utilizzo non è illustrato qui. `object` è previsto un elemento figlio di un elemento oggetto che rappresenta un'implementazione di dizionario specializzato. `keyObject` è previsto che sia un'istanza dell'oggetto (o un valore di un tipo valore) appropriata come chiave per quell'implementazione particolare del dizionario specializzato.  
  
-   WPF non implementa dizionari che richiedono questo utilizzo. Chiavi dell'oggetto è una funzionalità generale del linguaggio XAML, utile per determinati scenari di dizionario personalizzato in cui è consigliabile creare il dizionario in XAML. Per le funzionalità WPF quali stili impliciti che utilizzano chiavi non di tipo stringa per le risorse, altre tecniche per stabilire o specificare che le chiavi esistono, quindi usando una chiave dell'oggetto non è necessaria.  
  
-   *keyObject* potrebbe essere anche un utilizzo dell'estensione di markup in forma di elemento oggetto, anziché un'istanza dell'oggetto diretta.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight  
 `x:Key` per Silverlight è documentato separatamente. Per altre informazioni, vedere [XAML Namespace (x) Funzionalità del linguaggio (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vedere anche
- [Risorse XAML](../../../docs/framework/wpf/advanced/xaml-resources.md)
- [Risorse e codice](../../../docs/framework/wpf/advanced/resources-and-code.md)
- [Estensione di markup StaticResource](../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)
