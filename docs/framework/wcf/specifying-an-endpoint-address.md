---
title: Specifica di un indirizzo endpoint
description: Informazioni su un indirizzo endpoint, una parte di un ServiceEndpoint in WCF. Tutte le comunicazioni con un servizio WCF avvengono tramite gli endpoint.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], addressing
ms.assetid: ac24f5ad-9558-4298-b168-c473c68e819b
ms.openlocfilehash: e1bd9e5a27d1bc86d2d3e04ee82221a27a4e1fa8
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245985"
---
# <a name="specifying-an-endpoint-address"></a>Specifica di un indirizzo endpoint

Tutte le comunicazioni con un servizio Windows Communication Foundation (WCF) si verificano attraverso gli endpoint. Ogni <xref:System.ServiceModel.Description.ServiceEndpoint> contiene una proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.Address%2A>, una proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A> e una proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A>. Il contratto specifica quali operazioni sono disponibili. L'associazione specifica come comunicare con il servizio e l'indirizzo specifica dove trovare il servizio. Ogni endpoint deve avere un indirizzo univoco. L'indirizzo dell'endpoint è rappresentato dalla classe <xref:System.ServiceModel.EndpointAddress>, che contiene un URI (Uniform Resource Identifier), che rappresenta l'indirizzo del servizio, una proprietà <xref:System.ServiceModel.EndpointAddress.Identity%2A>, che rappresenta l'identità di sicurezza del servizio, e una raccolta di proprietà <xref:System.ServiceModel.EndpointAddress.Headers%2A> facoltative. Le intestazioni facoltative forniscono informazioni di indirizzamento più dettagliate che consentono di identificare o interagire con l'endpoint. Ad esempio, le intestazioni possono indicare come elaborare un messaggio in ingresso, dove l'endpoint deve inviare un messaggio di risposta o quale istanza di un servizio usare per elaborare un messaggio in ingresso di un particolare utente, quando sono disponibili più istanze.

## <a name="definition-of-an-endpoint-address"></a>Definizione di un indirizzo endpoint

In WCF un <xref:System.ServiceModel.EndpointAddress> modello è un riferimento a un endpoint (EPR) come definito nello standard WS-Addressing.

L'indirizzo URI per la maggior parte dei trasporti è costituito da quattro parti. Questo URI, ad esempio, `http://www.fabrikam.com:322/mathservice.svc/secureEndpoint` include le quattro parti seguenti:

- Schema: http:

- Macchina`www.fabrikam.com`

- (Facoltativo) Porta: 322

- Percorso: /mathservice.svc/secureEndpoint

Il modello di riferimento endpoint prevede che ogni riferimento possa includere alcuni parametri di riferimento che aggiungono ulteriori informazioni di identificazione. In WCF questi parametri di riferimento vengono modellati come istanze della <xref:System.ServiceModel.Channels.AddressHeader> classe.

L'indirizzo endpoint per un servizio può essere specificato in modo imperativo mediante l'utilizzo di codice oppure in modo dichiarativo mediante la configurazione. In genere definire endpoint nel codice non è pratico in quanto le associazioni e gli indirizzi di un servizio distribuito sono solitamente diversi da quelli usati durante lo sviluppo del servizio. In genere è più pratico definire endpoint di servizio mediante la configurazione piuttosto che mediante codice. Se le informazioni sull'associazione e sull'indirizzo non vengono incluse nel codice, tali dati possono essere modificati senza dover compilare e distribuire nuovamente l'applicazione. Se non è specificato alcun endpoint nel codice o nella configurazione, il runtime ne aggiunge uno predefinito ad ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio.

Esistono due modi per specificare gli indirizzi degli endpoint per un servizio in WCF. È possibile specificare un indirizzo assoluto per ogni endpoint associato al servizio o fornire un indirizzo di base per la classe <xref:System.ServiceModel.ServiceHost> di un servizio e quindi specificare un indirizzo per ogni endpoint associato a questo servizio, che viene definito come relativo all'indirizzo di base. È possibile utilizzare entrambe le procedure per specificare gli indirizzi degli endpoint per un servizio nella configurazione o nel codice. Se non si specifica un indirizzo relativo, il servizio utilizza l'indirizzo di base. È inoltre possibile avere più indirizzi di base per un servizio, ma per ogni servizio è consentito un solo indirizzo di base per ogni trasporto. Se sono presenti più endpoint, ognuno dei quali è configurato con un'associazione diversa, i relativi indirizzi devono essere univoci. Gli endpoint che utilizzano la stessa associazione ma contratti diversi possono utilizzare lo stesso indirizzo.

Quando si ospita il servizio in IIS, non si gestisce l'istanza di <xref:System.ServiceModel.ServiceHost>. Nel caso di un servizio ospitato in IIS, l'indirizzo di base è sempre l'indirizzo specificato nel file con estensione svc. Per gli endpoint del servizio ospitato in IIS è quindi necessario utilizzare sempre indirizzi relativi. Fornire un indirizzo endpoint completo può provocare errori nella fase di distribuzione del servizio. Per ulteriori informazioni, vedere [distribuzione di un servizio WCF ospitato in Internet Information Services](./feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).

## <a name="defining-endpoint-addresses-in-configuration"></a>Definizione degli indirizzi endpoint nella configurazione

Per definire un endpoint in un file di configurazione, usare l' [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) elemento.

