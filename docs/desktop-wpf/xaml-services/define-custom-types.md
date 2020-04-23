---
title: Definizione di tipi personalizzati da usare con i servizi XAML .NET
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: ff7e4229450e801a6d618c5141efde8cdcbef03d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "82071857"
---
# <a name="define-custom-types-for-use-with-net-xaml-services"></a>Definire tipi personalizzati da usare con i servizi XAML di .NETDefine custom types for use with .NET XAML Services

Quando si definiscono tipi personalizzati che sono oggetti business o che non hanno una dipendenza da framework specifici, è possibile seguire alcune procedure consigliate per XAML. Se segui queste procedure, i servizi XAML .NET e i relativi reader XAML e writer XAML possono individuare le caratteristiche XAML del tipo e fornirgli una rappresentazione appropriata in un flusso del nodo XAML usando il sistema di tipi XAML. In questo argomento vengono descritte le procedure consigliate per le definizioni dei tipi, le definizioni dei membri e l'attribuzione CLR di tipi o membri.

## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Modelli di costruttore e definizioni dei tipi per XAMLConstructor Patterns and Type Definitions for XAML

Per creare un'istanza come elemento oggetto in XAML, una classe personalizzata deve soddisfare i requisiti seguenti:To be instantiated as an object element in XAML, a custom class must meet the following requirements:

- La classe personalizzata deve essere pubblica e deve esporre un costruttore pubblico senza parametri. Per alcune note riguardanti le strutture, vedere la sezione seguente.

- La classe personalizzata non deve essere una classe annidata. Il "punto" aggiuntivo nel percorso del nome completo rende ambigua la divisione dello spazio dei nomi della classe e interferisce con altre funzionalità XAML, ad esempio le proprietà associate.
Se è possibile creare un'istanza di un oggetto come elemento oggetto, l'oggetto creato può riempire la forma dell'elemento proprietà di tutte le proprietà che accettano l'oggetto come tipo sottostante.

È comunque possibile fornire valori di oggetto per i tipi che non soddisfano questi criteri, se si abilita un convertitore di valori. Per altre informazioni, vedere Convertitori di tipi ed Estensioni di [markup per XAML.](type-converters-and-markup-extensions.md)

### <a name="structures"></a>Strutture

Le strutture possono sempre essere costruite in XAML, in base alla definizione CLR. Ciò è dovuto al fatto che un compilatore CLR crea in modo implicito un costruttore senza parametri per una struttura. Questo costruttore inizializza tutti i valori di proprietà sui valori predefiniti.

In alcuni casi, il comportamento di costruzione predefinito per una struttura non è auspicabile. Ciò potrebbe essere dovuto al fatto che la struttura è destinata a riempire i valori e funzionare concettualmente come un'unione. Come unione, i valori contenuti potrebbero avere interpretazioni che si escludono a vicenda e pertanto nessuna delle relative proprietà è impostabile. Un esempio di tale struttura nel <xref:System.Windows.GridLength>vocabolario WPFWPF è . Tali strutture devono implementare un convertitore di tipi in modo che i valori possano essere espressi in forma di attributo, utilizzando convenzioni di stringa che creano le diverse interpretazioni o modalità dei valori della struttura. La struttura deve inoltre esporre un comportamento simile per la costruzione del codice tramite un costruttore senza parametri.

### <a name="interfaces"></a>Interfacce

Le interfacce possono essere utilizzate come tipi sottostanti di membri. Il sistema di tipi XAML controlla l'elenco assegnabile e prevede che l'oggetto fornito come valore possa essere assegnato all'interfaccia. Non esiste alcun concetto di come l'interfaccia deve essere presentata come un tipo XAML, purché un tipo assegnabile pertinente supporti i requisiti di costruzione XAML.

### <a name="factory-methods"></a>Metodi Factory

I metodi factory sono una funzionalità xaml 2009. Modificano il principio XAML secondo cui gli oggetti devono avere costruttori senza parametri. I metodi factory non sono documentati in questo articolo. Vedere [direttiva x:FactoryMethod](xfactorymethod-directive.md).

## <a name="enumerations"></a>Enumerazioni

