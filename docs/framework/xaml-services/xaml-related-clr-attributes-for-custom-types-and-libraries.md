---
title: Attributi CLR correlati a XAML per tipi e librerie personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 2f907d097f52f13e733713d8ad68cc2390b051ed
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364225"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>Attributi CLR correlati a XAML per tipi e librerie personalizzati
In questo argomento vengono descritti gli attributi di Common Language Runtime (CLR) definiti da .NET Framework servizi XAML. Vengono inoltre descritti gli altri attributi CLR definiti nel .NET Framework che presentano uno scenario correlato a XAML per l'applicazione a assembly o tipi. L'assegnazione di assembly, tipi o membri con questi attributi CLR fornisce informazioni sul sistema di tipi XAML correlate ai tipi. Le informazioni vengono fornite a tutti i consumer XAML che usano .NET Framework servizi XAML per l'elaborazione del flusso di nodi XAML direttamente o tramite i reader e i writer XAML dedicati.  
  
## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>Attributi CLR correlati a XAML per tipi personalizzati e membri personalizzati  
 L'utilizzo degli attributi CLR comporta l'utilizzo del CLR generale per definire i tipi, in caso contrario tali attributi non sono disponibili. Se si utilizza CLR per definire il supporto del tipo, il contesto dello schema XAML predefinito utilizzato da .NET Framework writer XAML dei servizi XAML può leggere l'attribuzione CLR tramite reflection sugli assembly di backup.  
  
 Le sezioni seguenti descrivono gli attributi correlati a XAML che è possibile applicare ai tipi personalizzati o ai membri personalizzati. Ogni attributo CLR comunica informazioni rilevanti per un sistema di tipi XAML. Nel percorso di caricamento, le informazioni con attributi consentono al reader XAML di creare un flusso di nodi XAML valido o di creare un oggetto grafico valido per il writer XAML. Nel percorso di salvataggio, le informazioni con attributi consentono al reader XAML di formare un flusso di nodi XAML valido che ricostituisce le informazioni del sistema di tipi XAML. oppure dichiara gli hint o i requisiti di serializzazione per il writer XAML o altri consumer XAML.  
  
### <a name="ambientattribute"></a>AmbientAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **Si applica a:** Membri della classe, della `get` proprietà o della funzione di accesso che supportano proprietà collegati.  
  
 **Argomenti** Nessuna  
  
 <xref:System.Windows.Markup.AmbientAttribute>indica che la proprietà o tutte le proprietà che accettano il tipo con attributi devono essere interpretate nel concetto di proprietà di ambiente in XAML. l concetto di ambiente si riferisce al modo in cui i processori XAML determinano i proprietari dei tipi dei membri. Una proprietà di ambiente è una proprietà in cui è previsto che il valore sia disponibile nel contesto del parser durante la creazione di un oggetto grafico, ma in cui la tipica ricerca di membri di tipo viene sospesa per il set di nodi XAML immediato da creare.  
  
 Il concetto di ambiente può essere applicato a membri collegati, che non sono rappresentati come proprietà in termini di definizione <xref:System.AttributeTargets>dell'attribuzione CLR. L'utilizzo dell'attribuzione del metodo deve essere applicato solo nel caso di `get` una funzione di accesso che supporta l'utilizzo collegato per XAML.  
  
### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **Si applica a:** Classe  
  
 **Argomenti** Stringa che specifica il nome della proprietà che corrisponde a un singolo argomento del costruttore.  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute>Specifica che un oggetto può essere inizializzato mediante una sintassi del costruttore senza parametri e che una proprietà con il nome specificato fornisce informazioni sulla costruzione. Queste informazioni sono utili principalmente per la serializzazione XAML. Per altre informazioni, vedere <xref:System.Windows.Markup.ConstructorArgumentAttribute>.  
  
