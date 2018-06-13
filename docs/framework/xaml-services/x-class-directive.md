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
ms.openlocfilehash: 7e6a2379640d2556b553d14d20398a0a14931393
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566808"
---
# <a name="xclass-directive"></a>Direttiva x:Class
Consente di configurare la compilazione del markup XAML per l'aggiunta di classi parziali tra markup e code-behind. La classe parziale del codice è definita in un file di codice in un [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] language, mentre la classe parziale di markup viene in genere creata dalla generazione del codice durante la compilazione XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`namespace`|Facoltativo. Specifica un [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] dello spazio dei nomi che contiene la classe parziale identificata da `classname`. Se `namespace` è specificato, un punto (.) separa `namespace` e `classname`. Vedere la sezione Osservazioni.|  
|`classname`|Obbligatorio. Specifica il [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] nome della classe parziale che connette il codice XAML caricato e il code-behind per tale codice XAML.|  
  
## <a name="dependencies"></a>Dipendenze  
 `x:Class` può essere specificato solo per l'elemento radice di una produzione XAML. `x:Class` non è valido in qualsiasi oggetto che ha un padre per la produzione XAML. Per ulteriori informazioni, vedere [ \[MS-XAML\] sezione 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Note  
 Il `namespace` valore può contenere punti aggiuntivi per organizzare i relativi spazi dei nomi in gerarchie a nome, che è una tecnica comune nella programmazione .NET Framework. Solo l'ultimo punto in una stringa di `x:Class` valori viene interpretato per separare `namespace` e `classname.` la classe che viene utilizzata come `x:Class` non può essere una classe annidata. Classi annidate non sono consentite perché determinare il significato di punti per `x:Class` stringhe è ambiguo se sono consentite classi annidate.  
  
 Programmazione di modelli che utilizzano esistente `x:Class`, `x:Class` è facoltativo nel senso che è completamente valido a una pagina XAML che non dispone di alcun code-behind. Tuttavia, tale funzionalità interagisce con le operazioni di compilazione come implementato dalla Framework che usano XAML. `x:Class` funzionalità varia inoltre i ruoli che le varie classificazioni del contenuto XAML specificato in un modello dell'applicazione e nel corrispondente azioni di compilazione. Se il codice XAML dichiara valori di attributo di gestione degli eventi o crea gli elementi personalizzati in cui sono presenti classi di definizione nella classe code-behind, è necessario fornire il `x:Class` di riferimento (o [X:Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)) per il classe appropriata per il code-behind.  
  
 Il valore della `x:Class` direttiva deve essere una stringa che specifica il nome completo di una classe, ma senza informazioni sull'assembly (equivalente al <xref:System.Type.FullName%2A?displayProperty=nameWithType>). Per applicazioni semplici, è possibile omettere le informazioni dello spazio dei nomi CLR se il code-behind è strutturato anche in quel modo (definizione del codice inizia a livello di classe).  
  
 Il file code-behind per una definizione di un'applicazione o pagina deve essere all'interno di un file di codice che è incluso come parte del progetto che produce un'applicazione compilata e comporta la compilazione del markup. È necessario attenersi alle regole per le classi CLR. Per ulteriori informazioni, vedere [linee guida](../../../docs/standard/design-guidelines/index.md). Per impostazione predefinita, la classe code-behind deve essere `public`; tuttavia, è possibile definire un livello di accesso diverso utilizzando il [direttiva X:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
 L'interpretazione del `x:Class` attributo si applica solo a un'implementazione XAML basato su CLR, in particolare ai servizi XAML di .NET Framework. Altre implementazioni XAML che non si basano su CLR e che non utilizzano servizi XAML di .NET Framework potrebbero utilizzare una formula di una risoluzione diversa per la connessione al markup XAML e il backup di codice in fase di esecuzione. Per ulteriori informazioni su interpretazioni più generali di `x:Class`, vedere [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 Un determinato livello di architettura, il significato di `x:Class` non è definita nei servizi XAML di .NET Framework. Questo avviene perché i servizi XAML di .NET Framework non specifica il modello di programmazione mediante XAML markup e il codice di supporto sono connessi. Altri usi del `x:Class` direttiva può essere implementata da framework specifici che utilizzano modelli di programmazione o applicazione per definire come connettere markup XAML e codice basato su CLR. Ogni framework può disporre di operazioni di compilazione che abilitano alcuni il comportamento o componenti specifici che devono essere inclusi nell'ambiente di compilazione. All'interno di un framework di azioni di compilazione possono inoltre variare a seconda del linguaggio CLR specifico utilizzato per il code-behind.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>X:Class nel modello di programmazione WPF  
 Nelle applicazioni WPF e il modello applicazione WPF, `x:Class` può essere dichiarato come un attributo per qualsiasi elemento che è la radice di un file XAML e in fase di compilazione (in cui il codice XAML è inclusa in un progetto di applicazione WPF con `Page` azione di compilazione), o per il < C4 > <xref:System.Windows.Application>  radice nella definizione di applicazione di un'applicazione WPF compilata. Dichiarazione di `x:Class` su un elemento diverso da una radice della pagina o la radice dell'applicazione, oppure in un file XAML di WPF che non è compilato, provoca un errore in fase di compilazione di [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] e [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] compilatore XAML WPF. Per informazioni su altri aspetti del `x:Class` gestisce in WPF, vedere [Code-Behind e XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## <a name="xclass-for-windows-workflow-foundation"></a>x: Class per Windows Workflow Foundation  
 Per Windows Workflow Foundation, `x:Class` nome della classe di un'attività personalizzata costituita interamente in XAML o i nomi di classe parziale della pagina XAML per ActivityDesigner con code-behind.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight  
 `x:Class` per Silverlight è documentato separatamente. Per ulteriori informazioni, vedere [Namespace XAML (x) Funzionalità del linguaggio (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vedere anche  
 [Direttiva x:Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)  
 [Classi XAML e personalizzate per WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [Direttiva x:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md)  
 [Tipi migrati da WPF a System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
