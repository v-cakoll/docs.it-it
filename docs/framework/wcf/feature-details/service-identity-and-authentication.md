---
title: Identità del servizio e autenticazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [WCF], specifying the identity of a service
ms.assetid: a4c8f52c-5b30-45c4-a545-63244aba82be
ms.openlocfilehash: 6c12c3aadf53f9fddef2f0b0124994db15565cb5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600374"
---
# <a name="service-identity-and-authentication"></a>Identità del servizio e autenticazione
L'identità dell' *endpoint* di un servizio è un valore generato dal Web Services Description Language di servizio (WSDL). Questo valore, propagato a tutti i client, viene utilizzato per autenticare il servizio. Dopo che il client ha avviato una comunicazione con un endpoint e il servizio è stato autenticato nel client, quest'ultimo confronta il valore dell'identità endpoint con il valore effettivo restituito dal processo di autenticazione dell'endpoint. La corrispondenza di questi due valori costituisce garanzia per il client di aver contattato l'endpoint del servizio previsto. Questa funzione funge da protezione contro il *phishing* evitando che un client venga reindirizzato a un endpoint ospitato da un servizio dannoso.  
  
 Per un'applicazione di esempio che illustra l'impostazione Identity, vedere [esempio di identità del servizio](../samples/service-identity-sample.md). Per ulteriori informazioni sugli endpoint e sugli indirizzi endpoint, vedere [indirizzi](endpoint-addresses.md).  
  
> [!NOTE]
> Quando si utilizza NTLM (NT LanMan) per l'autenticazione, l'identità del servizio non viene controllata, poiché, con NTLM, il client non è in grado di autenticare il server. L'autenticazione NTLM viene utilizzata quando i computer fanno parte di un gruppo di lavoro di Windows o quando eseguono una versione precedente di Windows che non supporta l'autenticazione Kerberos.  
  
 Quando il client avvia un canale sicuro per l'invio di un messaggio a un servizio, l'infrastruttura di Windows Communication Foundation (WCF) autentica il servizio e invia il messaggio solo se l'identità del servizio corrisponde all'identità specificata nell'indirizzo dell'endpoint utilizzato dal client.  
  
 L'elaborazione dell'identità si articola nelle fasi seguenti:  
  
- In fase di progettazione, lo sviluppatore del client determina l'identità del servizio dai metadati dell'endpoint (esposti tramite WSDL).  
  
- In fase di esecuzione, l'applicazione client controlla le attestazioni delle credenziali di sicurezza del servizio, prima di inviare messaggi al servizio.  
  
 L'elaborazione dell'identità nel client è analoga all'autenticazione del client nel servizio. Un servizio protetto non esegue codice fino a quando non vengono autenticate le credenziali del client. Allo stesso modo, il client non invia messaggi al servizio fino a quando le credenziali del servizio non sono state autenticate in base a ciò che è noto in anticipo dai metadati del servizio.  
  
 La proprietà <xref:System.ServiceModel.EndpointAddress.Identity%2A> della classe <xref:System.ServiceModel.EndpointAddress> rappresenta l'identità del servizio chiamato dal client. Il servizio pubblica <xref:System.ServiceModel.EndpointAddress.Identity%2A> nei propri metadati. Quando lo sviluppatore client esegue lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per l'endpoint del servizio, la configurazione generata contiene il valore della proprietà del servizio <xref:System.ServiceModel.EndpointAddress.Identity%2A> . L'infrastruttura WCF (se configurata con sicurezza) verifica che il servizio disponga dell'identità specificata.  
  
> [!IMPORTANT]
> I metadati contengono l'identità prevista del servizio, pertanto è consigliabile esporre i metadati del servizio tramite mezzi di comunicazione protetti, ad esempio creando un endpoint HTTPS per il servizio. Per altre informazioni, vedere [procedura: proteggere gli endpoint dei metadati](how-to-secure-metadata-endpoints.md).  
  
