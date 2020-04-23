---
title: Attributi CLR correlati a XAML per tipi e librerie personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 5481d02e4d393312fa0f0dd13b45c54acc567e13
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071766"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>Attributi CLR correlati a XAML per librerie e tipi personalizzati

In questo argomento vengono descritti gli attributi CLR (Common Language Runtime) definiti dai servizi XAML .NET. Vengono inoltre descritti altri attributi CLR definiti in .NET che dispongono di uno scenario correlato a XAML per l'applicazione in assembly o tipi. L'attribuzione di assembly, tipi o membri con questi attributi CLR fornisce informazioni sul sistema dei tipi XAML relative ai tipi. Le informazioni vengono fornite a qualsiasi consumer XAML che usa i servizi XAML .NET per elaborare il flusso del nodo XAML direttamente o tramite i reader XAML dedicati e i writer XAML.

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>Attributi CLR correlati a XAML per tipi personalizzati e membri personalizzatiXAML-Related CLR Attributes for Custom Types and Custom Members

L'utilizzo di attributi CLR implica l'utilizzo di CLR complessivo per definire i tipi, altrimenti tali attributi non sono disponibili. Se si usa CLR per definire il supporto dei tipi, il contesto dello schema XAML predefinito utilizzato dai writer XAML dei servizi XAML .NET può leggere l'attribuzione CLR tramite reflection sugli assembly di backup.

Nelle sezioni seguenti vengono descritti gli attributi correlati a XAML che è possibile applicare a tipi personalizzati o membri personalizzati. Ogni attributo CLR comunica informazioni rilevanti per un sistema di tipi XAML. Nel percorso di caricamento, le informazioni con attributi consentono al reader XAML di formare un flusso del nodo XAML valido oppure il writer XAML produce un grafico a oggetti valido. Nel percorso di salvataggio, le informazioni con attributi consentono al reader XAML di formare un flusso di nodo XAML valido che ricostituisce le informazioni sul sistema di tipi XAML. oppure dichiara i suggerimenti o i requisiti di serializzazione per il writer XAML o altri consumer XAML.

### <a name="ambientattribute"></a>AmbienteAttribute

**Documentazione di riferimento:**<xref:System.Windows.Markup.AmbientAttribute>

**Si applica a:** Membri di classe, proprietà o `get` funzione di accesso che supportano proprietà associabili.

**Argomenti:** Nessuno

<xref:System.Windows.Markup.AmbientAttribute>indica che la proprietà, o tutte le proprietà che accettano il tipo con attributi, devono essere interpretate nel concetto di proprietà di ambiente in XAML. l concetto di ambiente si riferisce al modo in cui i processori XAML determinano i proprietari dei tipi dei membri. Una proprietà di ambiente è una proprietà in cui si prevede che il valore sia disponibile nel contesto del parser durante la creazione di un oggetto grafico, ma in cui la ricerca tipica dei membri di tipo viene sospesa per il set di nodi XAML immediato creato.

Il concetto di ambiente può essere applicato ai membri associabili, che <xref:System.AttributeTargets>non sono rappresentati come proprietà in termini di definizione dell'attribuzione CLR. L'utilizzo dell'attribuzione del `get` metodo deve essere applicato solo per una funzione di accesso che supporta l'utilizzo collegabile per XAML.

### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>

**Si applica a:** Classe

**Argomenti:** Stringa che specifica il nome della proprietà che corrisponde a un singolo argomento del costruttore.

<xref:System.Windows.Markup.ConstructorArgumentAttribute>specifica che un oggetto può essere inizializzato utilizzando una sintassi del costruttore senza parametri e che una proprietà del nome specificato fornisce informazioni sulla costruzione. Queste informazioni sono utili principalmente per la serializzazione XAML. Per altre informazioni, vedere <xref:System.Windows.Markup.ConstructorArgumentAttribute>.

### <a name="contentpropertyattribute"></a>Contentpropertyattribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.ContentPropertyAttribute>