Le enumerazioni hanno il comportamento di conversione dei tipi nativi XAML. I nomi delle costanti di enumerazione specificati in XAML vengono risolti in base al tipo di enumerazione sottostante e restituiscono il valore di enumerazione a un writer di oggetti XAML.

XAML supporta un utilizzo di stile <xref:System.FlagsAttribute> flag per le enumerazioni con applicato. Per ulteriori informazioni, vedere [Sintassi XAML in dettaglio](../../framework/wpf/advanced/xaml-syntax-in-detail.md). [(Sintassi XAML in dettaglio](../../framework/wpf/advanced/xaml-syntax-in-detail.md) è scritto per il pubblico WPFWPF, ma la maggior parte delle informazioni in tale argomento è rilevante per XAML che non è specifico di un particolare framework di implementazione.)

## <a name="member-definitions"></a>Definizioni dei membri

I tipi possono definire membri per l'utilizzo di XAML. È possibile che i tipi definiscano membri che sono utilizzabili in XAML anche se quel tipo specifico non è utilizzabile con XAML. Ciò è possibile a causa dell'ereditarietà CLR. Finché un tipo che eredita il membro supporta l'utilizzo di XAML come tipo e il membro supporta l'utilizzo di XAML per il tipo sottostante o ha una sintassi XAML nativa disponibile, tale membro è utilizzabile in XAML.

### <a name="properties"></a>Proprietà

Se si definiscono le proprietà come `get` proprietà `set` CLR pubblica utilizzando i modelli CLR tipici e i modelli di funzione <xref:System.Xaml.XamlMember> di accesso <xref:System.Xaml.XamlMember.IsReadPublic%2A> e <xref:System.Xaml.XamlMember.IsWritePublic%2A>le parole chiave appropriate per il linguaggio, il sistema di tipi XAML può segnalare la proprietà come membro con le informazioni appropriate fornite per le proprietà, ad esempio e .

Proprietà specifiche possono abilitare una <xref:System.ComponentModel.TypeConverterAttribute>sintassi di testo applicando . Per altre informazioni, vedere Convertitori di tipi ed Estensioni di [markup per XAML.](type-converters-and-markup-extensions.md)

In assenza di una sintassi di testo o di una conversione XAML nativa e in<xref:System.Xaml.XamlMember.TargetType%2A> assenza di ulteriori direzioni indiretti, ad esempio l'utilizzo di un'estensione di markup, il tipo di una proprietà (nel sistema di tipi XAML) deve essere in grado di restituire un'istanza a un writer di oggetti XAML trattando il tipo di destinazione come un tipo CLR.

Se si usa XAML 2009, [x:Reference Markup Extension](xreference-markup-extension.md) può essere usato per fornire valori se le considerazioni precedenti non vengono soddisfatte; Tuttavia, si tratta di un problema di utilizzo maggiore rispetto a un problema di definizione del tipo.

### <a name="events"></a>Events

Se si definiscono eventi come evento CLR pubblico, il sistema <xref:System.Xaml.XamlMember.IsEvent%2A> di `true`tipi XAML può segnalare l'evento come membro con as . Il cablaggio dei gestori eventi non rientra nell'ambito delle funzionalità dei servizi XAML di .NET. cablaggio è lasciato a quadri e implementazioni specifici.

### <a name="methods"></a>Metodi

Il codice inline per i metodi non è una funzionalità XAML predefinita. Nella maggior parte dei casi, non fai riferimento direttamente ai membri del metodo da XAML e il ruolo dei metodi in XAML è solo quello di fornire il supporto per modelli XAML specifici. [La direttiva x:FactoryMethod](xfactorymethod-directive.md) è un'eccezione.X:FactoryMethod Directive is an exception.

### <a name="fields"></a>Campi

Le linee guida di progettazione CLR scoraggiano i campi non statici. Per i campi statici, è possibile accedere ai valori dei campi statici solo tramite [x:Static Markup Extension](xstatic-markup-extension.md); in questo caso non si esegue alcuna operazione speciale nella definizione CLR per esporre un campo per gli utilizzi [x:Static.](xstatic-markup-extension.md)

## <a name="attachable-members"></a>Membri associabili

