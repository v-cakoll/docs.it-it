---
title: Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
caps.latest.revision: "11"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 0b35c35be7351fdf45157153ce6ca55fc763c3ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework
Quando si definiscono i tipi personalizzati che sono oggetti business o tipi che non dispongono di una dipendenza su Framework specifici, esistono alcune procedure consigliate per XAML è possibile seguire. Se si seguono queste procedure, servizi XAML di .NET Framework e i relativi reader XAML e writer XAML possono individuare le caratteristiche XAML del tipo e assegnargli una rappresentazione appropriata in un flusso del nodo XAML tramite il sistema di tipi XAML. In questo argomento vengono descritte le procedure consigliate per le definizioni dei tipi, le definizioni dei membri e assegnazione di attributi CLR di tipi o membri.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Modelli di costruttore e definizioni di tipi per XAML  
 Per creare un'istanza come elemento oggetto in XAML, una classe personalizzata deve soddisfare i requisiti seguenti:  
  
-   La classe personalizzata deve essere pubblica e deve esporre un costruttore pubblico (senza parametri) predefinito. Per alcune note riguardanti le strutture, vedere la sezione seguente.  
  
-   La classe personalizzata non deve essere una classe annidata. "Punto" il nome completo di percorso aggiuntivo rende ambiguo la divisione di spazio dei nomi di classe e interferisce con altre funzionalità XAML, ad esempio le proprietà associate.  
  
 Se è possibile creare istanze di un oggetto come un elemento oggetto, l'oggetto creato può inserire la forma di elemento di proprietà di qualsiasi proprietà che accetta l'oggetto come tipo sottostante.  
  
 È comunque possibile fornire i valori dell'oggetto per i tipi che non soddisfano questi criteri, se si abilita un convertitore di valori. Per ulteriori informazioni, vedere [convertitori di tipi ed estensioni di Markup per XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
### <a name="structures"></a>Strutture  
 Le strutture sono sempre in grado di essere costruito in XAML, per definizione di CLR. Questo avviene perché un compilatore CLR crea in modo implicito un costruttore predefinito per una struttura. Questo costruttore inizializza tutti i valori di proprietà sui valori predefiniti.  
  
 In alcuni casi, il comportamento di costruzione predefinita per una struttura non è auspicabile. È possibile che la struttura deve compilare concettualmente come un'unione di valori e funzioni. Come un'unione, i valori contenuti potrebbero avere interpretazioni si escludono a vicenda e, pertanto, nessuna delle proprietà possono essere impostata. Un esempio di una struttura nel vocabolario WPF è <xref:System.Windows.GridLength>. Tali strutture devono implementare un convertitore di tipi in modo che i valori possono essere espressi in forma di attributo, utilizzando le convenzioni di stringa che creano le interpretazioni o modalità diverse di valori di struttura. La struttura deve anche esporre un comportamento simile per la costruzione del codice tramite un costruttore non predefinito.  
  
### <a name="interfaces"></a>Interfacce  
 Interfacce possono essere utilizzate come tipi sottostanti di membri. Sistema di tipi XAML controlla l'elenco può essere assegnato e non prevede che è possibile assegnare l'oggetto che viene fornito come valore per l'interfaccia. Non vi è alcun concetto di modalità di presentazione dell'interfaccia come tipo XAML come un tipo assegnabile pertinente supporti i requisiti di costruzione XAML.  
  
### <a name="factory-methods"></a>Metodi factory  
 Metodi factory sono una funzionalità di XAML 2009. Modificare il principio XAML che gli oggetti devono avere costruttori predefiniti. Metodi factory non sono documentati in questo argomento. Vedere [direttiva X:FactoryMethod](../../../docs/framework/xaml-services/x-factorymethod-directive.md).  
  