**Si applica a:** Classe

**Argomenti:** Stringa che specifica il nome di un membro del tipo con attributi.

<xref:System.Windows.Markup.ContentPropertyAttribute>indica che la proprietà denominata dall'argomento deve essere utilizzata come proprietà di contenuto XAML per quel tipo. La definizione della proprietà del contenuto XAML eredita a tutti i tipi derivati assegnabili al tipo di definizione. È possibile eseguire l'override della definizione su un tipo derivato specifico applicando <xref:System.Windows.Markup.ContentPropertyAttribute> il tipo derivato specifico.

Per la proprietà che funge da proprietà di contenuto XAML, il tag dell'elemento proprietà per la proprietà può essere omesso nell'utilizzo di XAML. In genere, si designano proprietà di contenuto XAML che promuovono un markup XAML semplificato per i modelli di contenuto e contenimento. Poiché solo un membro può essere designato come proprietà di contenuto XAML, talvolta è possibile scegliere quale delle diverse proprietà del contenitore di un tipo deve essere designata come proprietà di contenuto XAML. Le altre proprietà del contenitore devono essere utilizzate con elementi di proprietà espliciti.

Nel flusso del nodo XAML, `StartMember` le `EndMember` proprietà di contenuto XAML producono <xref:System.Xaml.XamlMember>ancora e nodi, utilizzando il nome della proprietà per l'oggetto . Per determinare se un membro è la <xref:System.Xaml.XamlType> proprietà `StartObject` di contenuto XAML, <xref:System.Xaml.XamlType.ContentProperty%2A>esaminare il valore dalla posizione e ottenere il valore di .

### <a name="contentwrapperattribute"></a>ContentWrapperAttribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.ContentWrapperAttribute>

**Si applica a:** Classe, in particolare i tipi di raccolta.

**Argomenti:** Oggetto <xref:System.Type> che specifica il tipo da utilizzare come tipo di wrapper del contenuto per il contenuto esterno.

<xref:System.Windows.Markup.ContentWrapperAttribute>specifica uno o più tipi nel tipo di raccolta associato che verranno utilizzati per eseguire il wrapping del contenuto esterno. Il contenuto esterno fa riferimento ai casi in cui i vincoli di sistema del tipo sul tipo della proprietà di contenuto non acquisiscono tutti i possibili casi di contenuto supportati dall'utilizzo di XAML per il tipo proprietario. Ad esempio, il supporto XAML per il contenuto di un <xref:System.Collections.ObjectModel.Collection%601>determinato tipo potrebbe supportare stringhe in un generico fortemente tipizzato. I wrapper del contenuto sono utili per la migrazione di convenzioni di markup preesistenti nella concezione di XAML dei valori assegnabili per le raccolte, ad esempio la migrazione di modelli di contenuto correlati al testo.

Per specificare più di un tipo di wrapper di contenuto, applicare l'attributo più volte.

### <a name="dependsonattribute"></a>DependsOnAttribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.DependsOnAttribute>

**Si applica a:** Proprietà

**Argomenti:** Stringa che specifica il nome di un altro membro del tipo con attributi.

<xref:System.Windows.Markup.DependsOnAttribute>indica che la proprietà con attributi dipende dal valore di un'altra proprietà. L'applicazione di questo attributo a una definizione di proprietà garantisce che le proprietà dipendenti vengano elaborate per prima nella scrittura di oggetti XAML. Gli utilizzi <xref:System.Windows.Markup.DependsOnAttribute> di specificare i casi eccezionali di proprietà nei tipi in cui è necessario seguire un ordine specifico di analisi per la creazione di oggetti validi.

È possibile <xref:System.Windows.Markup.DependsOnAttribute> applicare più casi a una definizione di proprietà.

### <a name="markupextensionreturntypeattribute"></a>Markupextensionreturntypeattribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>

