---
title: Direttiva x:Class
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: 563802be655e0cb66c9a2735a64da9d7723c2a43
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401519"
---
# <a name="xclass-directive"></a>Direttiva x:Class
Configura la compilazione del markup XAML per unire classi parziali tra markup e code-behind. La classe parziale del codice è definita in un file di codice separato in un linguaggio Common Language Specification (CLS), mentre la classe parziale di markup viene in genere creata dalla generazione del codice durante la compilazione XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`namespace`|facoltativo. Specifica uno spazio dei nomi CLR che contiene la classe parziale `classname`identificata da. Se `namespace` si specifica, un punto (.) `namespace` separa e `classname`. Vedere la sezione Osservazioni.|  
|`classname`|Richiesto. Specifica il nome CLR della classe parziale che connette il codice XAML caricato e il code-behind per il codice XAML.|  
  
## <a name="dependencies"></a>Dipendenze  
 `x:Class`può essere specificato solo sull'elemento radice di una produzione XAML. `x:Class`non è valido per qualsiasi oggetto con un elemento padre nella produzione XAML. Per ulteriori informazioni, vedere [ \[la sezione MS\] -XAML 4.3.1.6](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Note  
 Il `namespace` valore può contenere punti aggiuntivi per organizzare gli spazi dei nomi correlati in gerarchie di nomi, una tecnica comune nella programmazione .NET Framework. Solo l'ultimo punto in una stringa di `x:Class` valori viene interpretato come separato `namespace` e `classname.` la classe usata come `x:Class` non può essere una classe annidata. Le classi annidate non sono consentite perché la determinazione `x:Class` del significato dei punti per le stringhe è ambigua se sono consentite classi annidate.  
  
 Nei modelli di programmazione esistenti che `x:Class`usano `x:Class` , è facoltativo nel senso che è interamente valido avere una pagina XAML senza code-behind. Questa funzionalità, tuttavia, interagisce con le azioni di compilazione implementate dai Framework che usano XAML. `x:Class`la funzionalità è influenzata anche dai ruoli che varie classificazioni del contenuto specificato in XAML hanno in un modello di applicazione e nelle azioni di compilazione corrispondenti. Se il codice XAML dichiara i valori degli attributi di gestione degli eventi o crea un'istanza di elementi personalizzati in cui le classi di definizione si trovano nella classe code- `x:Class` behind, è necessario fornire il riferimento alla direttiva (o [x:Subclass](x-subclass-directive.md)) alla classe appropriata per code-behind.  
  
 Il valore della `x:Class` direttiva deve essere una stringa che specifica il nome completo di una classe ma senza informazioni sull'assembly (equivalente <xref:System.Type.FullName%2A?displayProperty=nameWithType>a). Per le applicazioni semplici, è possibile omettere le informazioni sullo spazio dei nomi CLR se il code-behind è anche strutturato in questo modo (la definizione del codice inizia a livello di classe).  
  
 Il file code-behind per una definizione di pagina o di applicazione deve trovarsi all'interno di un file di codice incluso come parte del progetto che produce un'applicazione compilata e implica la compilazione del markup. È necessario seguire le regole dei nomi per le classi CLR. Per ulteriori informazioni, vedere [linee guida](../../standard/design-guidelines/index.md)per la progettazione di Framework. Per impostazione predefinita, la classe code-behind deve `public`essere. Tuttavia, è possibile definirla a un livello di accesso diverso usando la [direttiva x:ClassModifier](x-classmodifier-directive.md).  
  
 Questa interpretazione dell' `x:Class` attributo si applica solo a un'implementazione XAML basata su CLR, in particolare per .NET Framework servizi XAML. Altre implementazioni XAML che non sono basate su CLR e che non utilizzano .NET Framework servizi XAML potrebbero utilizzare una formula di risoluzione diversa per la connessione del markup XAML e il codice di run-time di backup. Per ulteriori informazioni sulle interpretazioni più generali di `x:Class`, vedere [ \[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
 A un certo livello di architettura, il significato di `x:Class` non è definito nei servizi XAML .NET Framework. Questo perché .NET Framework servizi XAML non specifica il modello di programmazione in base al quale sono connessi il markup XAML e il codice di supporto. Altri usi della direttiva `x:Class` potrebbero essere implementati da framework specifici che usano modelli di programmazione o modelli di applicazione per definire come connettere il markup XAML e il code-behind basato su CLR. Ogni Framework può avere proprie azioni di compilazione che abilitano parte del comportamento o componenti specifici che devono essere inclusi nell'ambiente di compilazione. All'interno di un Framework, le azioni di compilazione possono variare anche in base al linguaggio CLR specifico usato per il code-behind.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>x:Class nel modello di programmazione WPF  
 Nelle applicazioni WPF e nel modello di applicazione WPF `x:Class` , può essere dichiarato come attributo per qualsiasi elemento che rappresenta la radice di un file XAML e viene compilato (in cui il codice XAML è incluso in un progetto di applicazione `Page` WPF con azione di compilazione) o per il metodo C4 > <xref:System.Windows.Application>  radice nella definizione dell'applicazione di un'applicazione WPF compilata. La Dichiarazione `x:Class` di un elemento diverso da una radice di pagina o di un'applicazione o da un file XAML WPF non compilato causa un errore in fase di compilazione sotto il compilatore XAML WPF .NET Framework 3,0 e .NET Framework 3,5. Per informazioni su altri aspetti della `x:Class` gestione in WPF, vedere [code-behind e XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## <a name="xclass-for-windows-workflow-foundation"></a>x:Class per Windows Workflow Foundation  
 Per Windows Workflow Foundation, `x:Class` assegna un nome alla classe di un'attività personalizzata composta interamente in XAML o assegna un nome alla classe parziale della pagina XAML per un ActivityDesigner con code-behind.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight  
 `x:Class`per Silverlight è documentato separatamente. Per altre informazioni, vedere [spazio dei nomi XAML (x:) Funzionalità del linguaggio (Silverlight](https://go.microsoft.com/fwlink/?LinkId=199081)).  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Subclass](x-subclass-directive.md)
- [Classi XAML e personalizzate per WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Direttiva x:ClassModifier](x-classmodifier-directive.md)
- [Tipi migrati da WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