## <a name="enumerations"></a>Enumerazioni  
 Le enumerazioni dispongono di comportamento di conversione di tipo nativo di XAML. Nomi di costanti di enumerazione specificati in XAML vengono risolte rispetto al tipo di enumerazione sottostante e restituiscono il valore di enumerazione per un writer di oggetti XAML.  
  
 XAML supporta l'utilizzo dello stile flag per le enumerazioni con <xref:System.FlagsAttribute> applicato. Per ulteriori informazioni, vedere [sintassi di XAML In dettaglio](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md). ([Sintassi di XAML In dettaglio](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md) viene scritto per il pubblico WPF, ma la maggior parte delle informazioni in questo argomento è rilevante per il codice XAML non è specifico di un particolare framework di implementazione.)  
  
## <a name="member-definitions"></a>Definizioni dei membri  
 Tipi possono definire membri per l'utilizzo di XAML. È possibile che i tipi che definiscono i membri che possono essere utilizzati con XAML anche se il tipo specifico non è utilizzabile con XAML. Questo è possibile a causa di ereditarietà di CLR. Se un tipo che eredita il membro supporta l'utilizzo XAML come tipo e il membro supporta l'utilizzo della sintassi XAML per il relativo tipo sottostante o ha una sintassi XAML nativa, il membro è utilizzabile con XAML.  
  
