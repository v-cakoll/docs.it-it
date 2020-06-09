---
title: Compatibilità con la funzionalità di trust parziale
ms.date: 03/30/2017
ms.assetid: a36a540b-1606-4e63-88e0-b7c59e0e6ab7
ms.openlocfilehash: 85e34e365d125fe4f00756549ba5bda4311b78f8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579163"
---
# <a name="partial-trust-feature-compatibility"></a>Compatibilità con la funzionalità di trust parziale
Windows Communication Foundation (WCF) supporta un subset limitato di funzionalità durante l'esecuzione in un ambiente parzialmente attendibile. Le funzionalità supportate in un contesto parzialmente attendibile sono progettate sulla base di uno specifico set di scenari, come descritto nell'argomento [Supported Deployment Scenarios](supported-deployment-scenarios.md) .  
  
## <a name="minimum-permission-requirements"></a>Requisiti di autorizzazione minimi  
 WCF supporta un sottoinsieme di funzionalità in applicazioni in esecuzione con uno dei set di autorizzazioni denominati standard seguenti:  
  
- Autorizzazioni Attendibilità media  
  
- Autorizzazioni Area Internet  
  
 Il tentativo di utilizzare WCF in applicazioni parzialmente attendibili con autorizzazioni più restrittive può generare eccezioni di sicurezza in fase di esecuzione.  
  
## <a name="contracts"></a>Contratti  
 Se eseguiti in ambiente parzialmente attendibile, i contratti sono soggetti alle restrizioni seguenti:  
  
- La classe del servizio che implementa l'interfaccia `[ServiceContract]` deve essere `public` e presentare un costruttore `public` . Se definisce metodi `[OperationContract]` , questi devono essere `public`. Se invece implementa un'interfaccia `[ServiceContract]` , le implementazioni dei metodi possono essere esplicite o `private`, purché l'interfaccia `[ServiceContract]` sia `public`.  
  
- Quando si utilizza l'attributo `[ServiceKnownType]` , il metodo specificato deve essere `public`.  
  
- Le classi`[MessageContract]` e i relativi membri possono essere `public`. Se la classe `[MessageContract]` viene definita nell'assembly dell'applicazione, può essere `internal` e disporre di membri `internal` .  
  
## <a name="system-provided-bindings"></a>Associazioni fornite dal sistema  
 Le classi <xref:System.ServiceModel.BasicHttpBinding> e <xref:System.ServiceModel.WebHttpBinding> sono completamente supportate in un ambiente di trust parziale. La classe <xref:System.ServiceModel.WSHttpBinding> è supportata solo per la modalità di sicurezza trasporto.  
  
 Le associazioni che utilizzano trasporti diversi da HTTP, quali <xref:System.ServiceModel.NetTcpBinding>, <xref:System.ServiceModel.NetNamedPipeBinding>o <xref:System.ServiceModel.NetMsmqBinding>, non sono supportate in un ambiente di trust parziale.  
  
## <a name="custom-bindings"></a>Associazioni personalizzate  
 Le associazioni personalizzate possono essere create e utilizzate in ambiente parzialmente attendibile, ma devono rispettare le restrizioni specificate in questa sezione.  
  
### <a name="transports"></a>Trasporti  
 Gli unici elementi di associazione di trasporto consentiti sono <xref:System.ServiceModel.Channels.HttpTransportBindingElement> e <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
### <a name="encoders"></a>Codificatori  
 Sono consentiti i codificatori seguenti:  
  
- Codificatore di testo (<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>).  
  
- Codificatore binario (<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>).  
  
- Codificatore di messaggi Web (<xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>).  
  
 Non sono supportati codificatori MTOM (Message Transmission Optimization Mechanism).  
  
### <a name="security"></a>Sicurezza  
 Le applicazioni parzialmente attendibili possono utilizzare le funzionalità di sicurezza a livello di trasporto di WCF per proteggere la comunicazione. La sicurezza a livello di messaggio non è supportata. La configurazione di un'associazione per l'utilizzo della sicurezza a livello di messaggio genera un'eccezione in fase di esecuzione.  
  
