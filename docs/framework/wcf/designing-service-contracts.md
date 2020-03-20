---
title: Progettazione dei contratti di servizio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF]
ms.assetid: 8e89cbb9-ac84-4f0d-85ef-0eb6be0022fd
ms.openlocfilehash: 37723011d69e8ea2ead3f7a30a30898dede054cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176682"
---
# <a name="designing-service-contracts"></a>Progettazione dei contratti di servizio
In questo argomento vengono descritti i contratti di servizio, la relativa modalità di definizione, le operazioni disponibili (e le implicazioni per gli scambi di messaggi sottostanti), i tipi di dati utilizzati e altri temi che consentono di progettare operazioni in linea con i requisiti del proprio scenario.  
  
## <a name="creating-a-service-contract"></a>Creazione di un contratto di servizio  
 I servizi espongono una serie di operazioni. Nelle applicazioni Windows Communication Foundation (WCF) definire le operazioni creando <xref:System.ServiceModel.OperationContractAttribute> un metodo e contrassegnandolo con l'attributo . Quindi, per creare un contratto di servizio, si raggruppano le operazioni, dichiarandole all'interno di un'interfaccia contrassegnata con l'attributo <xref:System.ServiceModel.ServiceContractAttribute> oppure definendole in una classe contrassegnata con lo stesso attributo. Per un esempio di base, vedere [Procedura: definire un contratto](how-to-define-a-wcf-service-contract.md)di assistenza.  
  
 Tutti i metodi che <xref:System.ServiceModel.OperationContractAttribute> non dispongono di un attributo non sono operazioni del servizio e non sono esposti dai servizi WCF.  
  
 In questo argomento vengono descritte le decisioni seguenti da prendere durante la progettazione di un contratto di servizio:  
  
- Utilizzo di classi o interfacce.  
  
- Modalità di indicazione dei tipi di dati che si desidera scambiare.  
  
- Tipi di modello di scambio che è possibile usare.  
  
- Possibilità di inserimento nel contratto di requisiti di sicurezza espliciti.  
  
- Restrizioni per input e output dell'operazione.  
  
## <a name="classes-or-interfaces"></a>Classi o interfacce  
 Sia le classi che le interfacce rappresentano un raggruppamento di funzionalità e, pertanto, entrambi possono essere utilizzati per definire un contratto di servizio WCF. È tuttavia consigliabile utilizzare le interfacce dal momento che modellano direttamente i contratti di servizio. Senza implementazione, le interfacce si limitano a definire un raggruppamento di metodi con determinate firme. Implementare un'interfaccia del contratto di servizio ed è stato implementato un servizio WCF.  
  
 Le interfacce del contratto di servizio assumono tutti i vantaggi delle interfacce gestite:  
  
- Le interfacce del contratto di servizio possono estendere un numero qualsiasi di altre interfacce del contratto di servizio.  
  
- Una sola classe è in grado di implementare più contratti di servizio implementandone le interfacce.  
  
- È possibile modificare l'implementazione di un contratto di servizio modificando l'implementazione dell'interfaccia mentre il contratto di servizio rimane lo stesso.  
  
- È possibile modificare la versione del servizio implementando l'interfaccia obsoleta e l'interfaccia nuova. I client obsoleti si connettono alla versione originale mentre i client più recenti possono connettersi alla versione nuova.  
  
