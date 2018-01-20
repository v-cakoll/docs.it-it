---
title: 'Procedura: proteggere i messaggi in sessioni affidabili'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 2604b9dacf11b9971b10d23d9a807092ddf07830
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Procedura: proteggere i messaggi in sessioni affidabili

In questo argomento vengono delineati i passaggi necessari per attivare la protezione a livello di messaggio per i messaggi scambiati all'interno di una sessione affidabile utilizzando una delle associazioni fornite dal sistema che supportano tale sessione, ma non per impostazione predefinita. Abilitare una sessione protetta e affidabile in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione. In questa procedura vengono utilizzati i file di configurazione del client e del servizio per attivare la sessione affidabile protetta.

Questa procedura è costituita dalle tre attività chiave seguenti:

1. Specificare che il client e il servizio si scambiano messaggi in una sessione affidabile.

1. Richiedere la protezione a livello di messaggio all'interno della sessione affidabile.

1. Specificare il tipo di credenziale client che il client deve utilizzare per essere autenticato con il servizio.

È importante nell'attività prima che l'elemento di configurazione endpoint contenga un `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione denominata (in questo esempio) `MessageSecurity`. Il [  **\<associazione >** ](../../../../docs/framework/misc/binding.md) elemento di configurazione fa quindi riferimento a questo nome per abilitare sessioni affidabili impostando il `enabled` attributo del [  **\<reliableSession >** ](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) elemento `true`. È possibile richiedere che le garanzie di recapito ordinato siano disponibili all'interno di una sessione affidabile impostando l'attributo `ordered` su `true`.

Per la copia origine dell'esempio in cui è basato su questa procedura di configurazione, vedere il [sessione affidabile WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

Gli elementi essenziali della seconda attività vengono eseguiti tramite l'impostazione di `mode` attributo del  **\<sicurezza >** elemento contenuto nel  **\<associazione >** elemento del client e servizio `Message`.

Gli elementi essenziali della terza attività vengono eseguiti tramite l'impostazione di `clientCredentialType` attributo del  **\<messaggio >** elemento contenuto nel  **\<sicurezza >** elemento del client e servizio `Certificate`.

> [!NOTE]
> Quando si utilizza la sicurezza dei messaggi con sessioni affidabili, messaggistica affidabile tenta di autenticare un client non autenticato fino a quando non si verifica un timeout anziché generare un'eccezione al primo errore.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il servizio con una classe WSHttpBinding per utilizzare una sessione affidabile

Questa procedura è descritta [come: Exchange messaggi all'interno di una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il client con una classe WSHttpBinding per utilizzare una sessione affidabile

Questa procedura è descritta [come: Exchange messaggi all'interno di una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Impostare la modalità e la proprietà ClientCredentialType nella configurazione

1. Aggiungere un elemento di associazione appropriata di [  **\<associazioni >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento del file di configurazione. L'esempio seguente aggiunge un [  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.

1. Aggiungere un  **\<associazione >** elemento e impostare il relativo `name` attributo su un valore appropriato. Nell'esempio viene utilizzato il nome `MessageSecurity`.

1. Aggiungere un  **\<sicurezza >** elemento e impostare il `mode` attributo `Message`.

1. All'interno di  **\<sicurezza >** elemento, aggiungere un  **\<messaggio >** elemento e impostare il `clientCredentialType` attributo `Certificate`.

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