### <a name="unsupported-bindings"></a>Associazioni non supportate  
 Le associazioni che utilizzano messaggistica affidabile, transazioni o sicurezza a livello di messaggio non sono supportate.  
  
## <a name="serialization"></a>Serializzazione  
 Entrambe le classi <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Xml.Serialization.XmlSerializer> sono supportate in un ambiente di trust parziale. Tuttavia, l'utilizzo di <xref:System.Runtime.Serialization.DataContractSerializer> è soggetto alle condizioni seguenti:  
  
- Tutti i tipi `[DataContract]` serializzabili devono essere `public`.  
  
- Tutti i campi `[DataMember]` o le proprietà in un tipo `[DataContract]` devono essere pubblici e di lettura/scrittura. La serializzazione e la deserializzazione dei campi di sola [lettura](https://go.microsoft.com/fwlink/?LinkID=98854) non sono supportate quando si esegue WCF in un'applicazione parzialmente attendibile.  
  
- Il modello di programmazione `[Serializable]`/ISerializable non è supportato in ambiente parzialmente attendibile.  
  
- I tipi noti devono essere specificati nel codice o nella configurazione a livello di computer (machine.config). I tipi noti non possono essere specificati nella configurazione a livello di applicazione per motivi di sicurezza.  
  
- I tipi che implementano <xref:System.Runtime.Serialization.IObjectReference> generano un'eccezione in un ambiente parzialmente attendibile.  
  
 Per altre informazioni sulla sicurezza quando si usa [T:System.Runtime.Serialization.DataContractSerializer](partial-trust-best-practices.md) in modo sicuro in un'applicazione in ambiente parzialmente attendibile, vedere la sezione sulla serializzazione in <xref:System.Runtime.Serialization.DataContractSerializer> .  
  
### <a name="collection-types"></a>Tipi di raccolta  
 Alcuni tipi di raccolta implementano sia <xref:System.Collections.Generic.IEnumerable%601> che <xref:System.Collections.IEnumerable>. Gli esempi includono tipi che implementano <xref:System.Collections.Generic.ICollection%601>. Tali tipi possono implementare un'implementazione `public` di `GetEnumerator()`e un'implementazione esplicita di `GetEnumerator()`. In questo caso, <xref:System.Runtime.Serialization.DataContractSerializer> richiama l'implementazione `public` di `GetEnumerator()`e non l'implementazione esplicita di `GetEnumerator()`. Se nessuna delle implementazioni di `GetEnumerator()` è `public` e tutte sono implementazioni esplicite, <xref:System.Runtime.Serialization.DataContractSerializer> richiama `IEnumerable.GetEnumerator()`.  
  
 Per i tipi di raccolta quando WCF viene eseguito in un ambiente di trust parziale, se nessuna delle `GetEnumerator()` implementazioni è `public` o se nessuna di esse sono implementazioni esplicite dell'interfaccia, viene generata un'eccezione di sicurezza.  
  
### <a name="netdatacontractserializer"></a>NetDataContractSerializer  
 Molti tipi di raccolte .NET Framework come <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ArrayList>, <xref:System.Collections.Generic.Dictionary%602> e <xref:System.Collections.Hashtable> non sono supportati da <xref:System.Runtime.Serialization.NetDataContractSerializer> in ambiente parzialmente attendibile. Per questi tipi è impostato l'attributo `[Serializable]` e, come indicato in precedenza nella sezione sulla serializzazione, questo attributo non è supportato in ambiente parzialmente attendibile. <xref:System.Runtime.Serialization.DataContractSerializer> considera le raccolte in modo particolare ed è pertanto in grado di ignorare questa restrizione, al contrario di <xref:System.Runtime.Serialization.NetDataContractSerializer> che non dispone di un meccanismo di questo tipo.  
  
 Il tipo <xref:System.DateTimeOffset> non è supportato da <xref:System.Runtime.Serialization.NetDataContractSerializer> in ambiente parzialmente attendibile.  
  
 Se l'esecuzione avviene in ambiente parzialmente attendibile, non è possibile utilizzare un surrogato con <xref:System.Runtime.Serialization.NetDataContractSerializer> (tramite il meccanismo <xref:System.Runtime.Serialization.SurrogateSelector> ). Si noti che questa restrizione si applica all'utilizzo di un surrogato, non alla relativa serializzazione.  
  
## <a name="enabling-common-behaviors-to-run"></a>Abilitazione dell'esecuzione dei comportamenti comuni  
 I comportamenti del servizio o dell'endpoint non contrassegnati con l' <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attributo (APTCA) aggiunti alla [\<commonBehaviors>](../../configure-apps/file-schema/wcf/commonbehaviors.md) sezione di un file di configurazione non vengono eseguiti quando l'applicazione viene eseguita in un ambiente con attendibilità parziale e quando si verifica questa situazione non viene generata alcuna eccezione. Per imporre l'esecuzione di comportamenti comuni, è necessario eseguire una delle operazioni seguenti:  
  
- Contrassegnare il comportamento comune con l'attributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute> in modo tale che questo possa essere eseguito se distribuito come applicazione parzialmente attendibile. Si noti che una voce di registro può essere impostata nel computer per impedire l'esecuzione delle assembly APTCA. .  
  
- Verificare che, se l'applicazione viene distribuita come completamente attendibile, gli utenti non possano modificare le impostazioni di sicurezza per l'accesso al codice per eseguire l'applicazione in ambiente parzialmente attendibile. In tal caso, il comportamento non viene eseguito e non viene generata alcuna eccezione. Per garantire questo problema, vedere l'opzione **LevelFinal** usando [Caspol. exe (strumento per i criteri di sicurezza dall'accesso di codice)](../../tools/caspol-exe-code-access-security-policy-tool.md).  
  
 Per un esempio di comportamento comune, vedere [procedura: bloccare gli endpoint nell'organizzazione](../extending/how-to-lock-down-endpoints-in-the-enterprise.md).  
  
## <a name="configuration"></a>Configurazione  
 Con un'eccezione, il codice parzialmente attendibile può caricare solo le sezioni di configurazione WCF nel `app.config` file locale. Per caricare sezioni di configurazione WCF che fanno riferimento a sezioni WCF in Machine. config o in un file Web. config radice è necessario ConfigurationPermission (Unrestricted). Senza questa autorizzazione, i riferimenti alle sezioni di configurazione WCF (comportamenti, associazioni) esterni al file di configurazione locale generano un'eccezione al momento del caricamento della configurazione.  
  
 L'unica eccezione è data dalla configurazione del tipo noto per la serializzazione, come descritto nella sezione sulla serializzazione di questo argomento.  
  
> [!IMPORTANT]
> Le estensioni di configurazione sono supportate solo quando in esecuzione sotto Attendibilità totale.  
  
## <a name="diagnostics"></a>Diagnostica  
  
### <a name="event-logging"></a>Registrazione degli eventi  
 In ambiente parzialmente attendibile la registrazione eventi limitata è supportata. Solo gli errori relativi all'attivazione del servizio e alla registrazione dei messaggi/traccia vengono registrati nel registro eventi. Per evitare che venga scritto un numero eccessivo di messaggi nel registro eventi, il numero massimo di eventi registrabili da un processo è stato impostato su 5.  
  
### <a name="message-logging"></a>Registrazione messaggi  
 La registrazione messaggi non funziona quando WCF viene eseguito in un ambiente con attendibilità parziale. In un trust parziale, l'attivazione del servizio ha esito positivo ma non viene registrato alcun messaggio.  
  
### <a name="tracing"></a>Traccia  
 La funzionalità di traccia con restrizioni è disponibile quando l'applicazione viene eseguita in un ambiente di trust parziale. Nell'elemento <`listeners`> nel file di configurazione, gli unici tipi che è possibile aggiungere sono <xref:System.Diagnostics.TextWriterTraceListener> e il nuovo <xref:System.Diagnostics.EventSchemaTraceListener> . L'utilizzo della classe <xref:System.Diagnostics.XmlWriterTraceListener> standard può generare log incompleti o non corretti.  
  
 Le origini di traccia supportate sono:  
  
- <xref:System.ServiceModel>  
  
- <xref:System.Runtime.Serialization>  
  
- <xref:System.IdentityModel.Claims>, <xref:System.IdentityModel.Policy>, <xref:System.IdentityModel.Selectors>e <xref:System.IdentityModel.Tokens>.  
  
 Le origini di traccia seguenti non sono supportate:  
  
- CardSpace  
  
- <xref:System.IO.Log>  

- [System. ServiceModel. Internal. TransactionBridge](https://docs.microsoft.com/previous-versions/aa346556(v=vs.110))]
  
 I membri seguenti dell'enumerazione <xref:System.Diagnostics.TraceOptions> non dovrebbero essere specificati:  
  
- <xref:System.Diagnostics.TraceOptions.Callstack?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceOptions.ProcessId?displayProperty=nameWithType>  
  
 Quando si utilizza la traccia in un ambiente di trust parziale, assicurare che l'applicazione disponga di autorizzazioni sufficienti per archiviare l'output del listener di traccia. Ad esempio, quando si utilizza <xref:System.Diagnostics.TextWriterTraceListener> per scrivere output di traccia in un file di testo, assicurare che l'applicazione disponga dell'autorizzazione FileIOPermission necessaria per scrivere correttamente nel file di traccia.  
  
> [!NOTE]
> Per evitare il flooding dei file di traccia con errori duplicati, WCF Disabilita la traccia della risorsa o dell'azione dopo il primo errore di sicurezza. Viene generata una traccia di eccezione per ogni accesso alla risorsa non riuscito, la prima volta che viene eseguito il tentativo di accedere alla risorsa o eseguire l'azione.  
  
## <a name="wcf-service-host"></a>Host servizio WCF  
 L'host del servizio WCF non supporta l'attendibilità parziale. Se si desidera utilizzare un servizio WCF in attendibilità parziale, non utilizzare il modello di progetto libreria di servizi WCF in Visual Studio per compilare il servizio. In alternativa, creare un nuovo sito Web in Visual Studio scegliendo il modello di sito Web del servizio WCF, che può ospitare il servizio in un server Web in cui è supportato l'attendibilità parziale WCF.  
  
## <a name="other-limitations"></a>Altre limitazioni  

  WCF è in genere limitato alle considerazioni sulla sicurezza imposte dall'applicazione host. Se, ad esempio, WCF è ospitato in un'applicazione browser XAML (XBAP), è soggetto alle limitazioni XBAP, come descritto in [Windows Presentation Foundation sicurezza con attendibilità parziale](../../wpf/wpf-partial-trust-security.md).  
  
 Se indigo2 viene eseguito in ambiente parzialmente attendibile, le funzionalità aggiuntive seguenti non vengono abilitate:  
  
- Strumentazione gestione Windows (WMI, Windows Management Instrumentation)  
  
- La registrazione eventi è abilitata solo parzialmente (vedere la discussione nella sezione **Diagnostica** ).  
  
- Contatori delle prestazioni  
  
 L'utilizzo di funzionalità WCF che non sono supportate in un ambiente di trust parziale può generare eccezioni in fase di esecuzione.  
  
## <a name="unlisted-features"></a>Funzionalità non elencate  
 Il modo migliore per individuare se un'informazione non è disponibile in modalità di esecuzione in un ambiente di trust parziale è tentare di accedere alla risorsa o di eseguire l'azione all'interno di un blocco `try` e quindi eseguire il `catch` dell'errore. Per evitare il flooding dei file di traccia con errori duplicati, WCF Disabilita la traccia della risorsa o dell'azione dopo il primo errore di sicurezza. Viene generata una traccia di eccezione per ogni accesso alla risorsa non riuscito, la prima volta che viene eseguito il tentativo di accedere alla risorsa o eseguire l'azione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [Supported Deployment Scenarios](supported-deployment-scenarios.md)
- [T:System.Runtime.Serialization.DataContractSerializer](partial-trust-best-practices.md)