> [!NOTE]
> Quando si eredita da altre interfacce del contratto di servizio, non è possibile eseguire l'override delle proprietà dell'operazione, ad esempio il nome o lo spazio dei nomi. Se si tenta di farlo, si crea una nuova operazione nel contratto di servizio corrente.  
  
 Per un esempio di utilizzo di un'interfaccia per creare un contratto di servizio, vedere [Procedura: creare un servizio con un'interfaccia del contratto](./feature-details/how-to-create-a-service-with-a-contract-interface.md).  
  
 È tuttavia possibile utilizzare una classe per definire un contratto di servizio e contemporaneamente implementare il contratto. Il vantaggio della creazione dei servizi applicando direttamente <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> rispettivamente alla classe e ai metodi della classe è rappresentano dalla velocità e dalla semplicità. Gli svantaggi consistono nel fatto che le classi gestite non supportano l'ereditarietà multipla e di conseguenza possono implementare solo un contratto di servizio alla volta. Qualsiasi modifica alle firme della classe o del metodo, inoltre, modifica il contratto pubblico per quel servizio impedendo potenzialmente ai client non modificati di utilizzare il servizio. Per ulteriori informazioni, vedere [Implementazione di contratti](implementing-service-contracts.md)di servizio .  
  
 Per un esempio in cui viene utilizzata una classe per creare un contratto di servizio e implementarlo contemporaneamente, vedere [Procedura: creare un servizio con una classe Contract](./feature-details/how-to-create-a-wcf-contract-with-a-class.md).  
  
 A questo punto è necessario capire la differenza tra definire il contratto di servizio utilizzando un'interfaccia e utilizzare una classe. Il passaggio successivo consiste nel decidere quali dati possono essere scambiati tra un servizio e i relativi client.  
  
## <a name="parameters-and-return-values"></a>Parametri e valori restituiti  
 Ogni operazione presenta un valore restituito e un parametro, anche se soltanto `void`. Diversamente da un metodo locale, tuttavia, nel quale è possibile passare riferimenti a oggetti da un oggetto all'altro, le operazioni del servizio non passano riferimenti agli oggetti. In realtà passano copie degli oggetti.  
  
 Ciò è significativo poiché ogni tipo utilizzato in un parametro o valore restituito deve essere serializzabile, ovvero deve essere possibile convertire un oggetto di quel tipo in un flusso di byte e un flusso di byte in un oggetto.  
  
 I tipi primitivi sono serializzabili per impostazione predefinita, come molti tipi in .NET Framework.  
  
> [!NOTE]
> Il valore dei nomi di parametro nella firma dell'operazione fa parte del contratto e supporta la distinzione tra maiuscole e minuscole. Se si desidera utilizzare localmente lo stesso nome di parametro ma modificarlo nei metadati pubblicati, vedere <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>.  
  
#### <a name="data-contracts"></a>Contratti dati  
 Le applicazioni orientate ai servizi come le applicazioni Windows Communication Foundation (WCF) sono progettate per interagire con il maggior numero possibile di applicazioni client su piattaforme Microsoft e non Microsoft. Poiché l'interazione sia la più ampia possibile, è consigliabile contrassegnare i tipi con gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> per creare un contratto dati, parte del contratto di servizio che descrive i dati scambiati nelle operazioni del servizio.  
  
 I contratti dati sono contratti di tipo con consenso esplicito: nessun tipo o membro dati viene serializzato a meno che non si applichi in modo esplicito l'attributo del contratto dati. I contratti dati non sono correlati all'ambito di accesso del codice gestito: i membri dati privati possono essere serializzati e inviati altrove perché vi si possa accedere pubblicamente. Per un esempio di base di un contratto dati, vedere [Procedura: creare un contratto dati di base per una classe o](./feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)una struttura. WCF gestisce la definizione dei messaggi SOAP sottostanti che abilitano la funzionalità dell'operazione, nonché la serializzazione dei tipi di dati all'esterno e all'esterno del corpo dei messaggi. Purché i tipi di dati siano serializzabili, non è necessario occuparsi dell'infrastruttura dello scambio di messaggi sottostante durante la progettazione delle operazioni.  
  
 Anche se l'applicazione <xref:System.Runtime.Serialization.DataContractAttribute> <xref:System.Runtime.Serialization.DataMemberAttribute> WCF tipica utilizza gli attributi e per creare contratti dati per le operazioni, è possibile usare altri meccanismi di serializzazione. I meccanismi <xref:System.Runtime.Serialization.ISerializable>, <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.IXmlSerializable> standard gestiscono tutti la serializzazione dei tipi di dati nei messaggi SOAP sottostanti che li trasportano da un'applicazione all'altra. È possibile utilizzare più strategie di serializzazione se i tipi di dati richiedono un supporto speciale. Per altre informazioni sulle opzioni per la serializzazione dei tipi di dati nelle applicazioni WCF, vedere Specifica del trasferimento dei [dati nei contratti](./feature-details/specifying-data-transfer-in-service-contracts.md)di servizio .  
  