**Si applica a:** Classe, che deve essere <xref:System.Windows.Markup.MarkupExtension> un tipo derivato.

**Argomenti:** Oggetto <xref:System.Type> che specifica il tipo più `ProvideValue` preciso da aspettarsi come risultato dell'attributo <xref:System.Windows.Markup.MarkupExtension>.

Per altre informazioni, vedere Cenni preliminari sulle estensioni di [markup per XAML.](markup-extensions-overview.md)

### <a name="namescopepropertyattribute"></a>Namescopepropertyattribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>

**Si applica a:** Classe

**Argomenti:** Supporta due forme di attribuzione:

- Stringa che specifica il nome di una proprietà nel tipo con attributi.

- Stringa che specifica il nome di una <xref:System.Type> proprietà e oggetto per il tipo che definisce la proprietà denominata. Questo modulo consente di specificare un membro associabile come proprietà dell'ambito dei nomi XAML.

<xref:System.Windows.Markup.NameScopePropertyAttribute>specifica una proprietà che fornisce il valore dell'ambito dei nomi XAML per la classe con attributi. La proprietà dell'ambito dei nomi XAML <xref:System.Windows.Markup.INameScope> deve fare riferimento a un oggetto che implementa e contiene l'ambito dei nomi XAML effettivo, il relativo archivio e il relativo comportamento.

### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>

**Si applica a:** Classe

**Argomenti:** Stringa che specifica il nome della proprietà del nome in fase di esecuzione nel tipo con attributi.

<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>genera una proprietà del tipo con attributi che esegue il mapping alla [direttiva x:Name](xname-directive.md)XAML . La proprietà deve <xref:System.String> essere di tipo e deve essere di lettura/scrittura.

La definizione eredita a tutti i tipi derivati assegnabili al tipo di definizione. È possibile eseguire l'override della definizione su un tipo derivato specifico applicando <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> il tipo derivato specifico.

### <a name="trimsurroundingwhitespaceattribute"></a>TagliaSurroundingWhitespaceAttribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>

**Si applica a:** Tipi

**Argomenti:** Nessuno.

<xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>viene applicato a tipi specifici che potrebbero apparire come elementi figlio all'interno <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>di contenuto significativo di spazi vuoti (contenuto contenuto contenuto di una raccolta con ). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>è principalmente rilevante per il percorso di salvataggio, ma è disponibile <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>nel sistema di tipi XAML nel percorso di caricamento esaminando . Per altre informazioni, vedere [Elaborazione di spazi](white-space-processing.md)vuoti in XAML.

### <a name="typeconverterattribute"></a>TypeConverterAttribute

**Documentazione di riferimento:**  <xref:System.ComponentModel.TypeConverterAttribute>

