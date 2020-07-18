---
title: Serializzazione e deserializzazione
description: Vengono fornite informazioni sul motore di serializzazione WCF, che viene convertito tra .NET Framework oggetti e XML, in entrambe le direzioni.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3d71814c-bda7-424b-85b7-15084ff9377a
ms.openlocfilehash: b770543eb09ed2edc1a028561e0cf41e74fab1cc
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86444495"
---
# <a name="serialization-and-deserialization"></a>Serializzazione e deserializzazione
Windows Communication Foundation (WCF) include un nuovo motore di serializzazione, ovvero <xref:System.Runtime.Serialization.DataContractSerializer> . Il viene <xref:System.Runtime.Serialization.DataContractSerializer> convertito tra .NET Framework oggetti e XML in entrambe le direzioni. In questo argomento viene illustrato il funzionamento del serializzatore.  
  
 Quando si serializzano oggetti .NET Framework, il serializzatore riconosce una varietà di modelli di programmazione della serializzazione, incluso il nuovo modello di *contratto dati* . Per un elenco completo dei tipi supportati, vedere [Types Supported by the Data Contract Serializer](types-supported-by-the-data-contract-serializer.md). Per un'introduzione ai contratti dati, vedere [Using Data Contracts](using-data-contracts.md).  
  
 Durante la deserializzazione di XML, il serializzatore utilizza le classi <xref:System.Xml.XmlReader> e <xref:System.Xml.XmlWriter> . Supporta inoltre le <xref:System.Xml.XmlDictionaryReader> classi e <xref:System.Xml.XmlDictionaryWriter> per consentire la produzione di codice XML ottimizzato in alcuni casi, ad esempio quando si utilizza il formato XML binario WCF.  
  
 WCF include anche un serializzatore complementare, <xref:System.Runtime.Serialization.NetDataContractSerializer> . <xref:System.Runtime.Serialization.NetDataContractSerializer>:

* ***Non*** è protetto. Per ulteriori informazioni, vedere la [Guida alla sicurezza di BinaryFormatter](/dotnet/standard/serialization/binaryformatter-security-guide).
* È simile ai <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> serializzatori e perché emette anche .NET Framework nomi di tipo come parte dei dati serializzati.
* Viene utilizzato quando gli stessi tipi sono condivisi durante la serializzazione e la fine della deserializzazione.

 Sia <xref:System.Runtime.Serialization.DataContractSerializer> che <xref:System.Runtime.Serialization.NetDataContractSerializer> derivano da una classe base comune <xref:System.Runtime.Serialization.XmlObjectSerializer> .  
  
> [!WARNING]
> <xref:System.Runtime.Serialization.DataContractSerializer> serializza stringhe che contengono caratteri di controllo con un valore esadecimale inferiore a 20 come entità XML. Questo può causare un problema con un client non WCF durante l'invio di tali dati a un servizio WCF.  
  
## <a name="creating-a-datacontractserializer-instance"></a>Creazione di un'istanza DataContractSerializer  
 La creazione di un'istanza di <xref:System.Runtime.Serialization.DataContractSerializer> è un passaggio importante. Dopo la costruzione, non è possibile modificare nessuna di queste impostazioni.  
  
