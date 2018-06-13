---
title: Attributi CLR correlati a XAML per tipi e librerie personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: fc99ada6a3bc8465d22527a7ef985f9b057bcf77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566483"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>Attributi CLR correlati a XAML per tipi e librerie personalizzati
In questo argomento vengono descritti gli attributi di common language runtime (CLR) definiti dai servizi XAML di .NET Framework. Vengono inoltre descritti altri attributi CLR che sono definiti in .NET Framework che dispongono di uno scenario correlati a XAML per gli assembly o tipi di applicazione. Assegnazione di attributi assembly, tipi o membri con questi attributi CLR fornisce informazioni sul sistema di tipi XAML correlate ai tipi. Vengono fornite informazioni per tutti i consumer XAML che utilizza i servizi XAML di .NET Framework per l'elaborazione di flusso del nodo XAML direttamente o tramite il dedicato reader XAML e writer XAML.  
  
## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>Attributi CLR correlati a XAML per tipi personalizzati e membri personalizzati  
 L'utilizzo di attributi CLR comporta che si utilizza per definire i tipi CLR nel suo complesso, in caso contrario tali attributi non sono disponibili. Se si utilizza CLR per definire il tipo di backup, il contesto dello schema XAML predefinito utilizzato dai writer XAML dei servizi XAML di .NET Framework possa leggere attribuzione CLR tramite la reflection per assembly di supporto.  
  
 Nelle sezioni seguenti vengono descritti gli attributi correlati a XAML che è possibile applicare a tipi o membri personalizzati. Ogni attributo CLR comunica informazioni relative a un sistema di tipi XAML. Nel percorso di caricamento, le informazioni degli attributi consentono il reader XAML formare un flusso del nodo XAML valido, o consente al writer XAML di produrre un oggetto grafico valido. In Salva percorso, le informazioni degli attributi consentono il reader XAML formare un flusso del nodo XAML valido che ricostruisce informazioni sul sistema di tipi XAML; o dichiara hint per la serializzazione o i requisiti per il writer XAML o altri consumer di XAML.  
  
### <a name="ambientattribute"></a>AmbientAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **Si applica a:** (classe), proprietà, o `get` i membri di funzione di accesso che supportano la proprietà associabile.  
  
 **Argomenti:** nessuno  
  
 <xref:System.Windows.Markup.AmbientAttribute> indica che la proprietà o tutte le proprietà che accettano il tipo con attributo, devono essere interpretate nel concetto di proprietà di ambiente in XAML. l concetto di ambiente si riferisce al modo in cui i processori XAML determinano i proprietari dei tipi dei membri. Una proprietà di ambiente è una proprietà in cui il valore deve essere disponibile nel contesto del parser durante la creazione di un oggetto grafico, ma la ricerca di membro di tipo tipica viene sospesa per impostare la creazione di nodi XAML immediato.  
  
 Il concetto di ambiente può essere applicato ai membri associabili, che non sono rappresentati come proprietà in termini di modalità attribuzione CLR definisce <xref:System.AttributeTargets>. L'utilizzo di attribuzione del metodo deve essere applicato solo in caso di un `get` funzione di accesso che supporta l'utilizzo associabile per XAML.  
  
### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **Si applica a:** (classe)  
  
 **Argomenti:** una stringa che specifica il nome della proprietà che corrispondono a un argomento singolo costruttore.  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute> Specifica che un oggetto può essere inizializzato utilizzando una sintassi del costruttore non predefinito e che una proprietà con il nome specificato fornisce informazioni sulla costruzione. Queste informazioni sono utili principalmente per la serializzazione XAML. Per altre informazioni, vedere <xref:System.Windows.Markup.ConstructorArgumentAttribute>.  
  
