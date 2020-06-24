---
title: 'Endpoint: indirizzi, associazioni e contratti'
description: Informazioni sull'utilizzo di tutte le comunicazioni con un servizio WCF tramite gli endpoint del servizio, che forniscono ai client l'accesso alla funzionalità offerta dal servizio.
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: ce0874bfed716716b6fd1801b35a4266095cd752
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247312"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a>Endpoint: indirizzi, associazioni e contratti

Tutte le comunicazioni con un servizio Windows Communication Foundation (WCF) avvengono tramite gli *endpoint* del servizio. Gli endpoint forniscono ai client l'accesso alla funzionalità offerta da un servizio WCF.

Ogni endpoint è costituito da quattro proprietà:

- Un indirizzo che indica dove si trova l'endpoint.

- Un'associazione che specifica in che modo un client può comunicare con l'endpoint.

- Un contratto che identifica le operazioni disponibili.

- Un set di comportamenti che specificano dettagli di implementazione locali dell'endpoint.

In questo argomento viene illustrata la struttura dell'endpoint e viene illustrato come viene rappresentata nel modello a oggetti WCF.

## <a name="the-structure-of-an-endpoint"></a>Struttura di un endpoint

Ogni endpoint è costituito dagli elementi seguenti:

- Indirizzo: l'indirizzo identifica in modo univoco l'endpoint e comunica ai potenziali utenti l'ubicazione del servizio. Viene rappresentata nel modello a oggetti WCF dalla <xref:System.ServiceModel.EndpointAddress> classe. Una classe <xref:System.ServiceModel.EndpointAddress> contiene:

  - Una proprietà <xref:System.ServiceModel.EndpointAddress.Uri%2A>, che rappresenta l'indirizzo del servizio.

  - Una proprietà <xref:System.ServiceModel.EndpointAddress.Identity%2A>, che rappresenta l'identità di sicurezza del servizio e una raccolta di intestazioni di messaggio facoltative. Le intestazioni di messaggio facoltative vengono utilizzate per fornire ulteriori informazioni di indirizzamento più dettagliate, per identificare o interagire con l'endpoint.

  Per ulteriori informazioni, vedere [specifica di un indirizzo endpoint](../specifying-an-endpoint-address.md).

- Associazione: l'associazione specifica la modalità di comunicazione con l'endpoint, Ad esempio:

  - Il protocollo di trasporto da utilizzare (ad esempio, TCP o HTTP).

  - La codifica da utilizzare per i messaggi (ad esempio, testo o binaria).

  - I necessari requisiti di sicurezza (ad esempio, la protezione dei messaggi SSL o SOAP).

  Per ulteriori informazioni, vedere [Cenni preliminari sulle associazioni WCF](../bindings-overview.md). Un'associazione viene rappresentata nel modello a oggetti WCF dalla classe di base astratta <xref:System.ServiceModel.Channels.Binding> . Per la maggior parte degli scenari, gli utenti possono utilizzare una delle associazioni fornite dal sistema. Per ulteriori informazioni, vedere [binding forniti dal sistema](../system-provided-bindings.md).

- Contratti: il contratto delinea la funzionalità che l'endpoint espone al client. Un contratto specifica:

  - Quali operazioni possono essere chiamate da un client.

  - La forma del messaggio.

  - Il tipo di parametri di input o di dati necessario per chiamare l'operazione.

  - Il tipo di elaborazione o di messaggio di risposta che il client può aspettarsi.

  Per ulteriori informazioni sulla definizione di un contratto, vedere [progettazione di contratti di servizio](../designing-service-contracts.md).

- Comportamenti: è possibile utilizzare i comportamenti dell'endpoint per personalizzare il comportamento locale dell'endpoint del servizio. A questo scopo, i comportamenti degli endpoint partecipano al processo di compilazione di un runtime WCF. Un esempio di comportamento dell'endpoint è rappresentato dalla proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, che consente di specificare un indirizzo di ascolto diverso dall'indirizzo SOAP o WSDL (Web Services Description Language). Per ulteriori informazioni, vedere [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).

## <a name="defining-endpoints"></a>Definizione di endpoint

È possibile specificare l'endpoint di un servizio in modo imperativo, tramite codice, o in modo dichiarativo, tramite la configurazione. Per altre informazioni, vedere [procedura: creare un endpoint del servizio nella configurazione](how-to-create-a-service-endpoint-in-configuration.md) e [procedura: creare un endpoint di servizio nel codice](how-to-create-a-service-endpoint-in-code.md).

## <a name="in-this-section"></a>Contenuto della sezione

Contenuto della sezione viene illustrato lo scopo di associazioni, endpoint e indirizzi; viene descritto come configurare un'associazione e un endpoint e viene dimostrato come utilizzare il comportamento `ClientVia` e la proprietà `ListenUri`.

[Indirizzi](endpoint-addresses.md)\
Viene descritto come vengono risolti gli endpoint in WCF.

[Associazioni](bindings.md)\
Viene descritto come vengono utilizzate le associazioni per specificare i dettagli sul trasporto, la codifica e il protocollo necessari per consentire la comunicazione tra client e servizi.

[Contratti](contracts.md)\
Viene descritto in che modo i contratti definiscono i metodi di un servizio.

[Procedura: creare un endpoint del servizio nella configurazione](how-to-create-a-service-endpoint-in-configuration.md)\
Viene descritto come creare un endpoint del servizio nella configurazione.

[Procedura: creare un endpoint di servizio nel codice](how-to-create-a-service-endpoint-in-code.md)\
Viene descritto come creare un endpoint del servizio nel codice.

[Procedura: usare Svcutil.exe per convalidare il codice del servizio compilato](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)\
Viene descritto come rilevare errori in implementazioni e configurazioni del servizio senza ospitare il servizio utilizzando lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).

## <a name="see-also"></a>Vedere anche

- [Configurazione dei servizi](../configuring-services.md)
- [Estensione delle associazioni](../extending/extending-bindings.md)