### <a name="specifying-the-root-type"></a>Specifica del tipo radice  
 Il *tipo radice* è il tipo delle istanze che vengono serializzate o deserializzate. <xref:System.Runtime.Serialization.DataContractSerializer> ha numerosi overload del costruttore, tuttavia è necessario fornire almeno un tipo radice utilizzando il parametro `type` .  
  
 Un serializzatore creato per un certo tipo radice non può essere utilizzato per serializzare (o deserializzare) un altro tipo, a meno che il tipo non sia derivato dal tipo radice. Nell'esempio che segue vengono illustrate due classi.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#1)]
 [!code-vb[c_StandaloneDataContractSerializer#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#1)]  
  
 Questo codice costruisce un'istanza di `DataContractSerializer` che può essere utilizzata solo per serializzare o deserializzare istanze della classe `Person` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#2)]
 [!code-vb[c_StandaloneDataContractSerializer#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#2)]  
  
### <a name="specifying-known-types"></a>Specifica di tipi noti  
 Se i tipi serializzati implicano un polimorfismo che non è già gestito utilizzando l'attributo <xref:System.Runtime.Serialization.KnownTypeAttribute> o un qualche altro meccanismo, è necessario passare al costruttore del serializzatore un elenco di possibili tipi noti utilizzando il parametro `knownTypes` . Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](data-contract-known-types.md).  
  
 Nell'esempio di codice seguente viene illustrata una classe, `LibraryPatron`, che comprende una raccolta di un tipo specifico `LibraryItem`. La seconda classe definisce il tipo `LibraryItem` . La terza e la quarta classe,`Book` e `Newspaper`, ereditano dalla classe `LibraryItem` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#3)]  
 [!code-vb[c_StandaloneDataContractSerializer#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#3)]  
  
 Nel codice seguente viene creata un'istanza del serializzatore utilizzando il parametro `knownTypes` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#4)]
 [!code-vb[c_StandaloneDataContractSerializer#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#4)]  
  
### <a name="specifying-the-default-root-name-and-namespace"></a>Specifica del nome principale e dello spazio dei nomi predefiniti  
 In genere, quando un oggetto viene serializzato, il nome e lo spazio dei nomi predefiniti dell'elemento XML più esterno vengono determinati in base al nome del contratto dati e allo spazio dei nomi. I nomi di tutti gli elementi interni vengono determinati dai nomi dei membri dati e il loro spazio dei nomi è lo spazio dei nomi del contratto dati. Nell'esempio seguente vengono impostati i valori `Name` e `Namespace` nei costruttori delle classi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#5)]
 [!code-vb[c_StandaloneDataContractSerializer#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#5)]  
  
 La serializzazione di un'istanza della classe `Person` produce un XML simile al seguente.  
  
```xml  
<PersonContract xmlns="http://schemas.contoso.com">  
  <AddressMember>  
    <StreetMember>123 Main Street</StreetMember>  
   </AddressMember>  
</PersonContract>  
```  
  
 È tuttavia possibile personalizzare il nome e lo spazio dei nomi predefiniti dell'elemento radice passando i valori dei parametri `rootName` e `rootNamespace` al costruttore <xref:System.Runtime.Serialization.DataContractSerializer> . Si noti che `rootNamespace` non influisce sullo spazio dei nomi degli elementi contenuti che corrispondono ai membri dati. Influisce solo sullo spazio dei nomi dell'elemento più esterno.  
  
 Questi valori possono essere passati come stringhe o come istanze della classe <xref:System.Xml.XmlDictionaryString> per consentire la loro ottimizzazione utilizzando il formato XML binario.  
  
### <a name="setting-the-maximum-objects-quota"></a>Impostazione della quota massima di oggetti  
 Alcuni overload del costruttore `DataContractSerializer` hanno un parametro `maxItemsInObjectGraph` . Tale parametro determina il numero massimo di oggetti serializzati o deserializzati dal serializzatore in una singola chiamata al metodo <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> . Questo metodo legge sempre un oggetto radice che, tuttavia, potrebbe contenere altri oggetti come membri dei propri dati. Tali oggetti possono avere altri oggetti e così via. Il valore predefinito è 65536. Si noti che, in caso di serializzazione o deserializzazione di matrici, ogni elemento della matrice viene considerato come un oggetto separato. Inoltre, poiché per alcuni oggetti è possibile una vasta rappresentazione in memoria, tale quota da sola potrebbe non essere sufficiente per impedire attacchi di tipo Denial of Service. Per ulteriori informazioni, vedere [considerazioni sulla sicurezza per i dati](security-considerations-for-data.md). Se è necessario aumentare la quota oltre il valore predefinito, è importante aumentarla sia sul lato di invio (serializzazione) sia su quello di ricezione (deserializzazione) poiché si applica sia durante la lettura che durante la scrittura dei dati.  
  
### <a name="round-trips"></a>Percorsi di andata e ritorno  
 Si verifica un *percorso di andata e ritorno* quando un oggetto viene deserializzato e serializzato di nuovo in un'unica operazione. Pertanto, passa da XML a un'istanza dell'oggetto e torna indietro in un flusso XML.  
  
 Alcuni overload del costruttore `DataContractSerializer` hanno un parametro `ignoreExtensionDataObject` , la cui impostazione predefinita è `false` . In questa modalità predefinita, è possibile inviare i dati su un percorso di andata e ritorno da una versione più recente di un contratto dati a una versione precedente e di nuovo indietro alla versione più recente senza alcuna perdita, a condizione che il contratto dati implementi l'interfaccia <xref:System.Runtime.Serialization.IExtensibleDataObject> . Si supponga, ad esempio, che la versione 1 del contratto dati `Person` contenga i membri dati `Name` e `PhoneNumber` e che la versione 2 aggiunga un membro `Nickname` . Se `IExtensibleDataObject` viene implementato, durante l'invio di informazioni dalla versione 2 alla versione 1 i dati `Nickname` vengono memorizzati ed emessi di nuovo alla successiva serializzazione; i dati non vengono persi nel percorso di andata e ritorno. Per ulteriori informazioni, vedere [contratti dati compatibili con](forward-compatible-data-contracts.md) le versioni successive e [controllo delle versioni del contratto dati](data-contract-versioning.md).  
  
#### <a name="security-and-schema-validity-concerns-with-round-trips"></a>Problemi di sicurezza e validità dello schema in caso di percorsi di andata e ritorno  
 I percorsi di andata e ritorno possono avere implicazioni di sicurezza. La deserializzazione e memorizzazione di grandi quantità di dati estranei, ad esempio, possono rappresentare un rischio per la sicurezza. Possono esservi problemi di sicurezza quando vengono emessi di nuovo dati che non è assolutamente possibile verificare, specie se implicano firme digitali. Nello scenario precedente, ad esempio, l'endpoint della versione 1 potrebbe firmare un valore `Nickname` che contiene dati dannosi. Infine, potrebbero verificarsi problemi di validità dello schema poiché un endpoint potrebbe desiderare di emettere sempre dati strettamente conformi al contratto dichiarato e nessun valore aggiuntivo. Nell'esempio precedente, il contratto dell'endpoint della versione 1 asserisce che emette solo `Name` e `PhoneNumber`e, se viene utilizzata la convalida dello schema, l'emissione del valore `Nickname` aggiuntivo causa l'insuccesso della convalida.  
  
#### <a name="enabling-and-disabling-round-trips"></a>Attivazione e disattivazione di percorsi di andata e ritorno  
 Per disattivare i percorsi di andata e ritorno, non implementare l'interfaccia <xref:System.Runtime.Serialization.IExtensibleDataObject> . Se non si ha alcun controllo sui tipi, impostare il parametro `ignoreExtensionDataObject` su `true` per ottenere lo stesso effetto.  
  
### <a name="object-graph-preservation"></a>Conservazione dell'oggetto grafico  
 In genere, il serializzatore non si preoccupa dell'identità dell'oggetto, come illustrato nel codice seguente.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#6)]
 [!code-vb[c_StandaloneDataContractSerializer#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#6)]  
  
 Nel codice seguente viene creato un ordine di acquisto.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#7)]
 [!code-vb[c_StandaloneDataContractSerializer#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#7)]  
  
 Si noti che i campi `billTo` e `shipTo` sono impostati sulla stessa istanza dell'oggetto. L'XML generato, tuttavia, duplica le informazioni duplicate ed è simile all'XML seguente.  
  
```xml  
<PurchaseOrder>  
  <billTo><street>123 Main St.</street></billTo>  
  <shipTo><street>123 Main St.</street></shipTo>  
</PurchaseOrder>  
```  
  
 Questo approccio ha tuttavia le caratteristiche seguenti, che potrebbero essere indesiderate:  
  
- Prestazioni. Replicare i dati non è efficiente.  
  
- Riferimenti circolari. Se gli oggetti fanno riferimento a se stessi, anche tramite altri oggetti, la serializzazione tramite la replica comporta un ciclo infinito. In questo caso, il serializzatore genera una <xref:System.Runtime.Serialization.SerializationException> .  
  
- Semantica. Talvolta è importante mantenere due riferimenti allo stesso oggetto e non a due oggetti identici.  
  
 Per queste ragioni, alcuni overload del costruttore `DataContractSerializer` hanno un parametro `preserveObjectReferences` (l'impostazione predefinita è `false`). Quando questo parametro è impostato su `true` , viene utilizzato un metodo speciale per codificare i riferimenti agli oggetti, che solo WCF riconosce. Quando è impostato su `true`, l'esempio di codice XML è simile al seguente.  
  
```xml  
<PurchaseOrder ser:id="1">  
  <billTo ser:id="2"><street ser:id="3">123 Main St.</street></billTo>  
  <shipTo ser:ref="2"/>  
</PurchaseOrder>  
```  
  
 Lo spazio dei nomi "ser" si riferisce allo spazio dei nomi di serializzazione standard `http://schemas.microsoft.com/2003/10/Serialization/` . Ogni blocco di dati viene serializzato solo una volta e gli viene fornito un numero ID. Gli utilizzi successivi comportano un riferimento ai dati già serializzati.  
  
> [!IMPORTANT]
> Se entrambi gli attributi "id" e "ref" sono presenti nel contratto dati `XMLElement`, l'attributo "ref" viene rispettato e l'attributo "id" viene ignorato.  
  
 È importante capire le limitazioni di questa modalità:  
  
- L'XML prodotto da `DataContractSerializer` con `preserveObjectReferences` impostato su `true` non è interoperativo con nessun'altra tecnologia ed è possibile accedervi solo da un'altra istanza `DataContractSerializer` , anche con `preserveObjectReferences` impostato su `true`.  
  
- Non esiste supporto di metadati (schema) per questa funzionalità. Lo schema prodotto è valido solo quando `preserveObjectReferences` è impostato su `false`.  
  
- Questa funzionalità può rallentare il processo di serializzazione e di deserializzazione. Anche se i dati non devono essere replicati, i confronti degli oggetti aggiuntivi devono essere eseguiti in questa modalità.  
  
> [!CAUTION]
> Quando la modalità `preserveObjectReferences` è attivata, è particolarmente importante impostare il valore `maxItemsInObjectGraph` sulla quota corretta. A causa del modo in cui le matrici sono gestite in questa modalità, è facile per l'autore di un attacco costruire un piccolo messaggio dannoso che comporta un grande consumo di memoria limitato solo dalla quota `maxItemsInObjectGraph` .  
  
### <a name="specifying-a-data-contract-surrogate"></a>Specifica di un surrogato del contratto dati  
 Alcuni overload del costruttore `DataContractSerializer` hanno un parametro `dataContractSurrogate` che può essere impostato su `null`. In caso contrario, è possibile utilizzarlo per specificare un *surrogato del contratto dati*che è un tipo che implementa l'interfaccia <xref:System.Runtime.Serialization.IDataContractSurrogate> . È quindi possibile utilizzare l'interfaccia per personalizzare il processo di serializzazione e di deserializzazione. Per ulteriori informazioni, vedere [surrogati del contratto dati](../extending/data-contract-surrogates.md).  
  
## <a name="serialization"></a>Serializzazione  
 Le informazioni seguenti si applicano a qualsiasi classe che eredita da <xref:System.Runtime.Serialization.XmlObjectSerializer>, incluse le classi <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Runtime.Serialization.NetDataContractSerializer> .  
  
### <a name="simple-serialization"></a>Serializzazione semplice  
 La modalità più elementare per serializzare un oggetto consiste nel passarlo al metodo <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> . Esistono tre overload, per scrivere rispettivamente in un <xref:System.IO.Stream>, in un <xref:System.Xml.XmlWriter>o in un <xref:System.Xml.XmlDictionaryWriter>. Con l'overload <xref:System.IO.Stream> , l'output è XML nella codifica UTF-8. Con l'overload <xref:System.Xml.XmlDictionaryWriter> , il serializzatore ottimizza l'output per XML binario.  
  
 Quando si usa il <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> metodo, il serializzatore usa il nome e lo spazio dei nomi predefiniti per l'elemento wrapper e lo scrive insieme al contenuto (vedere la sezione precedente "specifica del nome e dello spazio dei nomi radice predefiniti").  
  
 Nell'esempio seguente viene illustrato come scrivere con <xref:System.Xml.XmlDictionaryWriter>.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#8)]
 [!code-vb[c_StandaloneDataContractSerializer#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#8)]  
  
 Viene prodotto un XML simile al seguente.  
  
```xml  
<Person>  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</Person>  
```  
  
### <a name="step-by-step-serialization"></a>Serializzazione dettagliata  
 Utilizzare i metodi <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A>, <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObjectContent%2A>e <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> rispettivamente per scrivere l'elemento finale, scrivere il contenuto dell'oggetto e chiudere l'elemento wrapper.  
  
> [!NOTE]
> Non esistono overload <xref:System.IO.Stream> di questi metodi.  
  
 Questa serializzazione dettagliata ha due utilizzi comuni. Nel primo caso, viene utilizzata per inserire contenuto, ad esempio attributi o commenti tra `WriteStartObject` e `WriteObjectContent`, come illustrato nell'esempio seguente.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#9)]
 [!code-vb[c_StandaloneDataContractSerializer#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#9)]  
  
 Viene prodotto un XML simile al seguente.  
  
```xml  
<Person serializedBy="myCode">  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</Person>  
```  
  
 Nel secondo caso, viene utilizzata per evitare di utilizzare <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A> e <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> e scrivere l'elemento wrapper personalizzato (o per evitare di scrivere un wrapper), come illustrato nel codice seguente.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#10)]
 [!code-vb[c_StandaloneDataContractSerializer#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#10)]  
  
 Viene prodotto un XML simile al seguente.  
  
```xml  
<MyCustomWrapper>  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</MyCustomWrapper>  
```  
  
> [!NOTE]
> L'utilizzo della serializzazione dettagliata può comportare un XML di schema non valido.  
  
## <a name="deserialization"></a>Deserializzazione  
 Le informazioni seguenti si applicano a qualsiasi classe che eredita da <xref:System.Runtime.Serialization.XmlObjectSerializer>, incluse le classi <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Runtime.Serialization.NetDataContractSerializer> .  
  
 La modalità più elementare per deserializzare un oggetto consiste nel chiamare uno degli overload del metodo <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> . Esistono tre overload, rispettivamente per la lettura con un <xref:System.Xml.XmlDictionaryReader>, un `XmlReader`o un `Stream`. Si noti che l'overload `Stream` crea un <xref:System.Xml.XmlDictionaryReader> testuale che non è protetto da nessuna quota e deve essere utilizzato solo per leggere dati attendibili.  
  
 Si noti inoltre che è necessario eseguire il cast dell'oggetto restituito dal metodo `ReadObject` sul tipo appropriato.  
  
 Nel codice seguente viene creata un'istanza di <xref:System.Runtime.Serialization.DataContractSerializer> e di <xref:System.Xml.XmlDictionaryReader>, quindi viene deserializzata un'istanza `Person` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#11)]
 [!code-vb[c_StandaloneDataContractSerializer#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#11)]  
  
 Prima di chiamare il metodo <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> , posizionare il lettore XML sull'elemento wrapper o su un nodo non di contenuto che precede l'elemento wrapper. A tale fine, chiamare il metodo <xref:System.Xml.XmlReader.Read%2A> di <xref:System.Xml.XmlReader> o la sua derivazione e testare <xref:System.Xml.XmlReader.NodeType%2A>, come illustrato nel codice seguente.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#12)]
 [!code-vb[c_StandaloneDataContractSerializer#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#12)]  
  
 Si noti che è possibile leggere gli attributi in questo elemento wrapper prima di passare il lettore a `ReadObject`.  
  
 Quando si usa uno degli `ReadObject` Overload semplici, il deserializzatore cerca il nome e lo spazio dei nomi predefiniti nell'elemento wrapper (vedere la sezione precedente, "specificando il nome e lo spazio dei nomi radice predefiniti") e genera un'eccezione se trova un elemento sconosciuto. Nell'esempio precedente è previsto l'elemento wrapper `<Person>` . Per verificare che il lettore sia posizionato su un elemento denominato come previsto, viene chiamato il metodo <xref:System.Runtime.Serialization.XmlObjectSerializer.IsStartObject%2A> .  
  
 Il controllo del nome di un elemento wrapper può essere disattivato. Alcuni overload del metodo `ReadObject` prendono il parametro booleano `verifyObjectName`, la cui impostazione predefinita è `true` . Quando è impostato su `false`, il nome e lo spazio dei nomi dell'elemento wrapper vengono ignorati. Ciò è utile per leggere l'XML scritto utilizzando il meccanismo di serializzazione dettagliata descritto in precedenza.  
  
## <a name="using-the-netdatacontractserializer"></a>Utilizzo di NetDataContractSerializer  
 La differenza principale tra `DataContractSerializer` e <xref:System.Runtime.Serialization.NetDataContractSerializer> è che `DataContractSerializer` Usa i nomi di contratto dati, mentre restituisce i `NetDataContractSerializer` nomi di assembly e di tipo completi .NET Framework nel codice XML serializzato. Ciò significa che devono essere condivisi esattamente gli stessi tipi tra gli endpoint di serializzazione e di deserializzazione. Il meccanismo dei tipi noti non è pertanto richiesto con `NetDataContractSerializer` perché i tipi esatti da deserializzare sono sempre conosciuti.  
  
 Possono tuttavia verificarsi numerosi problemi:  
  
- Sicurezza. Viene caricato qualsiasi tipo trovato nell'XML che viene deserializzato. Questo comportamento può essere sfruttato per forzare il caricamento di tipi dannosi. È consigliabile utilizzare `NetDataContractSerializer` con dati non attendibili solo se viene utilizzato un *gestore di associazione della serializzazione* (tramite la proprietà <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder%2A> o il parametro del costruttore). Il gestore di associazione consente che vengano caricati solo i tipi sicuri. Il meccanismo del gestore di associazione è identico a quello utilizzato dai tipi nello spazio dei nomi <xref:System.Runtime.Serialization> .  
  
- Controllo delle versioni. L'utilizzo di nomi di assembly e di tipo completi nell'XML limita rigidamente il modo in cui è possibile controllare le versioni dei tipi. Non è possibile modificare gli elementi seguenti: nomi dei tipi, spazi dei nomi, nomi degli assembly e versioni degli assembly. L'impostazione della proprietà <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> o del parametro del costruttore su <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle.Simple> anziché sul valore predefinito di <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle.Full> consente di modificare la versione dell'assembly, fatta eccezione per i tipi di parametro generici.  
  
- Interoperabilità. Poiché i nomi dei tipi e degli assembly .NET Framework sono inclusi nel codice XML, le piattaforme diverse da .NET Framework non possono accedere ai dati risultanti.  
  
- Prestazioni. La scrittura dei nomi di tipi e assembly aumenta notevolmente le dimensioni dell'XML risultante.  
  
 Questo meccanismo è simile alla serializzazione SOAP o binaria utilizzata da .NET Framework comunicazione remota (in particolare, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> e <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ).  
  
 L'utilizzo di `NetDataContractSerializer` è simile a quello di `DataContractSerializer`, tranne che per le differenze seguenti:  
  
- I costruttori non richiedono che venga specificato un tipo radice. È possibile serializzare qualsiasi tipo con la stessa istanza di `NetDataContractSerializer`.  
  
- I costruttori non accettano un elenco di tipi noti. Il meccanismo dei tipi noti è non necessario se i nomi dei tipi sono serializzati nell'XML.  
  
- I costruttori non accettano un surrogato del contratto dati. Accettano invece un parametro <xref:System.Runtime.Serialization.ISurrogateSelector> chiamato `surrogateSelector` (che esegue il mapping alla proprietà <xref:System.Runtime.Serialization.NetDataContractSerializer.SurrogateSelector%2A> ). Si tratta di un meccanismo surrogato legacy.  
  
- Il costruttore accetta un parametro chiamato `assemblyFormat` di <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> che esegue il mapping alla proprietà <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> . Come illustrato in precedenza, ciò può essere utilizzato per migliorare le funzionalità di controllo delle versioni del serializzatore. È identico al meccanismo <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> nella serializzazione SOAP o binaria.  
  
- Il costruttore accetta un parametro <xref:System.Runtime.Serialization.StreamingContext> chiamato `context` che esegue il mapping alla proprietà <xref:System.Runtime.Serialization.NetDataContractSerializer.Context%2A> . È possibile utilizzare questa funzionalità per passare informazioni nei tipi serializzati. Questo utilizzo è identico a quello del meccanismo <xref:System.Runtime.Serialization.StreamingContext> utilizzato in altre classi <xref:System.Runtime.Serialization> .  
  
- I metodi <xref:System.Runtime.Serialization.NetDataContractSerializer.Serialize%2A> e <xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize%2A> sono alias per i metodi <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> e <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> . Hanno la funzione di fornire un modello di programmazione più coerente con la serializzazione SOAP o binaria.  
  
 Per ulteriori informazioni su queste funzionalità, vedere [serializzazione binaria](../../../standard/serialization/binary-serialization.md).  
  
 I formati XML utilizzati da `NetDataContractSerializer` e `DataContractSerializer` in genere non sono compatibili. Ciò significa che non è consentito eseguire la serializzazione con uno di questi serializzatori e la deserializzazione con l'altro.  
  
 Si noti inoltre che non `NetDataContractSerializer` viene restituito il tipo di .NET Framework completo e il nome dell'assembly per ogni nodo nell'oggetto grafico. Restituisce queste informazioni solo in caso di ambiguità. Ovvero, a livello dell'oggetto radice e per il qualsiasi caso polimorfico.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.NetDataContractSerializer>
- <xref:System.Runtime.Serialization.XmlObjectSerializer>
- [Serializzazione binaria](../../../standard/serialization/binary-serialization.md)
- [Tipi supportati dal serializzatore dei contratti dati](types-supported-by-the-data-contract-serializer.md)