#### <a name="mapping-parameters-and-return-values-to-message-exchanges"></a>Esecuzione del mapping di parametri e valori restituiti agli scambi di messaggi  
 Le operazioni del servizio sono supportate da uno scambio sottostante di messaggi SOAP che trasferiscono i dati dell'applicazione avanti e indietro, oltre ai dati necessari per l'applicazione per supportare alcune funzionalità standard di sicurezza, transazione e correlate alla sessione. Poiché questo è il caso, la firma di un'operazione del servizio determina un determinato modello di *scambio* di messaggi sottostante (MEP) che può supportare il trasferimento dei dati e le funzionalità richieste da un'operazione. È possibile specificare tre modelli nel modello di programmazione WCF: modelli di messaggio di richiesta/risposta, unidirezionali e duplex.  
  
##### <a name="requestreply"></a>Request/Reply  
 Nel modello Request/Reply il mittente di una richiesta (un'applicazione client) riceve una risposta alla quale è correlata la richiesta. Si tratta del modello di scambio dei messaggi predefinito perché supporta un'operazione in cui uno o più parametri vengono passati all'operazione e un valore restituito viene passato di nuovo al chiamante. Nell'esempio di codice C# seguente viene illustrata un'operazione di base del servizio che accetta una stringa e restituisce una stringa.  
  
```csharp  
[OperationContractAttribute]  
string Hello(string greeting);  
```  
  
 Il codice seguente è l'equivalente del codice Visual Basic.  
  
```vb  
<OperationContractAttribute()>  
Function Hello (ByVal greeting As String) As String  
```  
  
 Questa firma dell'operazione determina la forma dello scambio di messaggi sottostante. Se non esisteva alcuna correlazione, WCF non è in grado di determinare per quale operazione è destinato il valore restituito.  
  
 Si noti che, a meno che non `void` si`Nothing` specifichi un modello di messaggio sottostante diverso, anche le operazioni del servizio che restituiscono ( in Visual Basic) sono scambi di messaggi di richiesta/risposta. Il risultato per l'operazione è che, a meno che un client non richiami l'operazione in modo asincrono, il client interrompe l'elaborazione fino alla ricezione del messaggio di risposta, anche se normalmente si tratta di un messaggio vuoto. Nell'esempio di codice di C# seguente viene illustrata un'operazione che restituisce un risultato solo dopo che il client ha ricevuto un messaggio di risposta vuoto.  
  
```csharp  
[OperationContractAttribute]  
void Hello(string greeting);  
```  
  
 Il codice seguente è l'equivalente del codice Visual Basic.  
  
```vb  
<OperationContractAttribute()>  
Sub Hello (ByVal greeting As String)  
```  
  
 L'esempio precedente può rallentare le prestazioni e la velocità di risposta del client se l'esecuzione dell'operazione richiede molto tempo, tuttavia le operazioni Request/Reply presentano vantaggi anche quando restituiscono `void`. Il vantaggio più ovvio consiste nel fatto che gli errori SOAP possono essere restituiti nel messaggio di risposta, a indicare che si è verificata una condizione di errore correlata al servizio, nella comunicazione o nell'elaborazione. Gli errori SOAP specificati in un contratto di servizio vengono passati all'applicazione client sotto forma di oggetto <xref:System.ServiceModel.FaultException%601>, dove il parametro tipo è il tipo specificato nel contratto di servizio. In questo modo la notifica ai client sulle condizioni di errore nei servizi WCF è semplice. Per ulteriori informazioni sulle eccezioni, gli errori SOAP e la gestione degli errori, vedere [Specifica e gestione degli errori in contratti e servizi](specifying-and-handling-faults-in-contracts-and-services.md). Per un esempio di servizio e client di richiesta/risposta, vedere [Procedura: creare un contratto di richiesta-risposta](./feature-details/how-to-create-a-request-reply-contract.md). Per ulteriori informazioni sui problemi relativi al modello di richiesta-risposta, vedere [Servizi di richiesta-risposta](./feature-details/request-reply-services.md).  
  
##### <a name="one-way"></a>Unidirezionale  
 Se il client di un'applicazione di servizio WCF non deve attendere il completamento dell'operazione e non elabora errori SOAP, l'operazione può specificare un modello di messaggio unidirezionale. Un'operazione unidirezionale è un'operazione in cui un client richiama un'operazione e continua l'elaborazione dopo che WCF scrive il messaggio nella rete. In genere ciò significa che, a meno che le dimensioni dei dati inviati nel messaggio in uscita non siano eccessive, il client continua l'esecuzione quasi immediatamente (purché non si verifichi un errore durante l'invio dei dati). Questo tipo di modello di scambio dei messaggi supporta il comportamento simile a quello degli eventi da un client a un'applicazione di servizio.  
  
 Uno scambio di messaggi in cui un messaggio viene inviato e non ne viene ricevuto nessuno non è in grado di supportare un'operazione del servizio che specifichi un valore restituito diverso da `void`, nel quale caso viene generata un'eccezione <xref:System.InvalidOperationException>.  
  
 L'assenza di messaggi di risposta implica inoltre che non verranno restituite segnalazioni SOAP per indicare eventuali errori durante l'elaborazione o la comunicazione (la comunicazione di informazioni sull'errore quando le operazioni sono unidirezionali richiede un modello di scambio dei messaggi duplex).  
  
 Per specificare uno scambio di messaggi unidirezionale per un'operazione che restituisce `void`, impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> su `true`, come nell'esempio di codice C# seguente.  
  
```csharp  
[OperationContractAttribute(IsOneWay=true)]  
void Hello(string greeting);  
```  
  
 Il codice seguente è l'equivalente del codice Visual Basic.  
  
```vb  
<OperationContractAttribute(IsOneWay := True)>  
Sub Hello (ByVal greeting As String)  
```  
  
 Questo metodo è identico all'esempio Request/Reply precedente ma impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> su `true` implica che sebbene il metodo sia identico, l'operazione del servizio non invia un messaggio di risposta e i client rispondono immediatamente dopo l'invio del messaggio in uscita al livello del canale. Per un esempio, vedere [Procedura: creare un contratto unidirezionale](./feature-details/how-to-create-a-one-way-contract.md). Per ulteriori informazioni sul modello unidirezionale, vedere [Servizi unidirezionali](./feature-details/one-way-services.md).  
  
##### <a name="duplex"></a>Duplex  
 Un modello duplex è caratterizzato dalla possibilità del servizio e del client di inviarsi reciprocamente messaggi indipendentemente dal modello usato, unidirezionale o Request/Reply. Questa forma di comunicazione bidirezionale è utile per i servizi con la necessità di comunicare direttamente con il client o per consentire un'esperienza asincrona a entrambe le estremità dello scambio di messaggi, compreso il comportamento simile a quello degli eventi.  
  
 Il modello duplex è leggermente più complesso del modello Request/Reply o del modello unidirezionale a causa del meccanismo supplementare di comunicazione con il client.  
  
 Per progettare un contratto duplex, è inoltre necessario progettare un contratto callback e assegnare il tipo di tale contratto callback alla proprietà <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> dell'attributo <xref:System.ServiceModel.ServiceContractAttribute> che contrassegna il contratto di servizio.  
  
 Per implementare un modello duplex è necessario creare una seconda interfaccia contenente le dichiarazioni del metodo chiamate sul client.  
  
 Per un esempio di creazione di un servizio e un client che accede a tale servizio, vedere [Procedura: creare un contratto duplex](./feature-details/how-to-create-a-duplex-contract.md) e [Procedura: accedere ai servizi con un contratto duplex](./feature-details/how-to-access-services-with-a-duplex-contract.md). Per un esempio di lavoro, vedere [Duplex](./samples/duplex.md). Per ulteriori informazioni sui problemi relativi all'utilizzo di contratti duplex, vedere [Servizi duplex](./feature-details/duplex-services.md).  
  
> [!CAUTION]
> Quando un servizio riceve un messaggio duplex, analizza l'elemento `ReplyTo` contenuto nel messaggio in arrivo per stabilire dove inviare la replica. Se il canale utilizzato per ricevere il messaggio non è protetto, un client non attendibile potrebbe inviare un messaggio dannoso con un `ReplyTo` di un computer di destinazione, sfociando in un Denial of Service (DoS) del computer di destinazione.  
  
##### <a name="out-and-ref-parameters"></a>Parametri Out e Ref  
 Nella maggior parte dei `in` casi, è possibile `out` `ref` utilizzare`ByRef` parametri (`ByVal` in Visual Basic) e parametri ( in Visual Basic). Poiché i parametri `out` e `ref` indicano entrambi che un'operazione restituisce dati, una firma dell'operazione come la seguente specifica che un'operazione Request/Reply è necessaria anche se la firma dell'operazione restituisce `void`.  
  
```csharp  
[ServiceContractAttribute]  
public interface IMyContract  
{  
  [OperationContractAttribute]  
  public void PopulateData(ref CustomDataType data);  
}  
```  
  
 Il codice seguente è l'equivalente del codice Visual Basic.  
  
```vb  
<ServiceContractAttribute()> _  
Public Interface IMyContract  
  <OperationContractAttribute()> _  
  Public Sub PopulateData(ByRef data As CustomDataType)  
End Interface  
```  
  
 Le uniche eccezioni sono costituite dai casi in cui la firma presenta una struttura particolare. È ad esempio possibile utilizzare l'associazione <xref:System.ServiceModel.NetMsmqBinding> per comunicare con i client solo se il metodo utilizzato per dichiarare un'operazione restituisce `void`. Non sono possibili valori di output, che si tratti di un valore restituito o di un parametro `ref` o `out`.  
  
 Utilizzando il parametro `out` o `ref`, inoltre, è necessario che l'operazione disponga di un messaggio di risposta sottostante per trasportare di nuovo l'oggetto modificato. Se l'operazione è unidirezionale, in fase di esecuzione viene generata un'eccezione <xref:System.InvalidOperationException>.  
  
### <a name="specify-message-protection-level-on-the-contract"></a>Specificare il livello di sicurezza del messaggio sul contratto  
 Durante la progettazione del contratto è inoltre necessario decidere il livello di sicurezza del messaggio dei servizi che implementano il contratto. È necessario solo se la protezione del messaggio è applicata all'associazione nell'endpoint del contratto. Se nell'associazione la protezione è disattivata (ovvero se l'associazione fornita dal sistema imposta <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType> sul valore <xref:System.ServiceModel.SecurityMode.None?displayProperty=nameWithType>), non è necessario formulare una decisione sul livello di sicurezza del messaggio per il contratto. Nella maggior parte dei casi le associazioni fornite dal sistema in cui è applicata la protezione a livello di messaggio forniscono un livello di sicurezza sufficiente e non è necessario prendere in considerazione il livello di sicurezza per operazione o per messaggio.  
  
 Il livello di sicurezza è un valore che specifica se i messaggi (o parti del messaggio) che supportano un servizio sono firmati, firmati e crittografati o inviati senza firma né crittografia. Il livello di sicurezza può essere impostato su vari ambiti: a livello di servizio, per un'operazione in particolare, per un messaggio all'interno dell'operazione o per una parte del messaggio. I valori impostati in un ambito diventano predefiniti per ambiti più ristretti, tranne quando sono sottoposti a override in modo esplicito. Se la configurazione di un'associazione non è in grado di fornire il livello di sicurezza minimo necessario per il contratto, viene generata un'eccezione. Quando, inoltre, nessun valore del livello di sicurezza è impostato in modo esplicito nel contratto, la configurazione dell'associazione controlla il livello di sicurezza per tutti i messaggi, se l'associazione dispone della protezione dei messaggi. Questo è il comportamento predefinito.  
  
> [!IMPORTANT]
> Decidere se impostare in modo esplicito i vari ambiti di un contratto su una protezione di <xref:System.Net.Security.ProtectionLevel.EncryptAndSign?displayProperty=nameWithType> di livello inferiore rispetto alla protezione completa, equivale solitamente a cercare un compromesso tra un certo grado di sicurezza e prestazioni maggiori. In questi casi le decisioni dipendono dalle operazioni e dal valore dei dati scambiati. Per ulteriori informazioni, vedere [Protezione dei servizi](securing-services.md).  
  
 Nell'esempio di codice seguente non viene impostata nel contratto né la proprietà <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> né la proprietà <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel%2A>.  
  
```csharp  
[ServiceContract]  
public interface ISampleService  
{  
  [OperationContractAttribute]  
  public string GetString();  
  
  [OperationContractAttribute]  
  public int GetInt();
}  
```  
  
 Il codice seguente è l'equivalente del codice Visual Basic.  
  
```vb  
<ServiceContractAttribute()> _  
Public Interface ISampleService  
  
  <OperationContractAttribute()> _  
  Public Function GetString()As String  
  
  <OperationContractAttribute()> _  
  Public Function GetData() As Integer  
  
End Interface  
```  
  
 Durante l'interazione con un'implementazione `ISampleService` in un endpoint con un <xref:System.ServiceModel.WSHttpBinding> predefinito (l'elemento <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType> predefinito, ovvero <xref:System.ServiceModel.SecurityMode.Message>), tutti i messaggi sono crittografati e firmati poiché questo è il livello di sicurezza predefinito. Tuttavia, quando un servizio `ISampleService` viene utilizzato con un oggetto <xref:System.ServiceModel.BasicHttpBinding> predefinito (l'oggetto <xref:System.ServiceModel.SecurityMode> predefinito, ovvero <xref:System.ServiceModel.SecurityMode.None>), tutti i messaggi vengono inviati come testo poiché non è disponibile alcuna protezione per questa associazione, di conseguenza il livello di sicurezza viene ignorato (ovvero i messaggi non vengono crittografati né firmati). Se l'elemento <xref:System.ServiceModel.SecurityMode> fosse impostato su <xref:System.ServiceModel.SecurityMode.Message>, i messaggi verrebbero crittografati e firmati (perché tale sarebbe il livello di sicurezza predefinito dell'associazione).  
  
 Se si desidera regolare o specificare in modo esplicito i requisiti di sicurezza per il contratto, impostare la proprietà <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> (o una qualsiasi delle proprietà `ProtectionLevel` in un ambito più ristretto) sul livello necessario per il contratto di servizio in questione. In questo caso, l'utilizzo di un'impostazione esplicita impone all'associazione di supportare tale impostazione almeno per l'ambito utilizzato. Nell'esempio di codice seguente viene specificato un valore <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel%2A> esplicitamente, per l'operazione `GetGuid`.  
  
```csharp  
[ServiceContract]  
public interface IExplicitProtectionLevelSampleService  
{  
  [OperationContractAttribute]  
  public string GetString();  
  
  [OperationContractAttribute(ProtectionLevel=ProtectionLevel.None)]  
  public int GetInt();
  [OperationContractAttribute(ProtectionLevel=ProtectionLevel.EncryptAndSign)]  
  public int GetGuid();
}  
```  
  
 Il codice seguente è l'equivalente del codice Visual Basic.  
  
```vb  
<ServiceContract()> _
Public Interface IExplicitProtectionLevelSampleService
    <OperationContract()> _
    Public Function GetString() As String
    End Function
  
    <OperationContract(ProtectionLevel := ProtectionLevel.None)> _
    Public Function GetInt() As Integer
    End Function
  
    <OperationContractAttribute(ProtectionLevel := ProtectionLevel.EncryptAndSign)> _
    Public Function GetGuid() As Integer
    End Function
  
End Interface  
```  
  
 Un servizio che implementa questo contratto `IExplicitProtectionLevelSampleService` e dispone di un endpoint che utilizza l'elemento <xref:System.ServiceModel.WSHttpBinding> predefinito (l'elemento <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType> predefinito, ovvero <xref:System.ServiceModel.SecurityMode.Message>) presenta il comportamento seguente:  
  