I membri associabili vengono esposti a XAML tramite un modello di metodo della funzione di accesso in un tipo di definizione. Non è necessario che il tipo di definizione stesso sia utilizzabile in XAML come oggetto. Infatti, un modello comune consiste nel dichiarare una classe di servizio il cui ruolo è quello di possedere il membro associabile e implementare i comportamenti correlati, ma non servono altre funzioni, ad esempio una rappresentazione dell'interfaccia utente. Per le sezioni seguenti, il segnaposto *PropertyName* rappresenta il nome del membro associabile. Tale nome deve essere valido nella grammatica [XamlName](xamlname-grammar.md).

Prestare attenzione alle collisioni di nomi tra questi modelli e altri metodi di un tipo. Se esiste un membro che corrisponde a uno dei modelli, può essere interpretato come un percorso di utilizzo del membro associabile da un processore XAML anche se questo non era l'intenzione.

#### <a name="the-getpropertyname-accessor"></a>La funzione di accesso GetPropertyNameThe GetPropertyName Accessor

La firma `GetPropertyName` per la funzione di accesso deve essere:

`public static object GetPropertyName(object target)`

- L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. È possibile utilizzare questo per definire l'ambito dell'utilizzo del membro associabile; Gli utilizzi al di fuori dell'ambito previsto genereranno eccezioni di cast non valide che vengono quindi rilevate da un errore di analisi XAML. Il nome `target` del parametro non `target` è un requisito, ma è denominato per convenzione nella maggior parte delle implementazioni.

- Il valore restituito può essere specificato come tipo più specifico nell'implementazione.

Per supportare una <xref:System.ComponentModel.TypeConverter> sintassi di testo abilitata <xref:System.ComponentModel.TypeConverterAttribute> per `GetPropertyName` l'utilizzo degli attributi del membro associabile, applicare alla funzione di accesso. Applicare al `get` posto di `set` può sembrare non intuitivo; Tuttavia, questa convenzione può supportare il concetto di membri associabili di sola lettura che sono serializzabili, che è utile negli scenari di progettazione.

#### <a name="the-setpropertyname-accessor"></a>La funzione di accesso SetPropertyNameThe SetPropertyName Accessor

La firma `SetPropertyName` per la funzione di accesso deve essere:

`public static void SetPropertyName(object target, object value)`

- L'oggetto `target` può essere specificato come un tipo più specifico nell'implementazione, con la stessa logica e le stesse conseguenze descritte nella sezione precedente.

- L'oggetto `value` può essere specificato come tipo più specifico nell'implementazione.

Tenere presente che il valore di questo metodo è l'input proveniente dall'utilizzo di XAML, in genere in forma di attributo. Dal modulo di attributo deve essere il supporto del `GetPropertyName`convertitore di valori per una sintassi di testo e l'attributo nella funzione di accesso s.

### <a name="attachable-member-stores"></a>Archivi membri associabili

I metodi della funzione di accesso non sono in genere sufficienti per fornire un mezzo per inserire i valori dei membri associabili in un oggetto grafico o per recuperare i valori dall'oggetto grafico e serializzarli correttamente. Per fornire questa `target` funzionalità, gli oggetti nelle firme delle accessire precedenti devono essere in grado di archiviare valori. Il meccanismo di archiviazione deve essere coerente con il principio del membro associabile che il membro è associabile alle destinazioni in cui il membro associabile non è presente nell'elenco dei membri. Servizi XAML .NET fornisce una tecnica di implementazione <xref:System.Xaml.IAttachedPropertyStore> per <xref:System.Xaml.AttachablePropertyServices>gli archivi membri collegabili tramite le API e . <xref:System.Xaml.IAttachedPropertyStore>viene utilizzato dai writer XAML per individuare l'implementazione dell'archivio e deve essere implementato nel tipo che è il `target` delle funzioni di accesso. Le <xref:System.Xaml.AttachablePropertyServices> API statiche vengono utilizzate all'interno del corpo delle funzioni di <xref:System.Xaml.AttachableMemberIdentifier>accesso e fanno riferimento al membro associabile tramite il relativo oggetto .