### <a name="contentpropertyattribute"></a>ContentPropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **Si applica a:** Classe  
  
 **Argomenti** Stringa che specifica il nome di un membro del tipo con attributo.  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute>indica che la proprietà denominata dall'argomento deve fungere da proprietà di contenuto XAML per quel tipo. La definizione della proprietà di contenuto XAML eredita tutti i tipi derivati assegnabili al tipo di definizione. È possibile eseguire l'override della definizione in un tipo derivato specifico <xref:System.Windows.Markup.ContentPropertyAttribute> applicando il tipo derivato specifico.  
  
 Per la proprietà che funge da proprietà di contenuto XAML, l'assegnazione di tag all'elemento Property per la proprietà può essere omessa nell'utilizzo di XAML. In genere, è possibile designare le proprietà del contenuto XAML che promuovono un markup XAML semplificato per i modelli di contenuto e di contenimento. Poiché solo un membro può essere designato come proprietà di contenuto XAML, talvolta si hanno scelte di progettazione da prendere in considerazione quale delle diverse proprietà del contenitore di un tipo deve essere designata come proprietà di contenuto XAML. Le altre proprietà del contenitore devono essere usate con elementi proprietà espliciti.  
  
 Nel flusso di nodi XAML, le proprietà del contenuto XAML `StartMember` producono `EndMember` ancora i nodi e, usando il nome della proprietà <xref:System.Xaml.XamlMember>per l'oggetto. Per determinare se un membro è la proprietà di contenuto XAML, esaminare <xref:System.Xaml.XamlType> il valore `StartObject` dalla posizione e ottenere il valore di <xref:System.Xaml.XamlType.ContentProperty%2A>.  
  
### <a name="contentwrapperattribute"></a>ContentWrapperAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **Si applica a:** Classe, in particolare i tipi di raccolta.  
  
 **Argomenti** Oggetto <xref:System.Type> che specifica il tipo da utilizzare come tipo di wrapper di contenuto per il contenuto esterno.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute>Specifica uno o più tipi nel tipo di raccolta associato che verranno utilizzati per eseguire il wrapping di contenuto esterno. Il contenuto esterno fa riferimento ai casi in cui i vincoli del sistema di tipi sul tipo della proprietà Content non acquisiscono tutti i possibili casi di contenuto che l'utilizzo di XAML per il tipo proprietario supporterà. Ad esempio, il supporto XAML per il contenuto di un determinato tipo potrebbe supportare le stringhe in un <xref:System.Collections.ObjectModel.Collection%601>oggetto generico fortemente tipizzato. I wrapper di contenuto sono utili per eseguire la migrazione delle convenzioni di markup preesistenti nella concezione XAML dei valori assegnabili per le raccolte, ad esempio la migrazione di modelli di contenuto correlati al testo.  
  
 Per specificare più di un tipo di wrapper di contenuto, applicare più volte l'attributo.  
  
### <a name="dependsonattribute"></a>DependsOnAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **Si applica a:** Proprietà  
  
 **Argomenti** Stringa che specifica il nome di un altro membro del tipo con attributo.  
  
 <xref:System.Windows.Markup.DependsOnAttribute>indica che la proprietà con attributi dipende dal valore di un'altra proprietà. L'applicazione di questo attributo a una definizione di proprietà garantisce che le proprietà dipendenti vengano elaborate prima nella scrittura di oggetti XAML. Gli utilizzi di <xref:System.Windows.Markup.DependsOnAttribute> specificano i casi eccezionali di proprietà sui tipi in cui è necessario seguire un ordine specifico di analisi per la creazione di oggetti validi.  
  
 È possibile applicare più <xref:System.Windows.Markup.DependsOnAttribute> case a una definizione di proprietà.  
  
### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **Si applica a:** Classe, che dovrebbe essere un <xref:System.Windows.Markup.MarkupExtension> tipo derivato.  
  
 **Argomenti** Oggetto <xref:System.Type> che specifica il tipo più preciso da prevedere `ProvideValue` come risultato dell'attributo <xref:System.Windows.Markup.MarkupExtension>.  
  
 Per altre informazioni, vedere [Cenni preliminari sulle estensioni di markup per XAML](markup-extensions-for-xaml-overview.md).  
  
### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **Si applica a:** Classe  
  
 **Argomenti** Supporta due forme di attribuzione:  
  
- Stringa che specifica il nome di una proprietà nel tipo con attributi.  
  
- Stringa che specifica il nome di una proprietà e un oggetto <xref:System.Type> per il tipo che definisce la proprietà denominata. Questo form è per specificare un membro collegabile come proprietà dell'ambito dei nomi XAML.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute>Specifica una proprietà che fornisce il valore dell'ambito dei nomi XAML per la classe con attributi. Si prevede che la proprietà NameScope XAML faccia riferimento a un oggetto <xref:System.Windows.Markup.INameScope> che implementa e che contenga il NameScope XAML effettivo, il relativo archivio e il relativo comportamento.  
  
### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **Si applica a:** Classe  
  
 **Argomenti** Stringa che specifica il nome della proprietà del nome della fase di esecuzione nel tipo con attributi.  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>segnala una proprietà del tipo con attributi che esegue il mapping alla [direttiva X:Name](x-name-directive.md)XAML. La proprietà deve essere di tipo <xref:System.String> e deve essere di lettura/scrittura.  
  
 La definizione eredita tutti i tipi derivati assegnabili al tipo di definizione. È possibile eseguire l'override della definizione in un tipo derivato specifico <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> applicando il tipo derivato specifico.  
  
### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **Si applica a:** Tipi  
  
 **Argomenti** No.  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>viene applicato a tipi specifici che possono apparire come elementi figlio all'interno di contenuto significativo di spazi vuoti (contenuto utilizzato da una raccolta <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>che dispone di). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>è rilevante principalmente per il percorso di salvataggio, ma è disponibile nel sistema di tipi XAML nel percorso di caricamento esaminando <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>. Per altre informazioni, vedere [elaborazione di spazi vuoti in XAML](whitespace-processing-in-xaml.md).  
  
### <a name="typeconverterattribute"></a>TypeConverterAttribute  
 **Documentazione di riferimento:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **Si applica a:** Classe, proprietà, metodo (l'unico caso di metodo valido XAML è una `get` funzione di accesso che supporta un membro collegabile).  
  
 **Argomenti** Oggetto <xref:System.Type> dell'oggetto <xref:System.ComponentModel.TypeConverter>.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>in un contesto XAML fa riferimento a <xref:System.ComponentModel.TypeConverter>un oggetto personalizzato. Questo <xref:System.ComponentModel.TypeConverter> fornisce il comportamento di conversione dei tipi per i tipi personalizzati o i membri di quel tipo.  
  
 Applicare l'attributo <xref:System.ComponentModel.TypeConverterAttribute> al tipo, facendo riferimento all'implementazione del convertitore di tipi. È possibile definire convertitori di tipi per XAML in classi, strutture o interfacce. Non è necessario fornire la conversione del tipo per le enumerazioni. tale conversione è abilitata in modo nativo.  
  
 Il convertitore di tipi deve essere in grado di eseguire la conversione da una stringa utilizzata per gli attributi o il testo di inizializzazione nel markup nel tipo di destinazione desiderato. Per ulteriori informazioni, vedere [TypeConverter e XAML](../wpf/advanced/typeconverters-and-xaml.md).  
  
 Anziché applicare a tutti i valori di un tipo, è possibile stabilire un comportamento del convertitore di tipi per XAML anche in una proprietà specifica. In questo caso, si applica <xref:System.ComponentModel.TypeConverterAttribute> alla definizione di proprietà (la definizione esterna, non le definizioni `get` e `set` specifiche).  
  
 Un comportamento del convertitore di tipi per l'utilizzo di XAML di un membro collegabile personalizzato può <xref:System.ComponentModel.TypeConverterAttribute> essere assegnato `get` applicando alla funzione di accesso del metodo che supporta l'utilizzo di XAML.  
  
 Analogamente <xref:System.ComponentModel.TypeConverter>a <xref:System.ComponentModel.TypeConverterAttribute> , esisteva nel .NET Framework prima dell'esistenza di XAML e il modello di convertitore di tipi veniva utilizzato per altri scopi. Per fare riferimento a e utilizzarlo <xref:System.ComponentModel.TypeConverterAttribute>, è necessario qualificarlo completamente o fornire un' `using` istruzione <xref:System.ComponentModel>per. È inoltre necessario includere l'assembly di sistema nel progetto.  
  
### <a name="uidpropertyattribute"></a>UidPropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **Si applica a:** Classe  
  
 **Argomenti** Stringa che fa riferimento alla proprietà pertinente in base al nome.  
  
 Indica la proprietà CLR di una classe che utilizza l'alias della [direttiva x:UID](x-uid-directive.md).  
  
### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **Si applica a:** Classe  
  
 **Argomenti** Valore booleano. Se utilizzato per lo scopo designato dell'attributo, deve sempre essere specificato come `true`.  
  
 Indica se questo tipo viene creato in base alla gerarchia durante la creazione del grafico di oggetti XAML. Si tratta di un concetto avanzato, che probabilmente è strettamente correlato alla definizione del modello di programmazione. Per altre informazioni, vedere <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.  
  
### <a name="valueserializerattribute"></a>ValueSerializerAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **Si applica a:** Classe, proprietà, metodo (l'unico caso di metodo valido XAML è una `get` funzione di accesso che supporta un membro collegabile).  
  
 **Argomenti** Oggetto <xref:System.Type> che specifica la classe di supporto del serializzatore di valori da utilizzare per la serializzazione di tutte le proprietà del tipo con attributi o della proprietà con attributi specifica.  
  
 <xref:System.Windows.Markup.ValueSerializer>Specifica una classe di serializzazione del valore che richiede più stato e <xref:System.ComponentModel.TypeConverter> contesto rispetto a. <xref:System.Windows.Markup.ValueSerializer>può essere associato a un membro associabile applicando l' <xref:System.Windows.Markup.ValueSerializerAttribute> attributo al metodo della `get` funzione di accesso statico per il membro associabile. La serializzazione dei valori è applicabile anche per enumerazioni, interfacce e strutture, ma non per delegati.  
  
### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **Si applica a:** Classe, in particolare i tipi di raccolta previsti per ospitare contenuto misto, in cui lo spazio vuoto intorno agli elementi oggetto può essere significativo per la rappresentazione dell'interfaccia utente.  
  
 **Argomenti** No.  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>indica che un tipo di raccolta deve essere elaborato come spazio vuoto significativo da un processore XAML, che influisce sulla costruzione dei nodi valore del flusso del nodo XAML all'interno della raccolta. Per altre informazioni, vedere [elaborazione di spazi vuoti in XAML](whitespace-processing-in-xaml.md).  
  
### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **Si applica a:** Classe, Property.  
  
 **Argomenti** Supporta due tipi di form di attribuzione come stringhe o tipi <xref:System.Type>come. Vedere <xref:System.Windows.Markup.XamlDeferLoadAttribute>.  
  
 Indica che una classe o una proprietà ha un utilizzo di caricamento posticipato per XAML (ad esempio un comportamento del modello) e segnala la classe che Abilita il comportamento di rinvio e il tipo di contenuto/destinazione.  
  
### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **Si applica a:** Classe  
  
 **Argomenti** Assegna un nome al callback.  
  
 Indica che una classe può utilizzare un'estensione di markup per fornire un valore per una o più proprietà e fa riferimento a un gestore che deve essere chiamato da un writer XAML prima di eseguire un'operazione di impostazione dell'estensione di markup su qualsiasi proprietà della classe.  
  
### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **Si applica a:** Classe  
  
 **Argomenti** Assegna un nome al callback.  
  
 Indica che una classe può usare un convertitore di tipi per fornire un valore per una o più proprietà e fa riferimento a un gestore che un writer XAML deve chiamare prima di eseguire un'operazione di impostazione del convertitore di tipi in qualsiasi proprietà della classe.  
  
### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **Si applica a:** Classe  
  
 **Argomenti** Stringa che specifica il nome della proprietà a cui assegnare l'alias `xml:lang` nel tipo con attributi.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute>segnala una proprietà del tipo con attributi che esegue il mapping alla `lang` direttiva XML. La proprietà non è necessariamente di tipo <xref:System.String>, ma deve essere assegnabile da una stringa (questa operazione può essere eseguita associando un convertitore di tipi al tipo della proprietà o alla proprietà specifica). La proprietà deve essere di lettura/scrittura.  
  
 Lo scenario per il `xml:lang` mapping consiste nel fatto che un modello a oggetti di runtime può accedere alle informazioni relative al linguaggio specificato in XML senza elaborare specificamente con un XMLDOM.  
  
 La definizione eredita tutti i tipi derivati assegnabili al tipo di definizione. È possibile eseguire l'override della definizione in un tipo derivato specifico <xref:System.Windows.Markup.XmlLangPropertyAttribute> applicando il tipo derivato specifico, sebbene si tratta di uno scenario non comune.  
  
## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>Attributi CLR correlati a XAML a livello di assembly  
 Le sezioni seguenti descrivono gli attributi correlati a XAML che non vengono applicati a tipi o definizioni di membro, ma vengono invece applicati agli assembly. Questi attributi sono attinenti all'obiettivo generale di definire una libreria che contiene tipi personalizzati da usare in XAML. Alcuni degli attributi non influiscono necessariamente direttamente sul flusso del nodo XAML, ma vengono passati nel flusso di nodi per l'uso da parte di altri consumer. I consumer per le informazioni includono ambienti di progettazione o processi di serializzazione che richiedono informazioni sullo spazio dei nomi XAML e informazioni sul prefisso associate. Queste informazioni vengono utilizzate anche da un contesto dello schema XAML (incluso l'.NET Framework valore predefinito dei servizi XAML).  
  
### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **Argomenti**  
  
- Stringa che specifica l'identificatore dello spazio dei nomi XAML a sussumere.  
  
- Stringa che specifica l'identificatore dello spazio dei nomi XAML che può sussumere lo spazio dei nomi XAML dall'argomento precedente.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>Specifica che uno spazio dei nomi XAML può essere sostituito da un altro spazio dei nomi XAML. In genere, lo spazio dei nomi XAML in sostituzione è indicato in un <xref:System.Windows.Markup.XmlnsDefinitionAttribute> definito in precedenza. Questa tecnica può essere usata per il controllo delle versioni di un vocabolario XAML in una libreria e per renderla compatibile con il markup precedentemente definito rispetto al vocabolario con versione precedente.  
  
### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **Argomenti**  
  
- Stringa che specifica l'identificatore dello spazio dei nomi XAML da definire.  
  
- Stringa che assegna un nome a uno spazio dei nomi CLR. Lo spazio dei nomi CLR deve definire i tipi pubblici nell'assembly e almeno uno dei tipi di spazio dei nomi CLR deve essere destinato all'utilizzo di XAML.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>Specifica un mapping per ogni assembly tra uno spazio dei nomi XAML e uno spazio dei nomi CLR, che viene quindi usato per la risoluzione del tipo da un writer di oggetti XAML o dal contesto dello schema XAML.  
  
 È possibile applicare <xref:System.Windows.Markup.XmlnsDefinitionAttribute> più di una a un assembly. Questa operazione può essere eseguita per qualsiasi combinazione dei motivi seguenti:  
  
- La progettazione della libreria contiene più spazi dei nomi CLR per l'organizzazione logica di accesso all'API di run-time. si desidera tuttavia che tutti i tipi negli spazi dei nomi siano utilizzabili in XAML facendo riferimento allo stesso spazio dei nomi XAML. In questo caso, si applicano <xref:System.Windows.Markup.XmlnsDefinitionAttribute> diversi attributi utilizzando lo <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> stesso valore ma <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> valori diversi. Questa operazione è particolarmente utile se si definiscono i mapping per lo spazio dei nomi XAML che il Framework o l'applicazione intende essere lo spazio dei nomi XAML predefinito nell'utilizzo comune.  
  
- La progettazione della libreria contiene più spazi dei nomi CLR e si desidera una separazione dello spazio dei nomi XAML intenzionale tra gli utilizzi dei tipi in tali spazi dei nomi CLR.  
  
- Si definisce uno spazio dei nomi CLR nell'assembly e si desidera che sia accessibile tramite più di uno spazio dei nomi XAML. Questo scenario si verifica quando si supportano più vocabolari con la stessa codebase.  
  
- Il supporto del linguaggio XAML viene definito in uno o più spazi dei nomi CLR. Per questi, il <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> valore deve essere `http://schemas.microsoft.com/winfx/2006/xaml`.  
  
### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **Argomenti**  
  
- Stringa che specifica l'identificatore di uno spazio dei nomi XAML.  
  
- Stringa che specifica un prefisso consigliato.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>Specifica un prefisso consigliato da usare per uno spazio dei nomi XAML. Il prefisso è utile quando si scrivono elementi e attributi in un file XAML serializzato dai servizi <xref:System.Xaml.XamlXmlWriter>XAML .NET Framework o quando una libreria di implementazione XAML interagisce con un ambiente di progettazione che dispone di funzionalità di modifica XAML.  
  
 È possibile applicare <xref:System.Windows.Markup.XmlnsPrefixAttribute> più di una a un assembly. Questa operazione può essere eseguita per qualsiasi combinazione dei motivi seguenti:  
  
- L'assembly definisce i tipi per più di uno spazio dei nomi XAML. In questo caso è necessario definire valori di prefisso diversi per ogni spazio dei nomi XAML.  
  
- Si stanno supportando più vocabolari e si usano prefissi diversi per ogni vocabolario e spazio dei nomi XAML.  
  
- Definire il supporto del linguaggio XAML nell'assembly e avere un <xref:System.Windows.Markup.XmlnsDefinitionAttribute> per `http://schemas.microsoft.com/winfx/2006/xaml`. In questo caso, è in genere consigliabile innalzare `x`di livello il prefisso.  
  
> [!NOTE]
>  .NET Framework servizi XAML definisce anche l'attributo <xref:System.Windows.Markup.RootNamespaceAttribute>correlato a XAML. Questo attributo è un attributo a livello di assembly per il supporto del sistema di progetto e non è pertinente per i tipi personalizzati XAML.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Attribute>
- [Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework](defining-custom-types-for-use-with-net-framework-xaml-services.md)
