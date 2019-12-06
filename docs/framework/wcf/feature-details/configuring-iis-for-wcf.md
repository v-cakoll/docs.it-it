---
title: Configurazione di Internet Information Services 7.0 per Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 369fd641adc91c58a676a7c2708e267366d73b41
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838052"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a>Configurazione di Internet Information Services 7.0 per Windows Communication Foundation

Internet Information Services (IIS) 7.0 dispone di una progettazione modulare che consente di installare in modo selettivo i componenti necessari. Questa progettazione è basata sulla nuova tecnologia di componentizzazione basata su manifesto introdotta in Windows Vista. Sono presenti più di 40 componenti di funzionalità autonomi di IIS 7,0 che possono essere installati in modo indipendente. I professionisti IT possono così personalizzare con facilità l'installazione in base alle esigenze. In questo argomento viene illustrato come configurare IIS 7,0 per l'utilizzo con Windows Communication Foundation (WCF) e come determinare i componenti necessari.

## <a name="minimal-installation-installing-was"></a>Installazione minima: installazione di WAS
 L'installazione minima dell'intero pacchetto IIS 7,0 consiste nell'installare il servizio Attivazione processo Windows (WAS). WAS è una funzionalità autonoma ed è l'unica funzionalità di IIS 7,0 disponibile per tutti i sistemi operativi Windows Vista (Home Basic, Home Premium, business, Ultimate ed Enterprise).

 Nel pannello di controllo fare clic su **programmi** e quindi **su attivazione o disattivazione delle funzionalità Windows** elencate in **programmi e funzionalità**. il componente was viene visualizzato nell'elenco, come illustrato nella figura seguente.

 ![Attivare o disattivare le funzionalità finestra di dialogo](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")

 Questa funzionalità presenta i sottocomponenti seguenti:

- Ambiente .NET

- API di configurazione

- Modello di processo

 Se si seleziona il nodo radice di WAS, per impostazione predefinita viene selezionato solo il sottonodo del **modello di processo** . Si noti che con questa installazione verrà installato solo il servizio WAS poiché non è disponibile alcun supporto per un server Web.

 Per far funzionare WCF o qualsiasi applicazione ASP.NET, selezionare la casella di controllo **ambiente .NET** . Ciò significa che tutti i componenti di WAS sono necessari per garantire il corretto funzionamento di WCF e ASP.NET. Questi verranno selezionati automaticamente una volta installati tali componenti.

## <a name="iis-70-default-installation"></a>IIS 7.0: installazione predefinita
 Controllando la funzionalità **Internet Information Services** , alcuni dei sottonodi vengono controllati automaticamente, come illustrato nella figura seguente.

 ![Impostazioni predefinite per le funzionalità di IIS 7,0](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")

 Questa è l'installazione predefinita di IIS 7,0. Con questa installazione è possibile usare IIS 7,0 per il servizio di contenuto statico, ad esempio pagine HTML e altro contenuto. Tuttavia, non è possibile eseguire applicazioni ASP.NET o CGI né ospitare servizi WCF.

## <a name="iis-70-installation-with-aspnet-support"></a>IIS 7.0: installazione con supporto ASP.NET
 È necessario installare ASP.NET per fare in modo che ASP.NET funzioni in IIS 7,0. Dopo aver controllato **ASP.NET**, la schermata dovrebbe essere simile alla figura seguente.

 ![Impostazioni obbligatorie Asp.NET](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")

 Si tratta dell'ambiente minimo per le applicazioni WCF e ASP.NET per il funzionamento in IIS 7,0.

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a>IIS 7.0: installazione con componenti compatibilità gestione IIS 6.0
 Quando si installa IIS 7,0 in un sistema con Visual Studio 2005 o altri script o strumenti di automazione (ad esempio adsutil. vbs) che configurano le applicazioni virtuali che utilizzano l'API metabase di IIS 6,0, assicurarsi di controllare gli **strumenti di script**di IIS 6,0. Questa operazione Controlla automaticamente gli altri sottonodi della compatibilità di **gestione**con IIS 6,0. Nella figura seguente viene mostrata la schermata dopo questa operazione:

 ![Impostazioni di compatibilità Gestione IIS 6,0](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")

 Con questa installazione, sono disponibili tutti gli elementi necessari per usare le funzionalità e gli esempi di IIS 7,0, ASP.NET e WCF disponibili sul Web.

## <a name="request-limits"></a>Limiti richiesta
 In Windows Vista con IIS 7 il valore predefinito del `maxUri` e le impostazioni di `maxQueryStringSize` sono state modificate. Per impostazione predefinita, il filtro di richiesta in IIS 7.0 consente una lunghezza dell'URL di 4096 caratteri e una lunghezza della stringa di query di 2048 caratteri. Per modificare questi valori predefiniti, aggiungere il codice XML seguente al file App.config:

```xml
 <system.webServer>
    <security>
        <requestFiltering>
            <requestLimits maxUrl="8192" maxQueryString="8192" />
        </requestFiltering>
    </security>
 </system.webServer>
 ```

## <a name="see-also"></a>Vedere anche

- [Architettura di attivazione di WAS](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [Configurazione di WAS per l'uso con WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [Procedura: Installare e configurare componenti di attivazione WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=201276)
