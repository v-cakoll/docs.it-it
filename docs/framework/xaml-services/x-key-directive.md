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
ms.openlocfilehash: 4ffd7a2922c7f3ba35ccb9ac7ce29a6a00cd99af
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837207"
---
# <a name="xkey-directive"></a>Direttiva x:Key
Identifica in modo univoco gli elementi creati a cui viene fatto riferimento in un dizionario definito in XAML. L'aggiunta di un valore `x:Key` a un elemento oggetto XAML è il metodo più comune per identificare una risorsa in un dizionario risorse, ad esempio in <xref:System.Windows.ResourceDictionary>WPF.  
  
## <a name="xaml-attribute-usage"></a>Utilizzo della sintassi XAML per attributi  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>Utilizzo degli attributi XAML (specifico per WPF)  
  
```xaml  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a>Valor XAML  
  
|||  
|-|-|  
|`stringKeyValue`|Stringa da utilizzare come chiave. La stringa di testo deve essere conforme alla [Grammatica XamlName](xamlname-grammar.md).|  
|`markupExtensionUsage`|All'interno dei delimitatori dell'estensione di markup {}, un utilizzo dell'estensione di markup che fornisce un oggetto da usare come chiave. Vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 `x:Key` supporta il concetto di dizionario risorse XAML. XAML come linguaggio non definisce un'implementazione del dizionario risorse, ciò è lasciato a framework specifici dell'interfaccia utente. Per altre informazioni su come vengono implementati i dizionari risorse XAML in WPF, vedere [risorse XAML](../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 In XAML 2006 e WPF, `x:Key` necessario fornire come attributo. È possibile ancora utilizzare chiavi non di tipo stringa, ma questo richiede un utilizzo dell'estensione di markup per fornire il valore non di tipo stringa sotto forma d'attributo. Se si usa XAML 2009, `x:Key` possibile specificare come elemento, per supportare in modo esplicito i dizionari codificati da tipi di oggetto diversi dalle stringhe senza richiedere un'estensione di markup intermedia. Vedere la sezione "XAML 2009" in questo argomento. Il resto della sezione osservazioni si applica in modo specifico all'implementazione XAML 2006.  
  
 Il valore dell'attributo di `x:Key` può essere qualsiasi stringa definita nella [Grammatica XamlName](xamlname-grammar.md) oppure può essere un oggetto valutato tramite un'estensione di markup. Per avere un esempio, vedere in WPF "Note di utilizzo WPF".  
  
 Gli elementi figlio di un elemento padre che è un'implementazione di <xref:System.Collections.IDictionary> devono in genere includere un attributo `x:Key` che specifica un valore di chiave univoco in tale dizionario. I framework potrebbero implementare le proprietà della chiave con alias da sostituire per `x:Key` sui particolari tipi; tipi che definiscono ad esempio le proprietà che dovrebbero essere attribuite con <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 L'equivalente della specifica di `x:Key` nel codice è la chiave, così come viene utilizzata con l'oggetto <xref:System.Collections.IDictionary> sottostante. Ad esempio, `x:Key` applicato nel markup a una risorsa in WPF equivale al valore del parametro `key` di <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> quando si aggiunge la risorsa a un WPF <xref:System.Windows.ResourceDictionary> nel codice.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
 Gli oggetti figlio di un oggetto padre che è un'implementazione di <xref:System.Collections.IDictionary>, come ad esempio il <xref:System.Windows.ResourceDictionary> WPF, devono in genere includere un attributo `x:Key` e un valore di chiave univoco in tale dizionario. Esistono due importanti eccezioni:  
  
- Alcuni tipi WPF dichiarano una chiave implicita per l'utilizzo di dizionario. Ad esempio, un <xref:System.Windows.Style> con un <xref:System.Windows.Style.TargetType%2A> o un <xref:System.Windows.DataTemplate> con un <xref:System.Windows.DataTemplate.DataType%2A>, può essere presente in un <xref:System.Windows.ResourceDictionary> ed utilizzare la chiave implicita.  
  
- WPF supporta un concetto di dizionario delle risorse unito. Le chiavi possono essere condivise tra i dizionari uniti e l'accesso al comportamento principale condiviso può essere eseguito utilizzando <xref:System.Windows.FrameworkContentElement.FindResource%2A>. Per altre informazioni, vedere [Dizionari risorse uniti](../wpf/advanced/merged-resource-dictionaries.md).  
  
 Nell'implementazione XAML WPF complessiva e nel modello dell'applicazione, l'univocità delle chiavi non è controllata dal compilatore del markup XAML. Invece, i valori `x:Key` mancanti e/o non univoci generano errori del parser XAML in fase di caricamento. Tuttavia, la gestione dei dizionari per WPF in Visual Studio può spesso rilevare tali errori nella fase di progettazione.  
  
 Si noti che nella sintassi illustrata l'oggetto <xref:System.Windows.ResourceDictionary> è implicito nel modo in cui il processore XAML WPF produce una raccolta per popolare una raccolta <xref:System.Windows.FrameworkElement.Resources%2A>. <xref:System.Windows.ResourceDictionary> non viene in genere fornito in modo esplicito come elemento nel markup, benché ciò sia possibile in alcuni casi se lo si ritiene opportuno per motivi di chiarezza (si tratterebbe di un elemento dell'oggetto Collection tra l'elemento di proprietà <xref:System.Windows.FrameworkElement.Resources%2A> e le voci al suo interno che compilano il dizionario). Per informazioni sui motivi per cui un oggetto Collection è quasi sempre un elemento implicito nel markup, vedere [in dettaglio la sintassi XAML](../wpf/advanced/xaml-syntax-in-detail.md).  
  
 Nell'implementazione WPF XAML, la gestione delle chiavi di dizionario risorse è definita dalla classe astratta <xref:System.Windows.ResourceKey>. Il processore XAML WPF, tuttavia, produce diversi tipi di estensione sottostanti per le chiavi in base al relativo utilizzo. Ad esempio, la chiave per <xref:System.Windows.DataTemplate> o per qualsiasi classi derivata viene gestita separatamente e produce un oggetto <xref:System.Windows.DataTemplateKey> distinto.  
  
 Chiavi e nomi utilizzano direttive ed elementi di linguaggio (`x:Key` contro `x:Name`) diversi nella definizione XAML di base. Chiavi e nomi sono utilizzati anche in situazioni diverse dalla definizione WPF e dall'applicazione di questi concetti. Per informazioni dettagliate, vedere [NAMESCOPE XAML WPF](../wpf/advanced/wpf-xaml-namescopes.md).  
  
 Come dichiarato precedentemente, il valore di una chiave può essere fornito tramite un'estensione di markup e può essere diverso da un valore stringa. Uno scenario WPF di esempio è che il valore di `x:Key` può essere un [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md). Determinati controlli espongono una chiave di stile del tipo per creare una risorsa di stile personalizzata che influenza in parte l'aspetto e il comportamento di tale controllo senza sostituirne totalmente lo stile. Un esempio di questo tipo di chiave è <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.  
  
 Le funzionalità del dizionario unito WPF introducono considerazioni aggiuntive riguardo all'univocità delle chiavi e al comportamento della ricerca della chiave. Per altre informazioni, vedere [Dizionari risorse uniti](../wpf/advanced/merged-resource-dictionaries.md).  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 attenua la restrizione che `x:Key` essere sempre specificata in forma di attributo.  
  
 In WPF è possibile usare le funzionalità XAML 2009, ma solo per il codice XAML non compilato dal markup. Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.  
  
 In XAML 2009 è possibile specificare `x:Key` elementi tramite l'utilizzo seguente:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>Utilizzo della sintassi XAML per gli elementi (solo XAML 2009)  
  
```xaml  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a>Valor XAML  
  