## <a name="identity-types"></a>Tipi di identità  
 Un servizio può fornire sei tipi di identità. Ogni tipo di identità corrisponde a un elemento che può essere contenuto nell'elemento `<identity>` della configurazione. Il tipo utilizzato dipende dallo scenario e dai requisiti di sicurezza del servizio. Nella tabella seguente vengono descritti tutti i singoli tipi di identità.  
  
|Tipo di identità|Descrizione|Scenario tipico|  
|-------------------|-----------------|----------------------|  
|Domain Name System (DNS)|Utilizzare questo elemento con certificati X.509 o account di Windows. Confronta il nome DNS specificato nella credenziale con il valore specificato in questo elemento.|Un controllo DNS consente di utilizzare certificati con nomi di soggetto o DNS. Se un certificato viene riemesso con lo stesso nome di soggetto o DNS, il controllo di identità resta valido. Quando un certificato viene riemesso, ottiene una nuova chiave RSA ma mantiene lo stesso nome di soggetto o DNS. Questo significa che i client non devono aggiornare le proprie informazioni di identità sul servizio.|  
|Certificato. Impostazione predefinita quando `ClientCredentialType` è impostato su Certificato.|Questo elemento specifica un certificato X.509 con codifica Base64 da confrontare con il client.<br /><br /> Usare inoltre questo elemento quando si usa CardSpace come credenziale per autenticare il servizio.|Questo elemento restringe l'autenticazione a un solo certificato in base al valore dell'identificazione personale. Ciò rende possibile un'autenticazione più restrittiva, poiché i valori dell'identificazione personale sono univoci. Occorre tuttavia notare che il certificato, se viene riemesso con lo stesso nome di soggetto, avrà anche una nuova identificazione personale. I client non saranno pertanto in grado di convalidare il servizio, a meno che non sia nota la nuova identificazione digitale. Per altre informazioni su come trovare l'identificazione personale di un certificato, vedere [procedura: recuperare l'identificazione personale di un certificato](how-to-retrieve-the-thumbprint-of-a-certificate.md).|  
|Riferimento del certificato|Identico all'opzione Certificato prima descritta. Tuttavia, questo elemento consente di specificare un nome di certificato e il percorso dell'archivio da cui recuperare il certificato.|Uguale allo scenario Certificato prima descritto.<br /><br /> Il vantaggio è che il percorso dell'archivio certificati può essere modificato.|  
|RSA|Questo elemento specifica un valore della chiave RSA da confrontare con il client. È simile all'opzione certificato, ma invece dell'identificazione personale del certificato viene utilizzata la chiave RSA del certificato.|Un controllo RSA consente di restringere specificamente l'autenticazione a un solo certificato in base alla relativa chiave RSA. Ciò rende possibile l'autenticazione più restrittiva di una chiave RSA specifica a spese del servizio, che non funziona più con i client esistenti, se il valore della chiave RSA viene modificato.|  
|Nome dell'entità utente. Impostazione predefinita quando `ClientCredentialType` è impostato su Windows e il processo del servizio non è in esecuzione con uno degli account di sistema.|Questo elemento specifica l'UPN con cui è in esecuzione il servizio. Vedere la sezione relativa a protocollo e identità Kerberos di [override dell'identità di un servizio per l'autenticazione](../extending/overriding-the-identity-of-a-service-for-authentication.md).|Questo assicura che il servizio sia in esecuzione con un account utente di Windows specifico. L'account utente può essere l'utente attualmente connesso o il servizio in esecuzione con un particolare account utente.<br /><br /> Questa impostazione sfrutta la protezione Kerberos di Windows, se il servizio è in esecuzione con un account di dominio all'interno di un ambiente Active Directory.|  
|Nome dell'entità servizio (SPN). Impostazione predefinita quando `ClientCredentialType` è impostato su Windows e il processo del servizio è in esecuzione con uno degli account di sistema: LocalService, LocalSystem o NetworkService.|Questo elemento specifica il nome SPN associato all'account del servizio. Vedere la sezione relativa a protocollo e identità Kerberos di [override dell'identità di un servizio per l'autenticazione](../extending/overriding-the-identity-of-a-service-for-authentication.md).|Questo assicura che il nome SPN e l'account specifico di Windows a esso associato identifichino il servizio.<br /><br /> È possibile utilizzare lo strumento Setspn.exe per associare un account computer per l'account utente del servizio.<br /><br /> Questa impostazione sfrutta la protezione Kerberos di Windows, se il servizio è in esecuzione con uno degli account di sistema o con un account di dominio associato a un nome SPN e il computer è un membro di un dominio interno a un ambiente Active Directory.|  
  