### <a name="contentpropertyattribute"></a>ContentPropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **Si applica a:** (classe)  
  
 **Argomenti:** una stringa che specifica il nome di un membro del tipo con attributo.  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute> indica che la proprietà denominata dall'argomento deve essere usata come la proprietà di contenuto XAML per quel tipo. La definizione delle proprietà di contenuto XAML è ereditata da tutti i tipi derivati assegnabili al tipo di definizione. È possibile sostituire la definizione di un tipo derivato specifico applicando <xref:System.Windows.Markup.ContentPropertyAttribute> sullo specifico tipo derivato.  
  
 Per la proprietà che funge da proprietà di contenuto XAML, elemento di proprietà tag per la proprietà può essere omesso nell'utilizzo di XAML. In genere, specificare le proprietà di contenuto XAML che alzare di livello un markup XAML semplificato per i modelli di contenuto e contenuto. Poiché solo un membro può essere definito come proprietà di contenuto XAML, è talvolta necessario scelte di progettazione per rendere relative del contenitore delle proprietà di un tipo devono essere designate come proprietà di contenuto XAML. Proprietà del contenitore deve essere utilizzata con gli elementi di proprietà espliciti.  
  
 Nel flusso del nodo XAML, le proprietà di contenuto XAML producono ancora `StartMember` e `EndMember` nodi, utilizzando il nome della proprietà per il <xref:System.Xaml.XamlMember>. Per determinare se il membro è la proprietà di contenuto XAML, esaminare il <xref:System.Xaml.XamlType> valore il `StartObject` posizionare e ottenere il valore di <xref:System.Xaml.XamlType.ContentProperty%2A>.  
  
### <a name="contentwrapperattribute"></a>ContentWrapperAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **Si applica a:** (classe), in particolare i tipi di raccolta.  
  
 **Argomenti:** A <xref:System.Type> che specifica il tipo da utilizzare come tipo di wrapper del contenuto per il contenuto esterno.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute> Specifica uno o più tipi nel tipo di raccolta associato che verrà utilizzato per eseguire il wrapping di contenuto esterno. Contenuto esterno si riferisce ai casi in cui i vincoli di sistema di tipo al tipo della proprietà di contenuto non acquisiscono tutti i possibili casi di contenuto che sarà possibile supportare l'utilizzo della sintassi XAML per il tipo proprietario. Ad esempio, il supporto XAML per il contenuto di un determinato tipo può supportare le stringhe in un oggetto generico fortemente tipizzato <xref:System.Collections.ObjectModel.Collection%601>. Wrapper del contenuto sono utili per la migrazione di convenzioni del markup preesistenti nella concezione XAML di valori assegnabili per le raccolte, ad esempio la migrazione di modelli di contenuto correlati al testo.  
  
 Per specificare più di un tipo di wrapper del contenuto, applicare l'attributo più volte.  
  
### <a name="dependsonattribute"></a>DependsOnAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **Si applica a:** proprietà  
  
 **Argomenti:** una stringa che specifica il nome di un altro membro del tipo con attributo.  
  
 <xref:System.Windows.Markup.DependsOnAttribute> indica che la proprietà con attributa dipende dal valore di un'altra proprietà. L'applicazione di questo attributo a una definizione di proprietà garantisce che le proprietà dipendenti vengono elaborate prima in scrittura di oggetti XAML. Utilizzi di <xref:System.Windows.Markup.DependsOnAttribute> specificano i casi eccezionali di proprietà sui tipi in cui deve essere seguire un ordine specifico di analisi per la creazione di un oggetto valido.  
  
 È possibile applicare più <xref:System.Windows.Markup.DependsOnAttribute> case per una definizione di proprietà.  
  
### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **Si applica a:** classe, che deve essere un <xref:System.Windows.Markup.MarkupExtension> tipo derivato.  
  
 **Argomenti:** A <xref:System.Type> che specifica il tipo più preciso per prevedere come il `ProvideValue` risultato il con attributi <xref:System.Windows.Markup.MarkupExtension>.  
  
 Per ulteriori informazioni, vedere [estensioni di Markup per XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **Si applica a:** (classe)  
  
 **Argomenti:** supporta due forme di attribuzione di:  
  
-   Stringa che specifica il nome di una proprietà del tipo con attributi.  
  
-   Una stringa che specifica il nome di una proprietà e un <xref:System.Type> per il tipo che definisce la proprietà denominata. Questo modulo consente di specificare un membro associabile come proprietà namescope XAML.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute> Specifica una proprietà che fornisce il valore di ambito dei nomi XAML per la classe con attributi. La proprietà di ambito dei nomi XAML deve fare riferimento a un oggetto che implementa <xref:System.Windows.Markup.INameScope> e mantiene il namescope XAML effettivo, il relativo archivio e il relativo comportamento.  
  
### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **Si applica a:** (classe)  
  
 **Argomenti:** una stringa che specifica il nome della proprietà name di runtime del tipo con attributi.  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> segnala una proprietà del tipo con attributo che è mappata a XAML [direttiva X:Name](../../../docs/framework/xaml-services/x-name-directive.md). La proprietà deve essere di tipo <xref:System.String> e deve essere di lettura/scrittura.  
  
 La definizione è ereditata da tutti i tipi derivati assegnabili al tipo di definizione. È possibile sostituire la definizione di un tipo derivato specifico applicando <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> sullo specifico tipo derivato.  
  
### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **Si applica a:** tipi  
  
 **Argomenti:** nessuno.  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> viene applicato a tipi specifici che potrebbero essere visualizzati come elementi figlio all'interno di spazi vuoti significativi contenuto (contenuto di una raccolta contenente <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> è importante soprattutto per il salvataggio percorso, ma è disponibile nel sistema di tipi XAML nel percorso di caricamento esaminando <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>. Per ulteriori informazioni, vedere [elaborazione degli spazi vuoti in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### <a name="typeconverterattribute"></a>TypeConverterAttribute  
 **Documentazione di riferimento:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **Si applica a:** (classe), proprietà, metodo (l'unico caso metodo XAML valido è un `get` funzione di accesso che supporta un membro associabile).  
  
 **Argomenti:** il <xref:System.Type> del <xref:System.ComponentModel.TypeConverter>.  
  
 <xref:System.ComponentModel.TypeConverterAttribute> in un file XAML contesto fa riferimento a un oggetto personalizzato <xref:System.ComponentModel.TypeConverter>. Questo <xref:System.ComponentModel.TypeConverter> fornisce il comportamento di conversione di tipi per tipi personalizzati o membri di quel tipo.  
  
 Si applica il <xref:System.ComponentModel.TypeConverterAttribute> attributo per il tipo di implementazione del convertitore di tipi di riferimento. È possibile definire i convertitori di tipi per XAML su classi, strutture o interfacce. Non è necessario fornire la conversione di tipo per le enumerazioni, che la conversione è abilitata in modo nativo.  
  
 Il convertitore di tipi deve essere in grado di convertire una stringa che viene utilizzata per il testo di inizializzazione nel markup o gli attributi nel tipo di destinazione. Per ulteriori informazioni, vedere [TypeConverters and XAML](../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
 Anziché applicare a tutti i valori di un tipo, un comportamento del convertitore di tipi per XAML può essere stabilito anche in una proprietà specifica. In questo caso, applicano <xref:System.ComponentModel.TypeConverterAttribute> alla definizione della proprietà (la definizione esterna, non la specifica `get` e `set` definizioni).  
  
 Un comportamento del convertitore di tipi per l'utilizzo XAML di un membro associabile personalizzato può essere assegnato applicando <xref:System.ComponentModel.TypeConverterAttribute> per il `get` funzione di accesso di metodo che supporta l'utilizzo di XAML.  
  
 Simile a <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> era inclusa in .NET Framework precedenti all'introduzione di XAML e il modello del tipo di convertitore serviva ad altri scopi. Per fare riferimento e utilizzare <xref:System.ComponentModel.TypeConverterAttribute>, è necessario completamente qualificarlo o fornire un `using` istruzione per <xref:System.ComponentModel>. È inoltre necessario includere l'assembly di sistema del progetto.  
  
### <a name="uidpropertyattribute"></a>UidPropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **Si applica a:** (classe)  
  
 **Argomenti:** una stringa che fa riferimento la proprietà pertinente in base al nome.  
  
 Indica la proprietà di una classe CLR che rappresenta l'alias di [direttiva X:UID](../../../docs/framework/xaml-services/x-uid-directive.md).  
  
### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **Si applica a:** (classe)  
  
 **Argomenti:** un valore booleano. Se utilizzato per scopi previsti dell'attributo, questo deve sempre essere specificato come `true`.  
  
 Indica se questo tipo viene creato in base alla gerarchia durante la creazione del grafico di oggetti XAML. Questo è un concetto avanzato, è probabile che è strettamente correlato alla definizione del modello di programmazione. Per altre informazioni, vedere <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.  
  
### <a name="valueserializerattribute"></a>ValueSerializerAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **Si applica a:** (classe), proprietà, metodo (l'unico caso metodo XAML valido è un `get` funzione di accesso che supporta un membro associabile).  
  
 **Argomenti:** A <xref:System.Type> che specifica la classe di supporto valore serializzatore da utilizzare quando si serializza tutte le proprietà del tipo con attributo o le specifiche attribuito proprietà.  
  
 <xref:System.Windows.Markup.ValueSerializer> Specifica una classe di serializzazione di valori che richiede più lo stato e il contesto rispetto a un <xref:System.ComponentModel.TypeConverter> does. <xref:System.Windows.Markup.ValueSerializer> è possibile associare a un membro associabile applicando la <xref:System.Windows.Markup.ValueSerializerAttribute> attributo statica `get` metodo della funzione di accesso per il membro associabile. La serializzazione di valori è applicabile anche per le enumerazioni, interfacce e strutture, ma non per i delegati.  
  
### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **Si applica a:** (classe), in particolare i tipi di raccolta previste per ospitare contenuto misto, in cui lo spazio vuoto attorno agli elementi oggetto potrebbe essere significativo per la rappresentazione dell'interfaccia utente.  
  
 **Argomenti:** nessuno.  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> indica che un tipo di raccolta deve essere elaborato come significativa di spazi vuoti da un processore XAML, che influisce sulla costruzione di nodi di valore del flusso di nodi XAML all'interno della raccolta. Per ulteriori informazioni, vedere [elaborazione degli spazi vuoti in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **Si applica a:** (classe), proprietà.  
  
 **Argomenti:** attribuzione supporta due form tipi sotto forma di stringhe o tipi come <xref:System.Type>. Vedere <xref:System.Windows.Markup.XamlDeferLoadAttribute>.  
  
 Indica che una classe o proprietà ha un utilizzo del caricamento posticipato per XAML (ad esempio, un comportamento del modello) e restituisce la classe che consente tale comportamento e il relativo tipo di contenuto/destinazione.  
  
### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **Si applica a:** (classe)  
  
 **Argomenti:** denomina il callback.  
  
 Indica che una classe è possibile utilizzare un'estensione di markup per fornire un valore per uno o più delle relative proprietà e fa riferimento a un gestore che chiami un writer XAML prima di eseguire un'operazione di impostazione di estensione di markup su qualsiasi proprietà della classe.  
  
### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **Si applica a:** (classe)  
  
 **Argomenti:** denomina il callback.  
  
 Indica che una classe è possibile usare un convertitore di tipi per fornire un valore per uno o più delle relative proprietà e fa riferimento a un gestore che chiami un writer XAML prima di eseguire un'operazione di impostazione di convertitore di tipo su qualsiasi proprietà della classe.  
  
### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **Si applica a:** (classe)  
  
 **Argomenti:** una stringa che specifica il nome della proprietà da alias da `xml:lang` nel tipo con attributo.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute> segnala una proprietà del tipo con attributo che viene eseguito il mapping al codice XML `lang` direttiva. La proprietà non è di tipo <xref:System.String>, ma deve essere assegnabile da una stringa (ad esempio mediante l'associazione di un convertitore di tipi con il tipo della proprietà o con la proprietà specifica). La proprietà deve essere di lettura/scrittura.  
  
 Lo scenario per il mapping `xml:lang` è, in modo che un modello a oggetti runtime possa accedere alle informazioni sul linguaggio XML specificato senza alcuna elaborazione specifica con un oggetto XMLDOM.  
  
 La definizione è ereditata da tutti i tipi derivati assegnabili al tipo di definizione. È possibile sostituire la definizione di un tipo derivato specifico applicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> sullo specifico tipo, derivato Sebbene sia uno scenario comune.  
  
## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>Attributi CLR correlati a XAML a livello di Assembly  
 Nelle sezioni seguenti vengono descritti gli attributi correlati a XAML che non vengono applicati a tipi o le definizioni dei membri, ma vengono invece applicati agli assembly. Questi attributi sono pertinenti per l'obiettivo complessivo della definizione di una libreria che contiene i tipi personalizzati da utilizzare in XAML. Alcuni degli attributi non influiscono necessariamente il flusso del nodo XAML direttamente, ma vengono passati nel flusso del nodo per altri consumer di utilizzare. I consumer per le informazioni includono gli ambienti di progettazione o i processi di serializzazione che necessitano di informazioni dello spazio dei nomi XAML e sul prefisso associato. Un contesto dello schema XAML (incluso il valore predefinito di servizi XAML di .NET Framework) inoltre utilizza queste informazioni.  
  
### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **Argomenti:**  
  
-   Stringa che specifica l'identificatore dello spazio dei nomi XAML da classificare.  
  
-   Stringa che specifica l'identificatore dello spazio dei nomi XAML che possono includere lo spazio dei nomi XAML dell'argomento precedente.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> Specifica che uno spazio dei nomi XAML può essere sostituito da un altro spazio dei nomi XAML. In genere, viene indicato lo spazio dei nomi XAML classificato in definita in precedenza <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Questa tecnica può essere utilizzato per il controllo delle versioni di un vocabolario XAML in una libreria e per renderlo compatibile con markup precedentemente definito per il vocabolario della versione precedente.  
  
### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **Argomenti:**  
  
-   Stringa che specifica l'identificatore dello spazio dei nomi XAML per definire.  
  
-   Stringa che i nomi di uno spazio dei nomi CLR. Lo spazio dei nomi CLR deve definire i tipi pubblici nell'assembly e almeno uno dei tipi dello spazio dei nomi CLR deve essere destinato a utilizzo della sintassi XAML.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Specifica un mapping di un singolo assembly tra uno spazio dei nomi XAML e uno spazio dei nomi CLR che viene quindi usato per la risoluzione del tipo da un writer di oggetti XAML o il contesto dello schema XAML.  
  
 Più <xref:System.Windows.Markup.XmlnsDefinitionAttribute> può essere applicato a un assembly. Questa operazione può essere eseguita per qualsiasi combinazione dei seguenti motivi:  
  
-   La progettazione della libreria contiene più spazi dei nomi CLR per l'organizzazione logica di accesso alle API di runtime; Tuttavia, si desidera che tutti i tipi in tali spazi dei nomi affinché possa essere usato con XAML facendo riferimento allo stesso spazio dei nomi XAML. In questo caso, si applicano diversi <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attributi utilizzando lo stesso <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> valore ma diversi <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> valori. Ciò è particolarmente utile se si siano definendo i mapping per lo spazio dei nomi XAML del framework o dell'applicazione intende lo spazio dei nomi XAML predefinito di uso comune.  
  
-   La progettazione della libreria contiene più spazi dei nomi CLR e si desidera una separazione di spazio dei nomi XAML intenzionale tra gli utilizzi dei tipi negli spazi dei nomi CLR.  
  
-   Definire uno spazio dei nomi CLR nell'assembly e si desidera che sia accessibile attraverso più di uno spazio dei nomi XAML. Questo scenario si verifica quando si prevede di supportare più vocabolari con la stessa codebase.  
  
-   Supporto del linguaggio XAML definite in uno o più spazi dei nomi CLR. Per questo motivo, il <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> il valore deve essere `http://schemas.microsoft.com/winfx/2006/xaml`.  
  
### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **Argomenti:**  
  
-   Stringa che specifica l'identificatore di uno spazio dei nomi XAML.  
  
-   Stringa che specifica un prefisso consigliato.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Specifica un prefisso consigliato da usare per uno spazio dei nomi XAML. Il prefisso è utile quando si scrivono elementi e attributi in un file XAML che viene serializzato da servizi XAML di .NET Framework <xref:System.Xaml.XamlXmlWriter>, o quando una libreria di implementazione XAML interagisce con un ambiente di progettazione XAML con funzionalità di modifica.  
  
 Più <xref:System.Windows.Markup.XmlnsPrefixAttribute> può essere applicato a un assembly. Questa operazione può essere eseguita per qualsiasi combinazione dei seguenti motivi:  
  
-   L'assembly definisce i tipi per più di uno spazio dei nomi XAML. In questo caso è necessario definire i valori di prefisso diverso per ogni spazio dei nomi XAML.  
  
-   Supporto di più vocabolari e si utilizzano prefissi diversi per ogni vocabolario e spazio dei nomi XAML.  
  
-   Si definisce il supporto del linguaggio XAML nell'assembly e avere un <xref:System.Windows.Markup.XmlnsDefinitionAttribute> per `http://schemas.microsoft.com/winfx/2006/xaml`. In questo caso, è in genere opportuno alzare di livello il prefisso `x`.  
  
> [!NOTE]
>  Servizi XAML di .NET framework definisce anche l'attributo correlati a XAML <xref:System.Windows.Markup.RootNamespaceAttribute>. Questo attributo è un attributo a livello di assembly per il supporto di sistema di progetto e quindi non è rilevante per i tipi XAML personalizzati.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Attribute>  
 [Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)