|||  
|-|-|  
|`keyObject`|L'elemento oggetto per l'oggetto utilizzato come chiave per un `object` specificato in un dizionario specializzato.|  
  
- Il contenitore/padre per questo tipo di utilizzo non viene visualizzato qui. E' previsto che `object` sia figlio di un elemento oggetto che rappresenta un'implementazione di dizionario specializzato. `keyObject` è previsto che sia un'istanza dell'oggetto (o un valore di un tipo di valore) che è appropriata come chiave per quella particolare implementazione del dizionario specializzato.  
  
- WPF non implementa dizionari che richiedono questo utilizzo. Gli oggetti utilizzati come chiavi sono una funzionalità generale del linguaggio XAML, utile per determinati scenari di dizionario personalizzato dove la creazione del dizionario in XAML è preferibile. Per le funzionalità WPF quali stili impliciti che utilizzano chiavi non di tipo stringa per le risorse, altre tecniche per stabilire o  specificare che le chiavi esistono, in modo che l'utilizzo di una chiave dell'oggetto non è necessario.  
  
- il valore di un *oggetto* può anche essere un utilizzo dell'estensione di markup nel form dell'elemento oggetto, anziché un'istanza dell'oggetto diretto.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight.  
 `x:Key` per Silverlight è documentato separatamente. Per altre informazioni, vedere [spazio dei nomi XAML (x:) Funzionalità del linguaggio (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>Vedere anche

- [Risorse XAML](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Risorse e codice](../wpf/advanced/resources-and-code.md)
- [Estensione di markup StaticResource](../wpf/advanced/staticresource-markup-extension.md)
