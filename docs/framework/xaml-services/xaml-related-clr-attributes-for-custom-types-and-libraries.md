---
title: Attributi CLR correlati a XAML per tipi e librerie personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 13cc4d85a1a4b5c9b1ff61afbf7980a54e3d22d0
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47172050"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>Attributi CLR correlati a XAML per tipi e librerie personalizzati
Questo argomento descrive gli attributi di common language runtime (CLR) definiti dai servizi XAML di .NET Framework. Viene inoltre altri attributi CLR che sono definiti in .NET Framework con uno scenario basate su XAML per gli assembly o i tipi dell'applicazione. Attribuzione di assembly, tipi o membri con questi attributi CLR fornisce informazioni sul sistema di tipo XAML correlate ai tipi. Vengono fornite informazioni per eventuali consumer XAML che usa i servizi XAML di .NET Framework per l'elaborazione del flusso di nodi XAML direttamente o tramite i reader XAML dedicati e i writer XAML.  
  
## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>Attributi CLR correlati a XAML per tipi personalizzati e membri personalizzati  
 Usando gli attributi CLR comporta che si usa per definire i tipi CLR nel suo complesso, in caso contrario, tali attributi non sono disponibili. Se si utilizza CLR per definire tipo di backup, il contesto dello schema XAML predefinito usato dai writer XAML di servizi XAML di .NET Framework possa leggere attribuzione di CLR tramite la reflection per assembly di supporto.  
  
 Le sezioni seguenti descrivono gli attributi correlati a XAML che è possibile applicare a tipi o membri personalizzati. Ogni attributo CLR comunica le informazioni relative a un sistema di tipi XAML. Nel percorso di caricamento, le informazioni degli attributi consentono il reader XAML formare un flusso di nodi XAML valido o è utile il writer XAML produrre un grafo di oggetto valido. Salva percorso, le informazioni degli attributi consentono il reader XAML formare un flusso di nodi XAML valido che ricostruisce le informazioni del sistema di tipi XAML; o dichiara hint per la serializzazione o i requisiti per il writer XAML o altri consumer XAML.  
  
### <a name="ambientattribute"></a>AmbientAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **Si applica a:** classe, proprietà, o `get` i membri di funzione di accesso che supportano le proprietà associabili.  
  
 **Argomenti:** None  
  
 <xref:System.Windows.Markup.AmbientAttribute> indica che la proprietà o tutte le proprietà che accettano il tipo con attributo, devono essere interpretate secondo il concetto di proprietà di ambiente in XAML. l concetto di ambiente si riferisce al modo in cui i processori XAML determinano i proprietari dei tipi dei membri. Una proprietà di ambiente è una proprietà in cui il valore deve essere disponibile nel contesto del parser durante la creazione di un oggetto grafico, ma in cui ricerca tipi o membri tipica viene sospeso per il nodo XAML immediato set creato.  
  
 Il concetto di ambiente può essere applicato ai membri associabili, che non sono rappresentati come proprietà in termini di modalità attribuzione di Common Language Runtime definisce <xref:System.AttributeTargets>. L'utilizzo di attribuzione del metodo deve essere applicata solo nel caso di un `get` funzione di accesso che supporta l'utilizzo associabile per XAML.  
  
### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **Si applica a:** classe  
  
 **Argomenti:** una stringa che specifica il nome della proprietà che corrisponde a un unico argomento del costruttore.  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute> Specifica che un oggetto può essere inizializzato mediante una sintassi del costruttore non predefinito e che una proprietà del nome specificato fornisce informazioni sulla costruzione. Queste informazioni sono utili principalmente per la serializzazione XAML. Per altre informazioni, vedere <xref:System.Windows.Markup.ConstructorArgumentAttribute>.  
  