- I messaggi dell'operazione `GetString` sono crittografati e firmati.  
  
- I messaggi dell'operazione `GetInt` sono inviati come testo non crittografato né firmato, ovvero come testo normale.  
  
- L'elemento `GetGuid` dell'operazione <xref:System.Guid?displayProperty=nameWithType> viene restituito in un messaggio crittografato e firmato.  
  
 Per ulteriori informazioni sui livelli di protezione e su come utilizzarli, vedere [Informazioni sui livelli](understanding-protection-level.md)di protezione . Per ulteriori informazioni sulla sicurezza, vedere [Protezione dei servizi](securing-services.md).  
  
##### <a name="other-operation-signature-requirements"></a>Altri requisiti per la firma di un'operazione  
 Alcune funzionalità dell'applicazione richiedono un tipo particolare di firma dell'operazione. L'associazione <xref:System.ServiceModel.NetMsmqBinding>, ad esempio, supporta servizi e client durevoli in cui è possibile per un'applicazione riavviarsi durante la comunicazione e riprendere da dove era stata interrotta senza perdere messaggi. (Per altre informazioni, vedere [code in WCF](./feature-details/queues-in-wcf.md).) Tuttavia, le operazioni `in` durevoli devono accettare un solo parametro e non avere alcun valore restituito.  
  
 Un altro esempio è l'utilizzo di tipi <xref:System.IO.Stream> nelle operazioni. Poiché il parametro <xref:System.IO.Stream> comprende l'intero corpo del messaggio, se un input o un output (ovvero il parametro `ref`, il parametro `out` o il valore restituito) è di tipo <xref:System.IO.Stream>, deve essere l'unico l'input o l'unico l'output specificato nell'operazione. Il parametro o il tipo restituito, inoltre, deve essere <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> o <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType>. Per ulteriori informazioni sui flussi, vedere [Dati di grandi dimensioni e Streaming](./feature-details/large-data-and-streaming.md).  
  