## <a name="specifying-identity-at-the-service"></a>Impostazione dell'identità nel servizio  
 In genere non è necessario impostare l'identità in un servizio, perché la selezione del tipo di credenziale di un client impone il tipo di identità esposto nei metadati del servizio. Per ulteriori informazioni su come eseguire l'override o specificare l'identità del servizio, vedere override [dell'identità di un servizio per l'autenticazione](../extending/overriding-the-identity-of-a-service-for-authentication.md).  
  
## <a name="using-the-identity-element-in-configuration"></a>Utilizzo dell' \<identity> elemento nella configurazione  
 Se si imposta su `Certificate,` il tipo di credenziale client nell'associazione prima descritta, il codice WSDL generato conterrà un certificato X.509 con serializzazione Base64 per il valore dell'identità, come illustrato nel codice seguente. Si tratta dell'impostazione predefinita per tutti i tipi di credenziale client diversi da Windows.  

 È possibile modificare il valore dell'identità del servizio predefinita o modificare il tipo dell'identità usando l' `<identity>` elemento nella configurazione o impostando l'identità nel codice. Nel codice di configurazione seguente viene impostata un'identità DNS (Domain Name System) con il valore `contoso.com`.  

## <a name="setting-identity-programmatically"></a>Impostazione dell'identità a livello di programmazione  
 Il servizio non deve specificare in modo esplicito un'identità, perché WCF la determina automaticamente. Tuttavia, WCF consente di specificare un'identità in un endpoint, se necessario. Nel codice seguente viene aggiunto un nuovo endpoint di servizio con un'identità DNS specifica.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="specifying-identity-at-the-client"></a>Impostazione dell'identità nel client  
 In fase di progettazione uno sviluppatore client utilizza in genere lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per generare la configurazione client. Il file di configurazione generato (destinato a essere utilizzato dal client) contiene l'identità del server. Ad esempio, il codice seguente viene generato da un servizio che specifica un'identità DNS, come illustrato nell'esempio precedente. Si noti che il valore dell'identità endpoint del client corrisponde a quello del servizio. In questo caso, quando il client riceve le credenziali Windows (Kerberos) per il servizio, si aspetta che il valore sia `contoso.com`.  

 Se, invece di Windows, il servizio specifica un certificato come tipo di credenziale client, si prevede che la proprietà DNS del certificato corrisponda al valore `contoso.com` (oppure, se la proprietà DNS è `null`, il nome di soggetto del certificato deve essere `contoso.com`).  
  
#### <a name="using-a-specific-value-for-identity"></a>Utilizzo di un valore specifico per l'identità  
 Nel file di configurazione client seguente viene illustrato come si prevede che l'identità del servizio sia un valore specifico. Nell'esempio seguente, il client può comunicare con due endpoint. Il primo viene identificato con un'identificazione personale del certificato e il secondo con una chiave RSA del certificato, ovvero un certificato che contiene solo una coppia chiave pubblica/chiave privata ma non viene emesso da un'autorità attendibile.  

## <a name="identity-checking-at-run-time"></a>Controllo dell'identità in fase di esecuzione  
 In fase di progettazione, un sviluppatore di client determina l'identità del server tramite i relativi metadati. In fase di esecuzione, il controllo dell'identità viene eseguito prima di chiamare qualsiasi endpoint nel servizio.  
  
 Il valore dell'identità è associato al tipo di autenticazione specificato dai metadati; in altre parole, al tipo di credenziali utilizzato per il servizio.  
  
 Se il canale è configurato per l'autenticazione tramite SSL (Secure Sockets Layer) a livello di messaggio o di trasporto con certificati X.509, sono validi i valori di identità seguenti:  
  