### <a name="contentpropertyattribute"></a>ContentPropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **Si applica a:** classe  
  
 **Argomenti:** una stringa che specifica il nome di un membro del tipo con attributo.  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute> indica che la proprietà denominata dall'argomento può essere utilizzato come la proprietà di contenuto XAML per quel tipo. La definizione di proprietà di contenuto XAML è ereditata da tutti i tipi derivati che sono assegnabili al tipo di definizione. È possibile sostituire la definizione in un tipo derivato specifico applicando <xref:System.Windows.Markup.ContentPropertyAttribute> sullo specifico tipo derivato.  
  
 Per la proprietà che funge da proprietà di contenuto XAML, l'assegnazione di tag per la proprietà di elemento di proprietà può essere omessa nella sintassi di XAML. In genere, è definire proprietà di contenuto XAML che promuovono un markup XAML ottimizzato per i modelli di contenuto e il contenimento. Poiché solo un membro può essere definito come proprietà di contenuto XAML, è talvolta necessario scelte di progettazione per rendere relative del contenitore diverse proprietà di un tipo deve essere designata come proprietà di contenuto XAML. Le altre proprietà del contenitore deve essere utilizzato con gli elementi di proprietà esplicito.  
  
 Nel flusso di nodi XAML, le proprietà del contenuto XAML comunque producono `StartMember` e `EndMember` nodi, usando il nome della proprietà per il <xref:System.Xaml.XamlMember>. Per determinare se il membro è la proprietà di contenuto XAML, esaminare il <xref:System.Xaml.XamlType> valore di `StartObject` posizionare e ottenere il valore di <xref:System.Xaml.XamlType.ContentProperty%2A>.  
  
### <a name="contentwrapperattribute"></a>ContentWrapperAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **Si applica a:** (classe), in particolare i tipi di raccolta.  
  
 **Argomenti:** oggetto <xref:System.Type> che specifica il tipo da utilizzare come tipo di wrapper del contenuto per il contenuto esterno.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute> Specifica uno o più tipi nel tipo di raccolta associato che verrà usato per eseguire il wrapping di contenuto esterno. Contenuto esterno fa riferimento ai casi in cui i vincoli di sistema di tipo del tipo di proprietà di contenuto non si acquisiscono tutti i possibili casi di contenuto che sarà possibile supportare l'utilizzo XAML per il tipo proprietario. Ad esempio, il supporto XAML per il contenuto di un determinato tipo può supportare le stringhe in un generico oggetto fortemente tipizzato <xref:System.Collections.ObjectModel.Collection%601>. Wrapper del contenuto sono utili per la migrazione preesistenti convenzioni di markup in concezione della XAML di valori assegnabili per le raccolte, ad esempio la migrazione dei modelli di contenuto correlati al testo.  
  
 Per specificare più di un tipo di wrapper del contenuto, applicare l'attributo più volte.  
  
### <a name="dependsonattribute"></a>DependsOnAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **Si applica a:** proprietà  
  
 **Argomenti:** una stringa che specifica il nome di un altro membro del tipo con attributo.  
  
 <xref:System.Windows.Markup.DependsOnAttribute> indica che la proprietà con attributa dipende dal valore di un'altra proprietà. Applicando questo attributo a una definizione di proprietà garantisce che le proprietà dipendenti vengono elaborate prima di tutto nella scrittura di oggetti XAML. Gli utilizzi di <xref:System.Windows.Markup.DependsOnAttribute> specificano i casi eccezionali di proprietà sui tipi in cui è necessario seguire un ordine specifico di analisi per la creazione di oggetti validi.  
  
 È possibile applicare più <xref:System.Windows.Markup.DependsOnAttribute> case da una definizione di proprietà.  
  
### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **Si applica a:** classe, che deve essere un <xref:System.Windows.Markup.MarkupExtension> tipo derivato.  
  
 **Argomenti:** oggetto <xref:System.Type> che specifica il tipo più preciso per prevedere come le `ProvideValue` risultato dei con attributi <xref:System.Windows.Markup.MarkupExtension>.  
  
 Per altre informazioni, vedere [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **Si applica a:** classe  
  
 **Argomenti:** supporta due forme di attribuzione:  
  
-   Stringa che specifica il nome di una proprietà nel tipo con attributi.  
  
-   Una stringa che specifica il nome di una proprietà e un <xref:System.Type> per il tipo che definisce la proprietà denominata. Questo modulo è per la specifica di un membro associabile come proprietà namescope XAML.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute> Specifica una proprietà che fornisce il valore di ambito dei nomi XAML per la classe con attributi. Si dovrà fare riferimento a un oggetto che implementa la proprietà namescope XAML <xref:System.Windows.Markup.INameScope> e mantiene il namescope XAML effettivo, il relativo archivio e il relativo comportamento.  
  
### <a name="runtimenamepropertyattribute"></a>Quell '  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **Si applica a:** classe  
  
 **Argomenti:** una stringa che specifica il nome della proprietà name in fase di esecuzione nel tipo con attributi.  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> indica una proprietà del tipo con attributo che esegue il mapping al XAML [direttiva X:Name](../../../docs/framework/xaml-services/x-name-directive.md). La proprietà deve essere di tipo <xref:System.String> e deve essere di lettura/scrittura.  
  
 La definizione è ereditata da tutti i tipi derivati che sono assegnabili al tipo di definizione. È possibile sostituire la definizione in un tipo derivato specifico applicando <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> sullo specifico tipo derivato.  
  
### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **Si applica a:** tipi  
  
 **Argomenti:** None.  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> viene applicato a tipi specifici che potrebbe essere visualizzato come elementi figlio all'interno del contenuto significativo di spazi vuoti (contenuto di una raccolta con <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> è importante soprattutto per il salvataggio percorso, ma è disponibile nel sistema di tipi XAML nel percorso di caricamento esaminando <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>. Per altre informazioni, vedere [l'elaborazione in XAML gli spazi vuoti](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### <a name="typeconverterattribute"></a>TypeConverterAttribute  
 **Documentazione di riferimento:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **Si applica a:** classe, proprietà, un metodo (l'unico caso metodo XAML valido è un `get` della funzione di accesso che supporta un membro associabile).  
  
 **Argomenti:** il <xref:System.Type> del <xref:System.ComponentModel.TypeConverter>.  
  
 <xref:System.ComponentModel.TypeConverterAttribute> in un XAML contesto fa riferimento a un oggetto personalizzato <xref:System.ComponentModel.TypeConverter>. Ciò <xref:System.ComponentModel.TypeConverter> fornisce il comportamento di conversione di tipi per i tipi personalizzati o i membri di quel tipo.  
  
 Si applica il <xref:System.ComponentModel.TypeConverterAttribute> attributo per il tipo di implementazione del convertitore di tipi di riferimento. È possibile definire i convertitori di tipi per XAML in classi, strutture o interfacce. Non è necessaria per eseguire la conversione di tipo per le enumerazioni, che la conversione è abilitata in modo nativo.  
  
 Il convertitore di tipi deve essere in grado di eseguire la conversione da una stringa che viene usata per il testo di inizializzazione nel markup, o gli attributi nel tipo di destinazione desiderato. Per altre informazioni, vedere [TypeConverter e XAML](../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
 Invece di applicare a tutti i valori di un tipo, un comportamento del convertitore di tipi per XAML può essere stabilito anche su una proprietà specifica. In questo caso, applicano <xref:System.ComponentModel.TypeConverterAttribute> alla definizione della proprietà (la definizione esterna, non le specifiche `get` e `set` definizioni).  
  
 Un comportamento del convertitore di tipo per l'utilizzo XAML di un membro associabile personalizzato può essere assegnato applicando <xref:System.ComponentModel.TypeConverterAttribute> per il `get` della funzione di accesso di metodo che supporta l'utilizzo XAML.  
  
 Simile a <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> era inclusa in .NET Framework precedenti l'esistenza di XAML e il modello di convertitore di tipo serviti altri scopi. Per riferimento e usi <xref:System.ComponentModel.TypeConverterAttribute>, è completamente necessario qualificarlo o fornire un `using` istruzione per <xref:System.ComponentModel>. È anche necessario includere l'assembly di sistema del progetto.  
  
### <a name="uidpropertyattribute"></a>UidPropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **Si applica a:** classe  
  
 **Argomenti:** una stringa che fa riferimento la proprietà pertinente in base al nome.  
  
 Indica la proprietà CLR di una classe che rappresenta l'alias di [X:Uid Directive](../../../docs/framework/xaml-services/x-uid-directive.md).  
  
### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **Si applica a:** classe  
  
 **Argomenti:** un valore booleano. Se utilizzato per scopi previsti dell'attributo, deve sempre essere specificato come `true`.  
  
 Indica se questo tipo viene creato in base alla gerarchia durante la creazione del grafico di oggetti XAML. Questo è un concetto avanzato, che è probabilmente strettamente correlato alla definizione del modello di programmazione. Per altre informazioni, vedere <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.  
  
### <a name="valueserializerattribute"></a>ValueSerializerAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **Si applica a:** classe, proprietà, un metodo (l'unico caso metodo XAML valido è un `get` della funzione di accesso che supporta un membro associabile).  
  
 **Argomenti:** oggetto <xref:System.Type> che specifica la classe di supporto valore serializzatore da utilizzare durante la serializzazione di tutte le proprietà del tipo con attributo o le specifiche attribuito proprietà.  
  
 <xref:System.Windows.Markup.ValueSerializer> Specifica una classe di serializzazione di valori che è più lo stato e contesto rispetto a un <xref:System.ComponentModel.TypeConverter> viene. <xref:System.Windows.Markup.ValueSerializer> può essere associato a un membro associabile applicando la <xref:System.Windows.Markup.ValueSerializerAttribute> attributo su statico `get` metodo della funzione di accesso per il membro associabile. Serializzazione di valori è applicabile anche per le enumerazioni, interfacce e strutture, ma non per i delegati.  
  
### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **Si applica a:** (classe), in particolare i tipi di raccolta che dovranno ospitare contenuto misto, in cui lo spazio vuoto attorno agli elementi oggetto potrebbe essere significativo per la rappresentazione dell'interfaccia utente.  
  
 **Argomenti:** None.  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> indica che un tipo di raccolta deve essere elaborato come spazi vuoti significativi da un processore XAML, che influisce sulla costruzione di nodi del valore del flusso di nodi XAML all'interno della raccolta. Per altre informazioni, vedere [l'elaborazione in XAML gli spazi vuoti](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **Si applica a:** classe, la proprietà.  
  
 **Argomenti:** attribuzione supporta due form tipi sotto forma di stringhe o tipi come <xref:System.Type>. Vedere <xref:System.Windows.Markup.XamlDeferLoadAttribute>.  
  
 Indica che una classe o una proprietà con un utilizzo del caricamento posticipato per XAML (ad esempio il comportamento dei modelli) e segnala la classe che consente tale comportamento e il relativo tipo di contenuto/destinazione.  
  
### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **Si applica a:** classe  
  
 **Argomenti:** denomina il callback.  
  
 Indica che una classe può utilizzare un'estensione di markup per fornire un valore per uno o più delle relative proprietà e fa riferimento a un gestore che un writer XAML deve chiamare prima di eseguire un'operazione di impostazione di estensione di markup su qualsiasi proprietà della classe.  
  
### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **Si applica a:** classe  
  
 **Argomenti:** denomina il callback.  
  
 Indica che una classe può utilizzare un convertitore di tipi per fornire un valore per uno o più delle relative proprietà e fa riferimento a un gestore che un writer XAML deve chiamare prima di eseguire un'operazione di impostazione del convertitore di tipo su qualsiasi proprietà della classe.  
  
### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **Si applica a:** classe  
  
 **Argomenti:** una stringa che specifica il nome della proprietà da alias `xml:lang` nel tipo con attributo.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute> indica una proprietà del tipo con attributo che esegue il mapping al codice XML `lang` direttiva. La proprietà non è necessariamente di tipo <xref:System.String>, ma deve essere assegnabile da una stringa (ad esempio associando un convertitore di tipi con il tipo della proprietà o con la proprietà specifica). La proprietà deve essere di lettura/scrittura.  
  
 Lo scenario di mapping `xml:lang` è, in modo che un modello a oggetti runtime possa accedere alle informazioni sul linguaggio XML specificato senza alcuna elaborazione specifica con un oggetto XMLDOM.  
  
 La definizione è ereditata da tutti i tipi derivati che sono assegnabili al tipo di definizione. È possibile sostituire la definizione in un tipo derivato specifico applicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> sullo specifico tipo, derivato Sebbene questo sia uno scenario comune.  
  
## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>Attributi CLR correlati a XAML a livello di Assembly  
 Le sezioni seguenti descrivono gli attributi correlati a XAML che non vengono applicati a tipi o le definizioni dei membri, ma vengono invece applicati agli assembly. Questi attributi sono pertinenti per l'obiettivo complessivo della definizione di una libreria che contiene i tipi personalizzati da usare in XAML. Alcuni degli attributi pure non obbligatoriamente influenza il flusso di nodi XAML direttamente, ma sono passate nel flusso di nodi per altri consumer da usare. I consumer per le informazioni includono gli ambienti di progettazione o i processi di serializzazione che necessitano di informazioni dello spazio dei nomi XAML e sul prefisso associato. Un XAML contesto dello schema (compresa quella predefinita di servizi XAML di .NET Framework) inoltre utilizza queste informazioni.  
  
### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **Argomenti:**  
  
-   Stringa che specifica l'identificatore dello spazio dei nomi XAML da classificare.  
  
-   Stringa che specifica l'identificatore dello spazio dei nomi XAML che possono includere lo spazio dei nomi XAML dell'argomento precedente.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> Specifica che uno spazio dei nomi XAML può essere sostituito da un altro spazio dei nomi XAML. In genere, viene indicato lo spazio dei nomi XAML classificato in un oggetto definito in precedenza <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Questa tecnica può essere usato per il controllo delle versioni di un vocabolario XAML in una libreria e per renderlo compatibile con markup precedentemente definito per il vocabolario della versione precedente.  
  
### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **Argomenti:**  
  
-   Stringa che specifica l'identificatore dello spazio dei nomi XAML per definire.  
  
-   Stringa che denomina un spazio dei nomi CLR. Lo spazio dei nomi CLR è necessario definire i tipi pubblici nell'assembly e almeno uno dei tipi dello spazio dei nomi CLR deve essere destinato all'utilizzo XAML.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Specifica un mapping di un singolo assembly tra uno spazio dei nomi XAML e uno spazio dei nomi CLR, che viene quindi usato per la risoluzione del tipo da un writer di oggetti XAML o il contesto dello schema XAML.  
  
 Più <xref:System.Windows.Markup.XmlnsDefinitionAttribute> può essere applicato a un assembly. Questa operazione può essere eseguita per qualsiasi combinazione dei seguenti motivi:  
  
-   La progettazione della libreria contiene più spazi dei nomi CLR per l'organizzazione logica di accesso all'API di runtime; Tuttavia, è necessario tutti i tipi in tali spazi dei nomi per essere utilizzabile da XAML facendo lo stesso spazio dei nomi XAML. In questo caso, si applicano diversi <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attributi usando lo stesso <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> valore ma diversi <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> valori. Ciò è particolarmente utile se si siano definendo i mapping per lo spazio dei nomi XAML del framework o dell'applicazione creato per essere lo spazio dei nomi XAML predefinito di uso comune.  
  
-   La progettazione della libreria contiene più spazi dei nomi CLR, e si desidera una separazione di spazio dei nomi XAML intenzionale tra gli utilizzi dei tipi di tali spazi dei nomi CLR.  
  
-   Si definisce uno spazio dei nomi CLR nell'assembly e si desidera che sia accessibile attraverso più di uno spazio dei nomi XAML. Questo scenario si verifica quando si intende supportare più vocabolari con la stessa codebase.  
  
-   Supporto del linguaggio XAML per definire in uno o più spazi dei nomi CLR. Per questo motivo, il <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> il valore deve essere `http://schemas.microsoft.com/winfx/2006/xaml`.  
  
### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute  
 **Documentazione di riferimento:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **Argomenti:**  
  
-   Stringa che specifica l'identificatore di uno spazio dei nomi XAML.  
  
-   Stringa che specifica un prefisso consigliato.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Specifica un prefisso consigliato da usare per uno spazio dei nomi XAML. Il prefisso è utile quando si scrivono elementi e attributi in un file XAML che viene serializzato da servizi XAML di .NET Framework <xref:System.Xaml.XamlXmlWriter>, o quando una libreria di implementazione XAML interagisce con un ambiente di progettazione XAML con funzionalità di modifica.  
  
 Più <xref:System.Windows.Markup.XmlnsPrefixAttribute> può essere applicato a un assembly. Questa operazione può essere eseguita per qualsiasi combinazione dei seguenti motivi:  
  
-   L'assembly definisce i tipi per più di uno spazio dei nomi XAML. In questo caso è necessario definire i valori di prefisso diverso per ogni spazio dei nomi XAML.  
  
-   Si prevede di supportare più vocabolari e si utilizzano prefissi diversi per ogni del vocabolario e dello spazio dei nomi XAML.  
  
-   Si definisce il supporto del linguaggio XAML nell'assembly e avere una <xref:System.Windows.Markup.XmlnsDefinitionAttribute> per `http://schemas.microsoft.com/winfx/2006/xaml`. In questo caso, è in genere opportuno alzare di livello il prefisso `x`.  
  
> [!NOTE]
>  Servizi XAML di .NET framework definisce anche l'attributo correlato a XAML <xref:System.Windows.Markup.RootNamespaceAttribute>. Questo attributo è un attributo a livello di assembly per il supporto di sistema di progetto e quindi non è rilevante per i tipi personalizzati di XAML.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Attribute>  
 [Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)
