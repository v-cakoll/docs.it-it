---
title: Attivazione basata sulla configurazione in IIS e WAS
ms.date: 03/30/2017
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
ms.openlocfilehash: 5e1672f4dd67950178c95d3e043e16072fcd0ef4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593581"
---
# <a name="configuration-based-activation-in-iis-and-was"></a>Attivazione basata sulla configurazione in IIS e WAS

In genere, quando si ospita un servizio Windows Communication Foundation (WCF) in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS), è necessario fornire un file con estensione svc. Il file con estensione svc contiene il nome del servizio e una factory di host del servizio personalizzata facoltativa. Quest'ulteriore file comporta un sovraccarico ai fini della gestibilità. Con la funzionalità di attivazione basata sulla configurazione non è più necessario disporre di un file con estensione svc e quindi tale sovraccarico viene evitato.

## <a name="configuration-based-activation"></a>Attivazione basata sulla configurazione

L'attivazione basata sulla configurazione acquisisce i metadati posizionati nel file con estensione svc e li sposta nel file Web.config. All'interno dell' `serviceHostingEnvironment` elemento<> è presente un `serviceActivations` elemento <>. All'interno dell' `serviceActivations` elemento <> sono presenti uno o più `add` elementi <>, uno per ogni servizio ospitato. L' `add` elemento <> contiene attributi che consentono di impostare l'indirizzo relativo per il servizio e il tipo di servizio o una factory di host del servizio. Nell'esempio di codice di configurazione riportato di seguito viene illustrato come utilizzare questa sezione.

> [!NOTE]
> Ogni `add` elemento <> deve specificare un servizio o un attributo Factory. È consentita la specifica sia degli attributi del servizio che della factory.

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
> - L' `relativeAddress` attributo deve essere impostato su un indirizzo relativo, ad esempio " \<sub-directory> /Service.svc" o "~/ \< Sub-Directory/Service. svc".
> - Se si registra un indirizzo relativo che non dispone di un'estensione nota associata a WCF, viene generata un'eccezione di configurazione.
> - L'indirizzo specificato è relativo alla radice dell'applicazione virtuale.
> - A causa del modello gerarchico della configurazione, gli indirizzi relativi registrati a livello del computer e del sito vengono ereditati dalle applicazioni virtuali.
> - Le registrazioni in un file di configurazione hanno priorità rispetto alle impostazioni in un file con estensione svc, xamlx, xoml o di un altro tipo.
> - Qualsiasi simbolo '\' (barra rovesciata) in un URI inviato a IIS/WAS viene convertito in modo automatico in un simbolo '/' (barra). Se viene aggiunto un indirizzo relativo che contiene un simbolo '\' e viene inviato a IIS un URI che utilizza l'indirizzo relativo, la barra rovesciata viene convertita in una barra normale e IIS non è in grado di associarla all'indirizzo relativo. IIS invia informazioni di traccia a indicare che non è stata rilevata alcuna corrispondenza.

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>
- [Servizi di hosting](../hosting-services.md)
- [Panoramica dell'hosting dei servizi flusso di lavoro](hosting-workflow-services-overview.md)
- [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
