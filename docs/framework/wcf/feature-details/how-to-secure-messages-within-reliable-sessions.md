---
title: 'Procedura: proteggere i messaggi in sessioni affidabili'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: edff27fe9649387c1922c34e72ef59d615e52b90
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141672"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Procedura: proteggere i messaggi in sessioni affidabili

In questo argomento vengono delineati i passaggi necessari per attivare la protezione a livello di messaggio per i messaggi scambiati all'interno di una sessione affidabile utilizzando una delle associazioni fornite dal sistema che supportano tale sessione, ma non per impostazione predefinita. Abilitare una sessione sicura e affidabile in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione. In questa procedura vengono utilizzati i file di configurazione del client e del servizio per attivare la sessione affidabile protetta.

Questa procedura è costituita dalle tre attività chiave seguenti:

1. Specificare che il client e il servizio si scambiano messaggi in una sessione affidabile.

1. Richiedere la protezione a livello di messaggio all'interno della sessione affidabile.

1. Specificare il tipo di credenziale client che il client deve utilizzare per essere autenticato con il servizio.

È importante nella prima attività che l'elemento di configurazione dell'endpoint contenga un `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione denominata (in questo esempio) `MessageSecurity`. L'elemento di configurazione [ **\<binding >** ](../../configure-apps/file-schema/wcf/bindings.md) quindi fa riferimento a questo nome per abilitare sessioni affidabili impostando l'attributo `enabled` dell'elemento [ **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) su `true`. È possibile richiedere che le garanzie di recapito ordinato siano disponibili all'interno di una sessione affidabile impostando l'attributo `ordered` su `true`.

Per la copia di origine dell'esempio su cui si basa questa procedura di configurazione, vedere la [sessione WS Reliable](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

Gli elementi essenziali della seconda attività vengono eseguiti impostando l'attributo `mode` dell'elemento del **> di sicurezza\<** contenuto nell'elemento **\<binding** del client e del servizio su `Message`.

Gli elementi essenziali della terza attività vengono eseguiti impostando l'attributo `clientCredentialType` dell'elemento **\<messaggio** contenuto nell'elemento > di **sicurezza\<** del client e del servizio su `Certificate`.

> [!NOTE]
> Quando si utilizza la sicurezza dei messaggi con sessioni affidabili, la messaggistica affidabile tenta di autenticare un client non autenticato fino a quando non si verifica un timeout anziché generare un'eccezione al primo errore.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il servizio con WSHttpBinding per l'utilizzo di una sessione affidabile

Questa procedura è descritta in [procedura: scambiare messaggi in una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il client con WSHttpBinding per l'utilizzo di una sessione affidabile

Questa procedura è descritta in [procedura: scambiare messaggi in una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Impostare la modalità e ClientCredentialType nella configurazione

1. Aggiungere un elemento di associazione appropriato al [ **\<associazioni >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento del file di configurazione. Nell'esempio seguente viene aggiunto un [ **\<elemento wshttpbinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) .

1. Aggiungere un elemento **\<binding >** e impostare il relativo attributo `name` su un valore appropriato. Nell'esempio viene usato il nome `MessageSecurity`.

1. Aggiungere un elemento **\<security >** e impostare l'attributo `mode` su `Message`.

1. All'interno dell'elemento **\<security >** aggiungere un elemento **\<message >** e impostare l'attributo `clientCredentialType` su `Certificate`.

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
