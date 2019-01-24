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
ms.openlocfilehash: 2913782d8179fb882f8e916ed25feafcb5740a3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690046"
---
# <a name="xclass-directive"></a>Direttiva x:Class
Configura la compilazione del markup XAML per creare un join classi parziali tra markup e code-behind. La classe parziale del codice è definita in un file di codice separato in un [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] language, mentre la classe parziale di markup viene in genere creata dalla generazione del codice durante la compilazione XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`namespace`|Facoltativo. Specifica un [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] dello spazio dei nomi che contiene la classe parziale identificata da `classname`. Se `namespace` viene specificato, un punto (.) separa `namespace` e `classname`. Vedere la sezione Osservazioni.|  
|`classname`|Obbligatorio. Specifica il [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] nome della classe parziale che si connette il caricamento XAML e il code-behind per tale XAML.|  
  
## <a name="dependencies"></a>Dipendenze  
 `x:Class` può essere specificato solo per l'elemento radice di una produzione XAML. `x:Class` non è valido in qualsiasi oggetto che ha un padre nella produzione XAML. Per altre informazioni, vedere [ \[MS-XAML\] sezione 4.3.1.6](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Note  
 Il `namespace` valore può contenere punti aggiuntivi per organizzare gli spazi dei nomi correlati in gerarchie di nome, che è una tecnica comune nella programmazione .NET Framework. Solo l'ultimo punto in una stringa di `x:Class` valori viene interpretato come per separare `namespace` e `classname.` della classe che viene usata come `x:Class` non può essere una classe annidata. Le classi annidate non sono consentite perché determinare il significato dei punti per `x:Class` stringhe è ambiguo se sono consentite le classi annidate.  
  
 Esistente di programmazione i modelli che utilizzano `x:Class`, `x:Class` è facoltativa nel senso che è sicuramente valido per avere una pagina XAML che non dispone di alcun code-behind. Tuttavia, tale funzionalità interagisce con le azioni di compilazione come implementato dalla Framework che usano XAML. `x:Class` la funzionalità è influenzata anche da ruoli che le varie classificazioni del contenuto XAML specificato in un modello di applicazione e nel corrispondente azioni di compilazione. Se il XAML dichiara i valori di attributo di gestione degli eventi o crea gli elementi personalizzati in cui sono presenti classi di definizione della classe code-behind, è necessario specificare il `x:Class` direttiva riferimento (o [X:Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)) per il classe appropriata per il code-behind.  
  
 Il valore della `x:Class` direttiva deve essere una stringa che specifica il nome completo di una classe, ma senza le informazioni di assembly (equivalente al <xref:System.Type.FullName%2A?displayProperty=nameWithType>). Per applicazioni semplici, è possibile omettere le informazioni dello spazio dei nomi CLR se il code-behind anche è strutturato in quel modo (definizione del codice inizia a livello di classe).  
  
 Il file code-behind per una definizione di pagina o l'applicazione deve essere all'interno di un file di codice che è incluso come parte del progetto che produce un'applicazione compilata e implica la compilazione del markup. È necessario seguire sulle regole di denominazione per le classi CLR. Per altre informazioni, vedere [linee guida di progettazione di Framework](../../../docs/standard/design-guidelines/index.md). Per impostazione predefinita, deve essere la classe code-behind `public`; tuttavia, è possibile definire un livello di accesso diversi usando il [direttiva X:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
 Questa interpretazione del `x:Class` attributo si applica solo a un'implementazione XAML basato su CLR, in particolare ai servizi XAML di .NET Framework. In altre implementazioni XAML che non si basano su CLR e che non usano servizi XAML di .NET Framework potrebbero usare una formula diversa risoluzione per la connessione di markup XAML e codice in fase di esecuzione di backup. Per altre informazioni più generali interpretazioni dei `x:Class`, vedere [ \[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
 In un certo livello di architettura, il significato di `x:Class` non è definito nei servizi XAML di .NET Framework. Questo avviene perché servizi XAML di .NET Framework non specifica il modello di programmazione mediante cui XAML markup e il codice di supporto sono connessi. Altri usi del `x:Class` direttiva può essere implementata da framework specifici che utilizzano modelli di programmazione o i modelli di applicazione per definire la modalità di connessione basati su CLR code-behind e markup XAML. Ogni framework può avere un proprio azioni di compilazione che consentono alcuni comportamento o componenti specifici che devono essere inclusi nell'ambiente di compilazione. All'interno di un framework, le azioni di compilazione anche possono variare a seconda del linguaggio specifico di CLR che viene usato per il code-behind.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>X:Class nel modello di programmazione WPF  
 Nelle applicazioni WPF e il modello applicazione WPF, `x:Class` può essere dichiarato come un attributo per qualsiasi elemento che è la radice di un file XAML ed è in fase di compilazione (in cui è incluso il XAML in un progetto di applicazione WPF con `Page` azione di compilazione), o per il < C4 > <xref:System.Windows.Application>  radice nella definizione di applicazione di un'applicazione WPF compilata. La dichiarazione `x:Class` su un elemento diverso da una radice della pagina o la directory radice dell'applicazione o in un file di WPF XAML non compilato, provoca un errore in fase di compilazione sotto la [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] e [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] compilatore XAML WPF. Per informazioni su altri aspetti della `x:Class` gestisce in WPF, vedere [Code-Behind e XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## <a name="xclass-for-windows-workflow-foundation"></a>X:Class per Windows Workflow Foundation  
 Per Windows Workflow Foundation, `x:Class` denomina la classe di un'attività personalizzata costituita interamente in XAML oppure nomi di classe parziale della pagina XAML per ActivityDesigner con code-behind.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight  
 `x:Class` per Silverlight è documentato separatamente. Per altre informazioni, vedere [XAML Namespace (x) Funzionalità del linguaggio (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vedere anche
- [Direttiva x:Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)
- [Classi XAML e personalizzate per WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Direttiva x:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md)
- [Tipi migrati da WPF a System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