### <a name="properties"></a>Proprietà  
 Se si definiscono proprietà come proprietà CLR pubblica utilizzando CLR tipico `get` e `set` modelli di funzione di accesso e parole chiave appropriata per la lingua, il sistema di tipi XAML può segnalare la proprietà come un membro con le informazioni appropriate previste <xref:System.Xaml.XamlMember> proprietà, ad esempio <xref:System.Xaml.XamlMember.IsReadPublic%2A> e <xref:System.Xaml.XamlMember.IsWritePublic%2A>.  
  
 Le proprietà specifiche possono abilitare una sintassi del testo applicando <xref:System.ComponentModel.TypeConverterAttribute>. Per ulteriori informazioni, vedere [convertitori di tipi ed estensioni di Markup per XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 In assenza di una sintassi del testo o di conversione XAML nativa e in assenza di ulteriore riferimento indiretto, ad esempio un utilizzo dell'estensione di markup, il tipo di una proprietà (<xref:System.Xaml.XamlMember.TargetType%2A> sistema di tipi in XAML) deve essere in grado di restituire un'istanza a un writer di oggetti XAML considerando t tipo di destinazione come tipo CLR.  
  
 Se l'utilizzo di XAML 2009, [estensione di Markup X:Reference](../../../docs/framework/xaml-services/x-reference-markup-extension.md) possono essere utilizzate per fornire i valori non vengono soddisfatte le considerazioni precedenti, tuttavia, che è più un problema di utilizzo di un problema di definizione del tipo di.  
  
### <a name="events"></a>Eventi  
 Se si definiscono gli eventi come un evento CLR pubblico, il sistema di tipi XAML può segnalare l'evento come un membro con <xref:System.Xaml.XamlMember.IsEvent%2A> come `true`. Cablaggio i gestori eventi non è nell'ambito di funzioni di servizi XAML di .NET Framework. questo viene lasciato alle implementazioni e framework specifici.  
  
### <a name="methods"></a>Metodi  
 Il codice inline per i metodi non è una funzionalità XAML predefinito. Nella maggior parte dei casi si non direttamente riferimento metodo membri da XAML e il ruolo di metodi in XAML è solo per fornire supporto per modelli XAML specifici. [Direttiva X:FactoryMethod](../../../docs/framework/xaml-services/x-factorymethod-directive.md) è un'eccezione.  
  
### <a name="fields"></a>Campi  
 Linee guida di progettazione CLR scoraggiano campi non statici. Per i campi statici, è possibile accedere a valori di campo statico solo tramite [estensione di Markup X:Static](../../../docs/framework/xaml-services/x-static-markup-extension.md); in questo caso non si sta eseguendo nulla nella definizione di CLR per esporre un campo per [X:Static](../../../docs/framework/xaml-services/x-static-markup-extension.md) utilizzi.  
  
## <a name="attachable-members"></a>Membri associabili  
 I membri associabili sono esposte in XAML tramite un modello di metodo di funzione di accesso su un tipo di definizione. Il tipo di definizione non è necessario essere utilizzabile per XAML come un oggetto. È in effetti un modello comune per dichiarare una classe del servizio il cui ruolo è proprietario membro associabile e implementare i comportamenti correlati, ma non servono alcuna altra funzione, ad esempio una rappresentazione dell'interfaccia utente. Per le sezioni seguenti, il segnaposto *PropertyName* rappresenta il nome del membro associabile. Tale nome deve essere valido nella [grammatica XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 Prestare attenzione a conflitti di nome tra questi modelli e altri metodi di un tipo. Se esiste un membro che corrisponde a uno dei modelli, questo può essere interpretato come un percorso di utilizzo del membro associabile da un processore XAML anche se non era l'intenzione.  
  
#### <a name="the-getpropertyname-accessor"></a>Funzione di accesso GetPropertyName  
 La firma per la funzione di accesso `Get`*NomeProprietà* deve essere:  
  
 `public static object Get` *PropertyName* `(object` `target` `)`  
  
-   L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. Ciò consente di definire l'ambito di utilizzo del membro associabile; gli utilizzi all'esterno dell'ambito previsto genereranno eccezioni di cast non valido che vengono quindi replicate da un errore di analisi XAML. Il nome del parametro `target` non è un requisito, ma è denominato `target` per convenzione nella maggior parte delle implementazioni.  
  
-   Il valore restituito può essere specificato come tipo più specifico nell'implementazione.  
  
 Per supportare un <xref:System.ComponentModel.TypeConverter> sintassi del testo abilitata per l'utilizzo dell'attributo del membro associabile, applicare <xref:System.ComponentModel.TypeConverterAttribute> per il `Get` *PropertyName* della funzione di accesso. L'applicazione per il `get` anziché il `set` può sembrare non intuitiva; tuttavia, questa convenzione può supportare il concetto di sola lettura e i membri associabili serializzabili, che è utile negli scenari di progettazione.  
  
#### <a name="the-setpropertyname-accessor"></a>La funzione di accesso SetPropertyName  
 La firma per il Set di*PropertyName* della funzione di accesso deve essere:  
  
 `public static void Set` *NomeProprietà* `(object` `target` `, object` `value` `)`  
  
-   Il `target` oggetto può essere specificato come un tipo più specifico nell'implementazione, con la stessa logica e conseguenze come descritto nella sezione precedente.  
  
-   L'oggetto `value` può essere specificato come tipo più specifico nell'implementazione.  
  
 Tenere presente che il valore di questo metodo è l'input proveniente dall'utilizzo in XAML, in genere in forma di attributo. Da una forma di attributo deve essere supporto del convertitore di tipi di valore per una sintassi del testo e attributo di `Get` *PropertyName* della funzione di accesso.  
  
### <a name="attachable-member-stores"></a>Archivi dei membri associabili  
 I metodi della funzione di accesso non sono in genere sufficiente per fornire un modo per inserire i valori del membro associabile in un oggetto grafico, o per recuperare i valori non compresi nell'oggetto grafico e serializzarli nel modo appropriato. Per fornire questa funzionalità, il `target` gli oggetti nelle firme della funzione di accesso precedente devono essere in grado di archiviare i valori. Il meccanismo di archiviazione deve essere coerenza con il principio del membro associabile che il membro è associabile a destinazioni in cui il membro associabile non è nell'elenco dei membri. Servizi XAML di .NET framework fornisce una tecnica di implementazione per il membro collegabile archivia tramite le API <xref:System.Xaml.IAttachedPropertyStore> e <xref:System.Xaml.AttachablePropertyServices>. <xref:System.Xaml.IAttachedPropertyStore>viene utilizzato dai writer XAML per individuare l'implementazione dell'archivio e deve essere implementata nel tipo che è la `target` delle funzioni di accesso. Il metodo statico <xref:System.Xaml.AttachablePropertyServices> API vengono utilizzate all'interno del corpo delle funzioni di accesso e fare riferimento al membro associabile dal relativo <xref:System.Xaml.AttachableMemberIdentifier>.  
  
## <a name="xaml-related-clr-attributes"></a>Attributi CLR correlati a XAML  
 Assegnazione di attributi correttamente i tipi, membri e gli assembly è importante ai report di informazioni sul sistema di tipi XAML ai servizi XAML di .NET Framework. È rilevante se si prevede di utilizzare con i sistemi XAML direttamente basate su XAML dei servizi XAML di .NET Framework reader e writer XAML i tipi, o se si definiscono o utilizza un framework che utilizzano XAML basato su tali reader XAML e writer XAML.  
  
 Per un elenco di ogni attributo correlati a XAML che sono rilevante per il supporto XAML dei tipi personalizzati, vedere [Related di attributi CLR per tipi personalizzati e le librerie](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="usage"></a>Utilizzo  
 Utilizzo di tipi personalizzati è necessario che l'autore del markup deve eseguire il mapping di un prefisso per l'assembly e spazio dei nomi CLR che contengono il tipo personalizzato. Questa procedura non è documentata in questo argomento.  
  
## <a name="access-level"></a>Livello di accesso  
 XAML consente di caricare e creare istanze di tipi che dispongono di un `internal` livello di accesso. Questa funzionalità viene fornita in modo che il codice utente possa definire tipi personalizzati e quindi creare un'istanza di tali classi dal codice che fa anche parte dello stesso ambito di codice utente.  
  
 Un esempio di WPF è ogni volta che il codice utente definisce un <xref:System.Windows.Controls.UserControl> inteso come un modo per effettuare il refactoring di un comportamento dell'interfaccia utente, ma non come parte di qualsiasi possibile meccanismo di estensione che potrebbe essere implicito dichiarando la classe di supporto con `public` livello di accesso. Questo tipo un <xref:System.Windows.Controls.UserControl> può essere dichiarato con `internal` accedere se il codice sottostante viene compilato nello stesso assembly da cui viene fatto riferimento come un tipo XAML.  
  
 Per un'applicazione che carica XAML con l'attendibilità totale e lo usa <xref:System.Xaml.XamlObjectWriter>, il caricamento delle classi con `internal` livello di accesso è sempre abilitato.  
  
 Per un'applicazione che carica XAML con attendibilità parziale, è possibile controllare le caratteristiche di livello di accesso tramite il <xref:System.Xaml.Permissions.XamlAccessLevel> API. Inoltre, devono essere in grado di propagare le autorizzazioni a livello di accesso e conservarle per le valutazioni della fase di esecuzione finale; i meccanismi di rinvio (ad esempio, il sistema di modelli WPF) Questa operazione viene gestita internamente passando il <xref:System.Xaml.Permissions.XamlAccessLevel> informazioni.  
  
### <a name="wpf-implementation"></a>Implementazione di WPF  
 XAML WPF viene utilizzato un modello di accesso parzialmente attendibile in cui se BAML viene caricato con attendibilità parziale, l'accesso è limitato a <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> per l'assembly che rappresenta l'origine BAML. Per rinvio, in WPF viene usato <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> come un meccanismo per passare le informazioni sul livello di accesso.  
  
 Nella terminologia di XAML di WPF, un *tipo interno* è un tipo definito dall'assembly stesso che include il codice XAML di riferimento. Tale tipo può essere mappato tramite uno spazio dei nomi XAML viene deliberatamente omesso assembly = parte di un mapping, ad esempio, `xmlns:local="clr-namespace:WPFApplication1"`.  Se BAML fa riferimento a un tipo interno e che disponga di tipo `internal` , livello di accesso verrà generato un `GeneratedInternalTypeHelper` classe per l'assembly. Se si desidera evitare `GeneratedInternalTypeHelper`, è necessario utilizzare `public` , livello di accesso necessario scomporre la classe rilevante in un assembly separato e rendere tale assembly dipendente.  
  
## <a name="see-also"></a>Vedere anche  
 [Attributi CLR correlati a XAML per tipi e librerie personalizzati](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)  
 [Servizi XAML](../../../docs/framework/xaml-services/index.md)
