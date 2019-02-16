---
title: 'Procedura: Proteggere i messaggi in sessioni affidabili'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: ee35f2a36ca08814423b5a3d0b1432bacd28c2e5
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "56333053"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Procedura: Proteggere i messaggi in sessioni affidabili

In questo argomento vengono delineati i passaggi necessari per attivare la protezione a livello di messaggio per i messaggi scambiati all'interno di una sessione affidabile utilizzando una delle associazioni fornite dal sistema che supportano tale sessione, ma non per impostazione predefinita. Abilitare una sessione affidabile protetta in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione. In questa procedura vengono utilizzati i file di configurazione del client e del servizio per attivare la sessione affidabile protetta.

Questa procedura è costituita dalle tre attività chiave seguenti:

1. Specificare che il client e il servizio si scambiano messaggi in una sessione affidabile.

1. Richiedere la protezione a livello di messaggio all'interno della sessione affidabile.

1. Specificare il tipo di credenziale client che il client deve utilizzare per essere autenticato con il servizio.

È importante per la prima attività contenenti l'elemento di configurazione di endpoint un `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione denominata (in questo esempio) `MessageSecurity`. Il [  **\<associazione >** ](../../../../docs/framework/misc/binding.md) elemento di configurazione fa quindi riferimento a questo nome per attivare sessioni affidabili impostando il `enabled` attributo del [  **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) elemento `true`. È possibile richiedere che le garanzie di recapito ordinato siano disponibili all'interno di una sessione affidabile impostando l'attributo `ordered` su `true`.

Per la copia origine dell'esempio in cui si basa questa procedura di configurazione, vedere la [sessioni affidabili WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

Gli elementi essenziali della seconda attività vengono eseguiti impostando il `mode` attributo del  **\<sicurezza >** elemento contenuto nel  **\<associazione >** elemento del client e del servizio per `Message`.

Gli elementi essenziali della terza attività vengono eseguiti impostando il `clientCredentialType` attributo del  **\<messaggio >** elemento contenuto nel  **\<sicurezza >** elemento del client e del servizio per `Certificate`.

> [!NOTE]
> Quando si usa la sicurezza dei messaggi con sessioni affidabili, messaggistica affidabile tenta di autenticare un client non autenticato, fino a quando non si verifica un timeout anziché generare un'eccezione al primo errore.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il servizio con una classe WSHttpBinding per utilizzare una sessione affidabile

Questa procedura è descritta nella [come: Lo scambio di messaggi in una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il client con una classe WSHttpBinding per utilizzare una sessione affidabile

Questa procedura è descritta nella [come: Lo scambio di messaggi in una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Impostare la modalità e la proprietà ClientCredentialType nella configurazione

1. Aggiungere un elemento di binding appropriato per il [  **\<associazioni >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento del file di configurazione. L'esempio seguente aggiunge un [  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.

1. Aggiungere un  **\<associazione >** e impostare il `name` attributo su un valore appropriato. L'esempio Usa il nome `MessageSecurity`.

1. Aggiungere un  **\<sicurezza >** e impostare il `mode` attributo `Message`.

1. All'interno di  **\<sicurezza >** elemento, aggiungere un  **\<messaggio >** e impostare il `clientCredentialType` attributo `Certificate`.

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
