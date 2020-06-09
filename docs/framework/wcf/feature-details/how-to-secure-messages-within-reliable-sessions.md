---
title: 'Procedura: proteggere i messaggi in sessioni affidabili'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: 306d0f96b5163fe5c24d270b4b9a7c1d3f499e7e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596955"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Procedura: proteggere i messaggi in sessioni affidabili

In questo argomento vengono delineati i passaggi necessari per attivare la protezione a livello di messaggio per i messaggi scambiati all'interno di una sessione affidabile utilizzando una delle associazioni fornite dal sistema che supportano tale sessione, ma non per impostazione predefinita. Abilitare una sessione sicura e affidabile in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione. In questa procedura vengono utilizzati i file di configurazione del client e del servizio per attivare la sessione affidabile protetta.

Questa procedura è costituita dalle tre attività chiave seguenti:

1. Specificare che il client e il servizio si scambiano messaggi in una sessione affidabile.

1. Richiedere la protezione a livello di messaggio all'interno della sessione affidabile.

1. Specificare il tipo di credenziale client che il client deve utilizzare per essere autenticato con il servizio.

È importante nella prima attività che l'elemento di configurazione dell'endpoint contenga un `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione denominata (in questo esempio) `MessageSecurity` . L' [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) elemento di configurazione fa quindi riferimento a questo nome per abilitare le sessioni affidabili impostando l' `enabled` attributo dell' [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) elemento su `true` . È possibile richiedere che le garanzie di recapito ordinato siano disponibili all'interno di una sessione affidabile impostando l'attributo `ordered` su `true`.

Per la copia di origine dell'esempio su cui si basa questa procedura di configurazione, vedere la [sessione WS Reliable](../samples/ws-reliable-session.md).

Gli elementi essenziali della seconda attività vengono eseguiti impostando l' `mode` attributo dell' **\<security>** elemento contenuto nell' **\<binding>** elemento del client e del servizio su `Message` .

Gli elementi essenziali della terza attività vengono eseguiti impostando l' `clientCredentialType` attributo dell' **\<message>** elemento contenuto nell' **\<security>** elemento del client e del servizio su `Certificate` .

> [!NOTE]
> Quando si utilizza la sicurezza dei messaggi con sessioni affidabili, la messaggistica affidabile tenta di autenticare un client non autenticato fino a quando non si verifica un timeout anziché generare un'eccezione al primo errore.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il servizio con WSHttpBinding per l'utilizzo di una sessione affidabile

Questa procedura è descritta in [procedura: scambiare messaggi in una sessione affidabile](how-to-exchange-messages-within-a-reliable-session.md).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il client con WSHttpBinding per l'utilizzo di una sessione affidabile

Questa procedura è descritta in [procedura: scambiare messaggi in una sessione affidabile](how-to-exchange-messages-within-a-reliable-session.md).

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Impostare la modalità e ClientCredentialType nella configurazione

1. Aggiungere un elemento di associazione appropriato all' [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) elemento del file di configurazione. Nell'esempio seguente viene aggiunto un [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.

1. Aggiungere un **\<binding>** elemento e impostare il relativo `name` attributo su un valore appropriato. Nell'esempio viene usato il nome `MessageSecurity` .

1. Aggiungere un **\<security>** elemento e impostare l' `mode` attributo su `Message` .

1. All'interno dell' **\<security>** elemento aggiungere un **\<message>** elemento e impostare l' `clientCredentialType` attributo su `Certificate` .

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
