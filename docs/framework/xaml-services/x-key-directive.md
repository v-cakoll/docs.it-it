---
title: Direttiva x:Key
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c73cf28905e1dd0f3056ab0eed953d6f05b0a7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xkey-directive"></a>Direttiva x:Key
Identifica in modo univoco gli elementi che vengono creati e a cui fa riferimento in un dizionario definite da XAML. Aggiunta di un `x:Key` valore da un elemento oggetto XAML è il modo più comune per identificare una risorsa in un dizionario risorse, ad esempio in un controllo WPF <xref:System.Windows.ResourceDictionary>.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>Utilizzo della sintassi XAML per gli attributi (specifico di WPF)  
  
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
|`stringKeyValue`|Una stringa di testo da utilizzare come chiave. La stringa di testo deve essere conforme al [grammatica XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md).|  
|`markupExtensionUsage`|All'interno di {} delimitatori di estensione di markup, un utilizzo dell'estensione di markup che fornisce un oggetto da utilizzare come chiave. Vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 `x:Key`supporta il concetto di dizionario risorse XAML. XAML come linguaggio non definisce un'implementazione di dizionario risorse, che è a sinistra i framework dell'interfaccia utente specifici. Per ulteriori informazioni sulla modalità di implementazione dei dizionari risorse XAML in WPF, vedere [risorse XAML](../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 In XAML 2006 e WPF, `x:Key` deve essere fornito come un attributo. È comunque possibile usare le chiavi, ma questo richiede un utilizzo dell'estensione di markup per fornire il valore non stringa in forma di attributo. Se si utilizza XAML 2009, `x:Key` può essere specificato come un elemento, per supportare in modo esplicito dizionari adattati dai tipi di oggetto diverso da stringhe senza richiedere un'estensione di markup intermedia. Vedere la sezione "XAML 2009" in questo argomento. Il resto della sezione Osservazioni si applica in particolare per l'implementazione XAML 2006.  
  
 Il valore dell'attributo `x:Key` può essere qualsiasi stringa definita nel [grammatica XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md) o può essere un oggetto valutato tramite un'estensione di markup. Per un esempio di WPF, vedere "Note sull'utilizzo di WPF".  
  
 Gli elementi figlio di un elemento padre che è un <xref:System.Collections.IDictionary> implementazione in genere deve includere un `x:Key` attributo che specifica un valore di chiave univoco all'interno di tale dizionario. Framework potrebbero implementare le proprietà della chiave di alias da sostituire per `x:Key` su tipi particolari; i tipi che definiscono tali proprietà devono essere attribuiti con <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 L'equivalente della specifica codice `x:Key` è la chiave utilizzata per l'oggetto sottostante <xref:System.Collections.IDictionary>. Ad esempio, un `x:Key` applicato nel markup per una risorsa in WPF è equivalente al valore del `key` parametro di <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> quando si aggiunge la risorsa a un WPF <xref:System.Windows.ResourceDictionary> nel codice.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Gli oggetti figlio di un elemento padre dell'oggetto che rappresenta un <xref:System.Collections.IDictionary> implementazione, ad esempio WPF <xref:System.Windows.ResourceDictionary>, in genere è necessario includere un `x:Key` attributo e il valore della chiave deve essere univoco all'interno di tale dizionario. Esistono due eccezioni rilevanti:  
  
-   Alcuni tipi WPF dichiarano una chiave per l'utilizzo del implicita. Ad esempio, un <xref:System.Windows.Style> con un <xref:System.Windows.Style.TargetType%2A>, o un <xref:System.Windows.DataTemplate> con un <xref:System.Windows.DataTemplate.DataType%2A>, può essere un <xref:System.Windows.ResourceDictionary> e utilizzare la chiave implicita.  
  
-   WPF supporta un concetto di dizionario risorse sottoposti a merge. Le chiavi possono essere condivisi tra i dizionari uniti e il comportamento del tasto condiviso è possibile accedere tramite <xref:System.Windows.FrameworkContentElement.FindResource%2A>. Per altre informazioni, vedere [Dizionari risorse uniti](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).  
  
 Nel XAML WPF implementazione e applicazione modello generale, l'univocità della chiave non è selezionata per il compilatore di markup XAML. In alternativa, mancanti o non univoco `x:Key` valori causano errori del parser XAML in fase di caricamento. Tuttavia, [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] la gestione dei dizionari per WPF può spesso nota tali errori in fase di progettazione.  
  
 Si noti che nella sintassi, il <xref:System.Windows.ResourceDictionary> oggetto è implicita nel modo in cui il processore XAML di WPF produce una raccolta per popolare un <xref:System.Windows.FrameworkElement.Resources%2A> insieme. A <xref:System.Windows.ResourceDictionary> non viene in genere fornito in modo esplicito come un elemento nel markup, anche se può essere in alcuni casi, se si desidera per maggiore chiarezza (sarebbe un elemento dell'oggetto collection tra il <xref:System.Windows.FrameworkElement.Resources%2A> elemento proprietà e gli elementi all'interno di popolano il dizionario). Per informazioni sui motivi per cui un oggetto collection è quasi sempre un elemento implicito nel markup, vedere [sintassi di XAML In dettaglio](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 Nell'implementazione XAML di WPF, la gestione di chiavi del dizionario risorse è definita per la <xref:System.Windows.ResourceKey> classe astratta. Il processore XAML di WPF produce tuttavia diversi tipi di estensione sottostanti per le chiavi in base al relativo utilizzo. Ad esempio, la chiave per un <xref:System.Windows.DataTemplate> o qualsiasi classe derivata viene gestita separatamente e produce un distinct <xref:System.Windows.DataTemplateKey> oggetto.  
  
 Chiavi e nomi utilizzano direttive diverse e gli elementi del linguaggio (`x:Key` e `x:Name`) nella definizione XAML di base. Le chiavi e i nomi vengono utilizzati anche in situazioni diverse per la definizione di WPF e l'applicazione di questi concetti. Per informazioni dettagliate, vedere [NameScope XAML WPF](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 Come indicato in precedenza, il valore di una chiave può essere fornito tramite un'estensione di markup e può essere diverso da un valore stringa. Uno scenario di esempio WPF è che il valore di `x:Key` potrebbe essere un[ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md). Alcuni controlli espongono una chiave di stile di tale tipo per una risorsa di stile personalizzato che influisce sulla parte dell'aspetto e il comportamento del controllo senza sostituirne lo stile. Un esempio di questo tipo di chiave è <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.  
  
 La funzionalità di dizionario unito WPF implica ulteriori considerazioni per l'univocità della chiave e il comportamento di ricerca della chiave. Per altre informazioni, vedere [Dizionari risorse uniti](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 vengono ridotti i la restrizione che `x:Key` sempre essere specificato in forma di attributo.  
  
 In WPF, è possibile utilizzare le funzionalità di XAML 2009, ma solo per il codice XAML non compilato dal markup. Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.  
  
 In XAML 2009, è possibile specificare `x:Key` elementi tramite l'utilizzo seguente:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>Utilizzo dell'elemento XAML (solo XAML 2009)  
  
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
|`keyObject`|Elemento dell'oggetto per l'oggetto che viene utilizzato come chiave per un determinato `object` in un dizionario specializzato.|  
  
-   Il contenitore/padre per questo tipo di utilizzo non è stato illustrato qui. `object`è previsto un elemento figlio di un elemento oggetto che rappresenta un'implementazione di dizionario specializzato. `keyObject`è previsto che un'istanza dell'oggetto (o un valore di un tipo valore) appropriata come chiave per quel particolare specializzate implementazione del dizionario.  
  
-   WPF non implementa dizionari che richiedono questo utilizzo. Chiavi dell'oggetto è una funzionalità generale del linguaggio XAML, utile per determinati scenari di dizionario personalizzato in cui è consigliabile la creazione del dizionario in XAML. Per le funzionalità WPF, ad esempio stili impliciti che utilizzano le chiavi non di tipo stringa per le risorse, altre tecniche per stabilire o specificare che le chiavi esistono, pertanto l'utilizzo di una chiave dell'oggetto non è necessario.  
  
-   *keyObject* potrebbe anche essere un utilizzo dell'estensione di markup in forma di elemento oggetto, anziché un'istanza dell'oggetto diretta.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight  
 `x:Key`per Silverlight è documentato separatamente. Per ulteriori informazioni, vedere [Namespace XAML (x) Funzionalità del linguaggio (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vedere anche  
 [Risorse XAML](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Risorse e codice](../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [Estensione di markup StaticResource](../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)