[!code-xml[S_UEHelloWorld#5](./snippets/specifying-an-endpoint-address/serviceapp2.config#5)]

Quando <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> viene chiamato il metodo, ovvero quando l'applicazione host tenta di avviare il servizio, il sistema cerca un [\<service>](../configure-apps/file-schema/wcf/service.md) elemento con un attributo Name che specifica "UE". Samples. HelloService ". Se l' [\<service>](../configure-apps/file-schema/wcf/service.md) elemento viene trovato, il sistema carica la classe specificata e crea gli endpoint usando le definizioni di endpoint fornite nel file di configurazione. Questo meccanismo consente di caricare e avviare un servizio con due righe di codice, mentre tiene le informazioni sull'associazione e l'indirizzamento fuori dal codice. Il vantaggio di tale approccio è che queste modifiche possono essere apportate senza dover ricompilare o ridistribuire l'applicazione.

Le intestazioni facoltative vengono dichiarate in un oggetto [\<headers>](../configure-apps/file-schema/wcf/headers-element.md) . Di seguito è riportato un esempio degli elementi utilizzati per specificare gli endpoint per un servizio in un file di configurazione che distingue tra due intestazioni: i client "Gold" `http://tempuri1.org/` e i client "standard" da `http://tempuri2.org/` . Il client che chiama questo servizio deve avere il appropriato [\<headers>](../configure-apps/file-schema/wcf/headers-element.md) nel file di configurazione.

[!code-xml[S_UEHelloWorld#1](./snippets/specifying-an-endpoint-address/serviceapp.config#1)]

Le intestazioni possono essere impostate anche su singoli messaggi anziché su tutti i messaggi su un endpoint (come illustrato in precedenza). A tale scopo, utilizzare <xref:System.ServiceModel.OperationContextScope> per creare un nuovo contesto in un'applicazione client, per aggiungere un'intestazione personalizzata al messaggio in uscita, come illustrato nell'esempio seguente.

[!code-csharp[OperationContextScope#4](../../../samples/snippets/csharp/VS_Snippets_CFX/operationcontextscope/cs/client.cs#4)]
[!code-vb[OperationContextScope#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/operationcontextscope/vb/client.vb#4)]

## <a name="endpoint-address-in-metadata"></a>Indirizzo endpoint nei metadati

Un indirizzo endpoint viene rappresentato in WSDL (Web Services Description Language) come elemento `EndpointReference` (EPR) WS-Addressing all'interno dell'elemento `wsdl:port` dell'endpoint corrispondente. L'EPR contiene l'indirizzo dell'endpoint e qualsiasi proprietà dell'indirizzo. Si noti che l'EPR in `wsdl:port` sostituisce `soap:Address`, come illustrato nell'esempio seguente.

## <a name="defining-endpoint-addresses-in-code"></a>Definizione degli indirizzi endpoint nel codice

È possibile creare un indirizzo endpoint nel codice con la classe <xref:System.ServiceModel.EndpointAddress>. L'URI specificato per l'indirizzo endpoint può essere un percorso completo o un percorso relativo all'indirizzo di base del servizio. Nel codice seguente viene illustrato come creare un'istanza della classe <xref:System.ServiceModel.EndpointAddress> e aggiungerla all'istanza di <xref:System.ServiceModel.ServiceHost> che ospita il servizio.

Nell'esempio seguente viene illustrato come specificare l'indirizzo endpoint completo nel codice.

[!code-csharp[S_UEHelloWorld#2](../../../samples/snippets/csharp/VS_Snippets_CFX/s_uehelloworld/cs/snippet.cs#2)]

Nell'esempio seguente viene illustrato come aggiungere un indirizzo relativo ("MyService") all'indirizzo di base dell'host del servizio.

[!code-csharp[S_UEHelloWorld#3](../../../samples/snippets/csharp/VS_Snippets_CFX/s_uehelloworld/cs/snippet.cs#3)]

> [!NOTE]
> Le proprietà di <xref:System.ServiceModel.Description.ServiceDescription> nell'applicazione del servizio non devono essere modificate successivamente al metodo <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> su <xref:System.ServiceModel.ServiceHostBase>. Se vengono modificati dopo questo punto, alcuni membri, ad esempio la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> e i metodi `AddServiceEndpoint` su <xref:System.ServiceModel.ServiceHostBase> e <xref:System.ServiceModel.ServiceHost>, generano un'eccezione. Altri consentono la modifica, ma il risultato è indefinito.
>
> Analogamente, sul client i valori <xref:System.ServiceModel.Description.ServiceEndpoint> non devono essere modificati dopo la chiamata a <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> su <xref:System.ServiceModel.ChannelFactory>. Se viene modificata dopo questo punto, la proprietà <xref:System.ServiceModel.ChannelFactory.Credentials%2A> genera un'eccezione. Gli altri valori della descrizione client possono essere modificati senza errore, ma il risultato è indefinito.
>
> Per il servizio o per il client, è consigliabile modificare la descrizione prima di chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.

## <a name="using-default-endpoints"></a>Uso di endpoint predefiniti

Se non è specificato alcun endpoint nel codice o nella configurazione, il runtime ne fornisce di predefiniti aggiungendone uno ad ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio. L'indirizzo di base può essere specificato nel codice o nella configurazione e gli endpoint predefiniti vengono aggiunti quando viene chiamato <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> in <xref:System.ServiceModel.ServiceHost>.

Se vengono forniti endpoint in modo esplicito, è comunque possibile aggiungere gli endpoint predefiniti chiamando <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> su <xref:System.ServiceModel.ServiceHost> prima di chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.EndpointAddress>
- [Identità del servizio e autenticazione](./feature-details/service-identity-and-authentication.md)
- [Cenni preliminari sulla creazione di endpoint](endpoint-creation-overview.md)
- [Hosting](./feature-details/hosting.md)