**Si applica a:** Classe, proprietà, metodo (l'unico caso `get` del metodo valido per XAML è una funzione di accesso che supporta un membro associabile).

**Argomenti:** Il <xref:System.Type> del <xref:System.ComponentModel.TypeConverter>file .

<xref:System.ComponentModel.TypeConverterAttribute>in un contesto <xref:System.ComponentModel.TypeConverter>XAML fa riferimento a un oggetto personalizzato . Fornisce <xref:System.ComponentModel.TypeConverter> il comportamento di conversione dei tipi per i tipi personalizzati o i membri di tale tipo.

Applicare <xref:System.ComponentModel.TypeConverterAttribute> l'attributo al tipo, facendo riferimento all'implementazione del convertitore di tipi. È possibile definire convertitori di tipi per XAML su classi, strutture o interfacce. Non è necessario fornire la conversione dei tipi per le enumerazioni, che la conversione è abilitata in modo nativo.

Il convertitore di tipi deve essere in grado di eseguire la conversione da una stringa utilizzata per gli attributi o il testo di inizializzazione nel markup, nel tipo di destinazione desiderato. Per ulteriori informazioni, vedere [TypeConverters e XAML.](../../framework/wpf/advanced/typeconverters-and-xaml.md)

Anziché applicare a tutti i valori di un tipo, è anche possibile stabilire un comportamento del convertitore di tipi per XAML su una proprietà specifica. In questo caso, <xref:System.ComponentModel.TypeConverterAttribute> si applica alla definizione di `get` proprietà `set` (la definizione esterna, non le definizioni e le definizioni specifiche).

Un comportamento del convertitore di tipi per l'utilizzo <xref:System.ComponentModel.TypeConverterAttribute> xaml `get` di un membro associabile personalizzato può essere assegnato applicando alla funzione di accesso al metodo che supporta l'utilizzo di XAML.

Analogamente a <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> esisteva in .NET prima dell'esistenza di XAML e il modello del convertitore di tipi serviva ad altri scopi. Per fare riferimento <xref:System.ComponentModel.TypeConverterAttribute>e utilizzare , è necessario `using` qualificarlo completamente o fornire un'istruzione per <xref:System.ComponentModel>. Includere anche l'assembly di sistema nel progetto.

### <a name="uidpropertyattribute"></a>Uidpropertyattribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.UidPropertyAttribute>

**Si applica a:** Classe

**Argomenti:** Stringa che fa riferimento alla proprietà pertinente in base al nome.

Indica la proprietà CLR di una classe che assomiglia la [direttiva x:Uid](xuid-directive.md).

### <a name="usableduringinitializationattribute"></a>Usableduringinitializationattribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>

**Si applica a:** Classe

**Argomenti:** Valore booleano. Se utilizzato per lo scopo previsto dell'attributo, il valore deve essere impostato su `true`.

Indica se il tipo viene compilato dall'alto verso il basso durante la creazione di oggetti oggetto XAML. Si tratta di un concetto avanzato, che è probabilmente strettamente correlato alla definizione del modello di programmazione. Per altre informazioni, vedere <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.

### <a name="valueserializerattribute"></a>Valueserializerattribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.ValueSerializerAttribute>

**Si applica a:** Classe, proprietà, metodo (l'unico caso `get` del metodo valido per XAML è una funzione di accesso che supporta un membro associabile).

**Argomenti:** Oggetto <xref:System.Type> che specifica la classe di supporto del serializzatore di valori da utilizzare durante la serializzazione di tutte le proprietà del tipo con attributi o della proprietà con attributi specifica.

<xref:System.Windows.Markup.ValueSerializer>specifica una classe di serializzazione di valore <xref:System.ComponentModel.TypeConverter> che richiede più stato e contesto di un oggetto does. <xref:System.Windows.Markup.ValueSerializer>può essere associato a un membro <xref:System.Windows.Markup.ValueSerializerAttribute> associabile applicando `get` l'attributo sul metodo della funzione di accesso statico per il membro associabile. La serializzazione dei valori è applicabile anche per enumerazioni, interfacce e strutture, ma non per i delegati.

### <a name="whitespacesignificantcollectionattribute"></a>Whitespacesignificantcollectionattribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>

**Si applica a:** Classe, in particolare i tipi di raccolta che si prevede ospitare contenuto misto, in cui gli spazi vuoti intorno agli elementi oggetto potrebbero essere significativi per la rappresentazione dell'interfaccia utente.

**Argomenti:** Nessuno.

<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>indica che un tipo di raccolta deve essere elaborato come spazio vuoto significativo da un processore XAML, che influenza la costruzione dei nodi valore del flusso del nodo XAML all'interno della raccolta. Per altre informazioni, vedere [Elaborazione di spazi](white-space-processing.md)vuoti in XAML.

### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute (AttributiXamlDeferLoadAttribute)

**Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>

**Si applica a:** Classe, proprietà.

**Argomenti:** Supporta due tipi di form di attribuzione come stringhe o tipi come <xref:System.Type>. Vedere <xref:System.Windows.Markup.XamlDeferLoadAttribute>.

Indica che una classe o una proprietà prevede l'utilizzo del caricamento posticipato per XAML (come il comportamento dei modelli) e segnala la classe che consente tale comportamento e il relativo tipo di contenuto/destinazione.

### <a name="xamlsetmarkupextensionattribute"></a>Xamlsetmarkupextensionattribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>

**Si applica a:** Classe

**Argomenti:** Assegna un nome al callback.

Indica che una classe può utilizzare un'estensione di markup per fornire un valore per una o più delle relative proprietà e fa riferimento a un gestore che un writer XAML deve chiamare prima di eseguire un'operazione di impostazione dell'estensione di markup su qualsiasi proprietà della classe.

### <a name="xamlsettypeconverterattribute"></a>Proprietà XamlSetTypeConverterAttribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>

**Si applica a:** Classe

**Argomenti:** Assegna un nome al callback.

Indica che una classe può utilizzare un convertitore di tipi per fornire un valore per una o più delle relative proprietà e fa riferimento a un gestore che un writer XAML deve chiamare prima di eseguire un'operazione di impostazione del convertitore di tipi su qualsiasi proprietà della classe.

### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute (Attributo XmlLangPropertyAttribute)

**Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>

**Si applica a:** Classe

**Argomenti:** Stringa che specifica il nome della proprietà `xml:lang` a cui assegnare un alias nel tipo con attributi.

<xref:System.Windows.Markup.XmlLangPropertyAttribute>restituisce una proprietà del tipo con `lang` attributi che esegue il mapping alla direttiva XML. La proprietà non è <xref:System.String> necessariamente di tipo, ma deve essere assegnabile da una stringa (l'assegnazione può essere eseguita associando un convertitore di tipi al tipo della proprietà o alla proprietà specifica). La proprietà deve essere di lettura/scrittura.

Lo scenario `xml:lang` per il mapping è in modo che un modello a oggetti di runtime abbia accesso alle informazioni sul linguaggio specificate da XML senza elaborare in modo specifico con un XMLDOM.

La definizione eredita a tutti i tipi derivati assegnabili al tipo di definizione. È possibile eseguire l'override della definizione su un tipo derivato specifico applicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> il tipo derivato specifico, anche se si tratta di uno scenario non comune.

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>Attributi CLR correlati a XAML a livello di assembly

Nelle sezioni seguenti vengono descritti gli attributi correlati a XAML che non vengono applicati ai tipi o alle definizioni dei membri, ma che vengono invece applicati agli assembly. Questi attributi sono pertinenti all'obiettivo generale di definire una libreria che contiene tipi personalizzati da utilizzare in XAML. Alcuni degli attributi non influenzano necessariamente direttamente il flusso del nodo XAML, ma vengono passati nel flusso del nodo per l'uso da parte di altri consumer. I consumer per le informazioni includono ambienti di progettazione o processi di serializzazione che richiedono informazioni sullo spazio dei nomi XAML e informazioni sul prefisso associato. Anche un contesto dello schema XAML (incluso l'impostazione predefinita dei servizi XAML .NET) usa queste informazioni.

### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>

**Argomenti:**

- Stringa che specifica l'identificatore dello spazio dei nomi XAML da eseguire somma.

- Stringa che specifica l'identificatore dello spazio dei nomi XAML che può assumere lo spazio dei nomi XAML dall'argomento precedente.

  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>specifica che uno spazio dei nomi XAML può essere sommato da un altro spazio dei nomi XAML. In genere, lo spazio dei nomi XAML in sostituzione è indicato in un <xref:System.Windows.Markup.XmlnsDefinitionAttribute> definito in precedenza. Questa tecnica può essere utilizzata per il controllo delle versioni di un vocabolario XAML in una libreria e per renderlo compatibile con il markup definito in precedenza rispetto al vocabolario con controllo delle versioni precedente.

### <a name="xmlnsdefinitionattribute"></a>Xmlnsdefinitionattribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>

**Argomenti:**

- Stringa che specifica l'identificatore dello spazio dei nomi XAML da definire.

- Stringa che denomina uno spazio dei nomi CLR. Lo spazio dei nomi CLR deve definire i tipi pubblici nell'assembly e almeno uno dei tipi dello spazio dei nomi CLR deve essere destinato all'utilizzo di XAML.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>specifica un mapping in base all'assembly tra uno spazio dei nomi XAML e uno spazio dei nomi CLR, che viene quindi utilizzato per la risoluzione del tipo da un writer di oggetti XAML o dal contesto dello schema XAML.

  Più di <xref:System.Windows.Markup.XmlnsDefinitionAttribute> uno può essere applicato a un assieme. Questa operazione può essere eseguita per qualsiasi combinazione dei seguenti motivi:

- La progettazione della libreria contiene più spazi dei nomi CLR per l'organizzazione logica dell'accesso API in fase di esecuzione; Tuttavia, si desidera che tutti i tipi in tali spazi dei nomi siano utilizzabili in XAML facendo riferimento allo stesso spazio dei nomi XAML. In questo caso, <xref:System.Windows.Markup.XmlnsDefinitionAttribute> si applicano <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> diversi <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> attributi utilizzando lo stesso valore ma valori diversi. Ciò è particolarmente utile se si definiscono i mapping per lo spazio dei nomi XAML che il framework o l'applicazione intende essere lo spazio dei nomi XAML predefinito nell'utilizzo comune.

- La progettazione della libreria contiene più spazi dei nomi CLR e si desidera una separazione intenzionale dello spazio dei nomi XAML tra gli utilizzi dei tipi in tali spazi dei nomi CLR.

- Si definisce uno spazio dei nomi CLR nell'assembly e si desidera che sia accessibile tramite più di uno spazio dei nomi XAML. Questo scenario si verifica quando si supportano più vocabolari con la stessa codebase.

- Il supporto del linguaggio XAML viene definito in uno o più spazi dei nomi CLR. In questo caso, <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> il `http://schemas.microsoft.com/winfx/2006/xaml`valore deve essere .

### <a name="xmlnsprefixattribute"></a>Xmlnsprefixattribute

**Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>

**Argomenti:**

- Stringa che specifica l'identificatore di uno spazio dei nomi XAML.

- Stringa che specifica un prefisso consigliato.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>specifica un prefisso consigliato da utilizzare per uno spazio dei nomi XAML. Il prefisso è utile quando si scrivono elementi e attributi <xref:System.Xaml.XamlXmlWriter>in un file XAML serializzato da .NET XAML Services o quando una libreria di implementazione XAML interagisce con un ambiente di progettazione con funzionalità di modifica XAML.

  Più di <xref:System.Windows.Markup.XmlnsPrefixAttribute> uno può essere applicato a un assieme. Questa operazione può essere eseguita per qualsiasi combinazione dei seguenti motivi:

- L'assembly definisce i tipi per più di uno spazio dei nomi XAML. In questo caso, definire valori di prefisso diversi per ogni spazio dei nomi XAML.

- Si supportano più vocabolari e si usano prefissi diversi per ogni vocabolario e spazio dei nomi XAML.

- Definire il supporto del linguaggio <xref:System.Windows.Markup.XmlnsDefinitionAttribute> XAML `http://schemas.microsoft.com/winfx/2006/xaml`nell'assembly e avere un per . In questo caso, in genere `x`è necessario alzare di livello il prefisso .

> [!NOTE]
> I servizi XAML .NET definiscono <xref:System.Windows.Markup.RootNamespaceAttribute>anche l'attributo correlato a XAML. Questo attributo è un attributo a livello di assembly per il supporto del sistema del progetto e non è rilevante per i tipi personalizzati XAML.

## <a name="see-also"></a>Vedere anche

- <xref:System.Attribute>
- [Definizione di tipi personalizzati da usare con i servizi XAML .NET](define-custom-types.md)