## <a name="xaml-related-clr-attributes"></a>Attributi CLR correlati a XAMLXAML-Related CLR Attributes

Attribuire correttamente i tipi, i membri e gli assembly è importante per segnalare le informazioni sul sistema di tipi XAML ai servizi XAML .NET. La segnalazione delle informazioni sul sistema di tipi XAML è rilevante se si verifica una delle situazioni seguenti:

- Si intende utilizzare i tipi con sistemi XAML basati direttamente su reader XAML dei servizi XAML .NET e writer XAML.
- È possibile definire o utilizzare un framework che utilizza XAML basato su tali reader XAML e writer XAML.

Per un elenco di ogni attributo correlato a XAML rilevante per il supporto XAML dei tipi personalizzati, vedere [Attributi CLR correlati a XAML per tipi e librerie personalizzati.](clr-attributes-with-custom-types-and-libraries.md)

## <a name="usage"></a>Uso

L'utilizzo di tipi personalizzati richiede che l'autore del markup debba eseguire il mapping di un prefisso per l'assembly e lo spazio dei nomi CLR che contengono il tipo personalizzato. Questa procedura non è documentata in questo argomento.

## <a name="access-level"></a>Livello di accesso

XAML fornisce un mezzo per caricare `internal` e creare istanze di tipi che dispongono di un livello di accesso. Questa funzionalità viene fornita in modo che il codice utente possa definire i propri tipi e quindi creare un'istanza di tali classi dal markup che fa anche parte dello stesso ambito del codice utente.

Un esempio da WPFWPF è <xref:System.Windows.Controls.UserControl> ogni volta che il codice utente definisce un che è inteso come un modo per effettuare `public` il refactoring di un comportamento dell'interfaccia utente, ma non come parte di qualsiasi possibile meccanismo di estensione che potrebbe essere implicito dichiarando la classe di supporto con il livello di accesso. Tale <xref:System.Windows.Controls.UserControl> oggetto può `internal` essere dichiarato con accesso se il codice di supporto viene compilato nello stesso assembly da cui viene fatto riferimento come tipo XAML.

Per un'applicazione che carica XAML <xref:System.Xaml.XamlObjectWriter>con attendibilità totale e usa , il caricamento di classi con `internal` livello di accesso è sempre abilitato.

Per un'applicazione che carica XAML in attendibilità parziale, <xref:System.Xaml.Permissions.XamlAccessLevel> è possibile controllare le caratteristiche del livello di accesso usando l'API. Inoltre, i meccanismi di differimento (ad esempio il sistema di modelli WPFWPF) devono essere in grado di propagare le autorizzazioni del livello di accesso e conservarle per le valutazioni in fase di esecuzione finali; questo viene gestito internamente <xref:System.Xaml.Permissions.XamlAccessLevel> passando le informazioni.

### <a name="wpf-implementation"></a>Implementazione WPFWPF Implementation

XAML WPFWPF XAML usa un modello di accesso parzialmente attendibile <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> in cui se BAML viene caricato in attendibilità parziale, l'accesso è limitato all'assembly che è l'origine BAML. Per il rinvio, <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> WPFWPF usa come meccanismo per il passaggio delle informazioni sul livello di accesso.

Nella terminologia XAML WPF, un *tipo interno* è un tipo definito dallo stesso assembly che include anche il codice XAML di riferimento. È possibile eseguire il mapping di un tipo di questo tipo tramite uno spazio `xmlns:local="clr-namespace:WPFApplication1"`dei nomi XAML che omette deliberatamente la parte assembly di un mapping, ad esempio . Se BAML fa riferimento a `internal` un tipo interno `GeneratedInternalTypeHelper` e tale tipo ha un livello di accesso, viene generata una classe per l'assembly. Se si desidera `GeneratedInternalTypeHelper`evitare , `public` è necessario utilizzare il livello di accesso oppure fare trafattore la classe pertinente in un assembly separato e rendere tale assembly dipendente.

## <a name="see-also"></a>Vedere anche

- [Attributi CLR correlati a XAML per tipi e librerie personalizzati](clr-attributes-with-custom-types-and-libraries.md)
- [Servizi XAML](../../../api/index.md)
