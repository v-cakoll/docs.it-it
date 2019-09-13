---
title: Attivazione basata sulla configurazione in IIS e WAS
ms.date: 03/30/2017
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
ms.openlocfilehash: 5b06f474d26b80f955b1508f01da83448a8708a3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928776"
---
# <a name="configuration-based-activation-in-iis-and-was"></a>Attivazione basata sulla configurazione in IIS e WAS

In genere, quando si ospita un servizio Windows Communication Foundation (WCF) in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS), è necessario fornire un file con estensione svc. Il file con estensione svc contiene il nome del servizio e una factory di host del servizio personalizzata facoltativa. Quest'ulteriore file comporta un sovraccarico ai fini della gestibilità. Con la funzionalità di attivazione basata sulla configurazione non è più necessario disporre di un file con estensione svc e quindi tale sovraccarico viene evitato.

## <a name="configuration-based-activation"></a>Attivazione basata sulla configurazione

L'attivazione basata sulla configurazione acquisisce i metadati posizionati nel file con estensione svc e li sposta nel file Web.config. All'interno dell'`serviceHostingEnvironment`elemento < > è presente un`serviceActivations`elemento < >. All'interno dell'`serviceActivations`elemento < > sono presenti uno o`add`più elementi < >, uno per ogni servizio ospitato. L'elemento`add`< > contiene attributi che consentono di impostare l'indirizzo relativo per il servizio e il tipo di servizio o una factory di host del servizio. Nell'esempio di codice di configurazione riportato di seguito viene illustrato come utilizzare questa sezione.

> [!NOTE]
> Ogni elemento`add`< > deve specificare un servizio o un attributo Factory. È consentita la specifica sia degli attributi del servizio che della factory.

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>
  </serviceActivations>
</serviceHostingEnvironment>
```

 Con questa situazione nel file Web.config è possibile posizionare il codice sorgente del servizio nella directory App_Code dell'applicazione o un assembly compilato nella directory bin dell'applicazione.

> [!NOTE]
>
> - Quando si utilizza l'attivazione basata sulla configurazione, il codice inline presente nei file con estensione svc non è supportato.
> - L' `relativeAddress` attributo deve essere impostato su un indirizzo relativo, ad esempio\<"sub-directory >/Service.svc" o "~\</Sub-Directory/Service. svc".
> - Se si registra un indirizzo relativo che non dispone di un'estensione nota associata a WCF, viene generata un'eccezione di configurazione.
> - L'indirizzo specificato è relativo alla radice dell'applicazione virtuale.
> - A causa del modello gerarchico della configurazione, gli indirizzi relativi registrati a livello del computer e del sito vengono ereditati dalle applicazioni virtuali.
> - Le registrazioni in un file di configurazione hanno priorità rispetto alle impostazioni in un file con estensione svc, xamlx, xoml o di un altro tipo.
> - Qualsiasi simbolo '\' (barra rovesciata) in un URI inviato a IIS/WAS viene convertito in modo automatico in un simbolo '/' (barra). Se viene aggiunto un indirizzo relativo che contiene un simbolo '\' e viene inviato a IIS un URI che utilizza l'indirizzo relativo, la barra rovesciata viene convertita in una barra normale e IIS non è in grado di associarla all'indirizzo relativo. IIS invia informazioni di traccia a indicare che non è stata rilevata alcuna corrispondenza.

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>
- [Servizi di hosting](../../../../docs/framework/wcf/hosting-services.md)
- [Panoramica dell'hosting dei servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)
- [\<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=201276)