- DNS. WCF garantisce che il certificato fornito durante l'handshake SSL contenga un attributo DNS o `CommonName` (CN) uguale al valore specificato nell'identità DNS sul client. Si noti che questi controlli vengono eseguiti in aggiunta alla determinazione della validità del certificato server. Per impostazione predefinita, WCF convalida che il certificato del server viene emesso da un'autorità radice attendibile.  
  
- Certificato. Durante l'handshake SSL, WCF garantisce che l'endpoint remoto fornisca il valore del certificato esatto specificato nell'identità.  
  
- Riferimento del certificato. Uguale a Certificato.  
  
- RSA. Durante l'handshake SSL, WCF garantisce che l'endpoint remoto fornisca la chiave RSA esatta specificata nell'identità.  
  
 Se il servizio esegue l'autenticazione utilizzando SSL a livello di messaggio o di trasporto con una credenziale Windows e negozia la credenziale, sono validi i valori di identità seguenti:  
  
- DNS. La negoziazione passa il nome SPN del servizio, in modo che il nome DNS possa essere controllato. Il nome SPN presenta il formato `host/<dns name>`.  
  
- SPN. Viene restituito un SPN del servizio esplicito, ad esempio, `host/myservice`.  
  
- UPN. UPN dell'account di servizio. Il formato dell'UPN è `username` @ `domain` . Ad esempio, quando il servizio è in esecuzione con un account utente, l'UPN può essere `username@contoso.com`.  
  
 L'impostazione dell'identità a livello di programmazione (utilizzando la proprietà <xref:System.ServiceModel.EndpointAddress.Identity%2A>) è facoltativa. Se non viene specificata alcuna identità, e il tipo di credenziale client è Windows, l'impostazione predefinita è SPN con il valore impostato sulla parte del nome host dell'indirizzo dell'endpoint del servizio preceduta dal valore letterale "host/". Se non viene specificata alcuna identità, e il tipo di credenziale client è un certificato, l'impostazione predefinita è `Certificate`. Questo vale per la protezione a livello di messaggio e di trasporto.  
  
## <a name="identity-and-custom-bindings"></a>Identità e associazioni personalizzate  
 Poiché l'identità di un servizio dipende dal tipo di associazione utilizzato, assicurarsi che sia esposta un'identità appropriata quando si crea un'associazione personalizzata. Ad esempio, nell'esempio di codice seguente, l'identità esposta non è compatibile con il tipo di sicurezza, poiché l'identità per l'associazione bootstrap di conversazione protetta non corrisponde all'identità per l'associazione sull'endpoint. L'associazione di conversazione protetta imposta l'identità DNS, mentre <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> imposta l'identità UPN o SPN.  
  
 [!code-csharp[C_Identity#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#8)]
 [!code-vb[C_Identity#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#8)]  
  
 Per ulteriori informazioni su come impilare correttamente gli elementi di associazione per un'associazione personalizzata, vedere [creazione di associazioni definite dall'utente](../extending/creating-user-defined-bindings.md). Per ulteriori informazioni sulla creazione di un'associazione personalizzata con <xref:System.ServiceModel.Channels.SecurityBindingElement> , vedere [procedura: creare un oggetto SecurityBindingElement per una modalità di autenticazione specificata](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: creare un'associazione personalizzata usando SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Procedura: creare un elemento SecurityBindingElement per una modalità di autenticazione specificata](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
- [Procedura: creare un verificatore di identità client personalizzato](../extending/how-to-create-a-custom-client-identity-verifier.md)
- [Selezione di un tipo di credenziale](selecting-a-credential-type.md)
- [Working with Certificates](working-with-certificates.md)
- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Creazione di associazioni definite dall'utente](../extending/creating-user-defined-bindings.md)
- [Procedura: recuperare l'identificazione personale di un certificato](how-to-retrieve-the-thumbprint-of-a-certificate.md)