##### <a name="names-namespaces-and-obfuscation"></a>Nomi, spazi dei nomi e offuscamento  
 I nomi e gli spazi dei nomi dei tipi .NET nella definizione di contratti e operazioni sono significativi quando i contratti vengono convertiti in WSDL e quando vengono creati e inviati messaggi del contratto. Di conseguenza, è consigliabile che gli spazi dei nomi e i nomi del contratto di servizio vengano impostati in modo esplicito tramite le proprietà `Name` e `Namespace` di tutti gli attributi del contratto di supporto, ad esempio <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, <xref:System.Runtime.Serialization.DataContractAttribute>,  <xref:System.Runtime.Serialization.DataMemberAttribute> e altri attributi del contratto.  
  
 Se i nomi e gli spazi dei nomi non vengono impostati in modo esplicito, una delle conseguenze sarà che l'utilizzo dell'offuscamento IL sull'assembly determinerà la modifica dei nomi e degli spazi dei nomi del tipo di contratto e genererà WSDL modificato e scambi di rete che in genere hanno esito negativo. Se i nomi e gli spazi dei nomi del contratto non vengono impostati in modo esplicito, ma si intende utilizzare l'offuscamento, utilizzare gli attributi <xref:System.Reflection.ObfuscationAttribute> e <xref:System.Reflection.ObfuscateAssemblyAttribute> per impedire la modifica dei nomi e degli spazi dei nomi del tipo di contratto.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: creare un contratto request/reply](./feature-details/how-to-create-a-request-reply-contract.md)
- [Procedura: creare un contratto unidirezionale](./feature-details/how-to-create-a-one-way-contract.md)
- [Procedura: creare un contratto duplex](./feature-details/how-to-create-a-duplex-contract.md)
- [Specifying Data Transfer in Service Contracts](./feature-details/specifying-data-transfer-in-service-contracts.md)
- [Specifica e gestione degli errori in contratti e servizi](specifying-and-handling-faults-in-contracts-and-services.md)
- [Uso di sessioni](using-sessions.md)
- [Operazioni sincrone e asincrone](synchronous-and-asynchronous-operations.md)
- [Servizi affidabili](reliable-services.md)
- [Servizi e transazioni](services-and-transactions.md)
