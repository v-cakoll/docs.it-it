---
title: Configurazione di Internet Information Services 7.0 per Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 3e34f46fbf3ccf12c6a89a7cac96143965d958d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a>Configurazione di Internet Information Services 7.0 per Windows Communication Foundation
Internet Information Services (IIS) 7.0 dispone di una progettazione modulare che consente di installare in modo selettivo i componenti necessari. Questa progettazione si basa sulla nuova tecnologia di componentizzazione basata su manifesti introdotta in [!INCLUDE[wv](../../../../includes/wv-md.md)]. Sono disponibili più di 40 componenti di [!INCLUDE[iisver](../../../../includes/iisver-md.md)] con funzionalità autonome, che possono essere installati in modo indipendente. I professionisti IT possono così personalizzare con facilità l'installazione in base alle esigenze. In questo argomento viene illustrato come configurare [!INCLUDE[iisver](../../../../includes/iisver-md.md)] per utilizzare con Windows Communication Foundation (WCF) e determinare quali componenti sono necessari.  
  
## <a name="minimal-installation-installing-was"></a>Installazione minima: installazione di WAS  
 L'installazione minima dell'intero pacchetto di [!INCLUDE[iisver](../../../../includes/iisver-md.md)] prevede l'installazione del servizio Attivazione processo Windows (WAS, Windows Process Activation Service). Tale servizio è una funzionalità autonoma nonché la sola funzionalità di [!INCLUDE[iisver](../../../../includes/iisver-md.md)] disponibile per tutti i sistemi operativi [!INCLUDE[wv](../../../../includes/wv-md.md)] (Home Basic, Home Premium, Business, Ultimate ed Enterprise).  
  
 Dal Pannello di controllo, fare clic su **programmi** e quindi fare clic su **o disattivazione delle funzionalità Windows attivare** presente in **programmi e funzionalità**, il componente WAS è riportato di elenco come illustrato nella figura seguente.  
  
 ![Consente di attivare le funzionalità o finestra di dialogo Off](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")  
  
 Questa funzionalità presenta i sottocomponenti seguenti:  
  
-   Ambiente .NET  
  
-   API di configurazione  
  
-   Modello di processo  
  
 Se si seleziona il nodo principale di WAS, solo il **modello di processo** sottonodo è selezionata per impostazione predefinita. Si noti che con questa installazione verrà installato solo il servizio WAS poiché non è disponibile alcun supporto per un server Web.  
  
 Per rendere WCF o any [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] applicazione siano funzionanti, controllare il **ambiente .NET** casella di controllo. Ciò significa che tutti i componenti WAS sono necessari per effettuare WCF e [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] per il corretto funzionamento. Questi verranno selezionati automaticamente una volta installati tali componenti.  
  
## <a name="iis-70-default-installation"></a>IIS 7.0: installazione predefinita  
 Controllando il **Internet Information Services** funzionalità, alcuni dei nodi secondari vengono archiviate automaticamente come illustrato nella figura seguente.  
  
 ![Impostazioni predefinite per le funzionalità di IIS 7.0](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")  
  
 Questa è l'installazione predefinita di [!INCLUDE[iisver](../../../../includes/iisver-md.md)]. Con essa è possibile utilizzare [!INCLUDE[iisver](../../../../includes/iisver-md.md)] per gestire contenuto statico (ad esempio pagine HTML e altro contenuto). Tuttavia, non è possibile eseguire [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] o le applicazioni CGI o ospitare servizi WCF.  
  
## <a name="iis-70-installation-with-aspnet-support"></a>IIS 7.0: installazione con supporto ASP.NET  
 È necessario installare [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] perché [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] possa essere eseguito in IIS 7.0. Dopo aver controllato **ASP.NET**, la schermata dovrebbe essere simile alla figura seguente.  
  
 ![Le impostazioni obbligatorie Asp.NET](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")  
  
 Questo è l'ambiente minimo per entrambi WCF e [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] alle applicazioni di utilizzare [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
## <a name="iis-70-installation-with-iis-60-compatibility-components"></a>IIS 7.0: installazione con componenti compatibilità gestione IIS 6.0  
 Quando si installa [!INCLUDE[iisver](../../../../includes/iisver-md.md)] in un sistema con Visual Studio 2005 o di un altro script di automazione o strumenti (ad esempio Adsutil.vbs) che consentono di configurare le applicazioni virtuali che utilizzano [!INCLUDE[iis601](../../../../includes/iis601-md.md)] Metabase API, accertarsi di aver letto la [!INCLUDE[iis601](../../../../includes/iis601-md.md)]  **Gli strumenti di scripting**. Verifica automaticamente gli altri nodi secondari del [!INCLUDE[iis601](../../../../includes/iis601-md.md)] **compatibilità di gestione**. Nell'illustrazione seguente viene mostrata la schermata visualizzata dopo l'esecuzione di questa operazione.  
  
 ![Impostazioni di compatibilità IIS 6.0 Management](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")  
  
 Con questa installazione, si dispone di tutto è necessario utilizzare [!INCLUDE[iisver](../../../../includes/iisver-md.md)], [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] esempi disponibili sul Web e le funzionalità WCF.  
  
## <a name="request-limits"></a>Limiti di richiesta.  
 In [!INCLUDE[wv](../../../../includes/wv-md.md)] con IIS 7 il valore predefinito delle impostazioni `maxUri` e `maxQueryStringSize` è stato modificato. Per impostazione predefinita, il filtro di richiesta in IIS 7.0 consente una lunghezza dell'URL di 4096 caratteri e una lunghezza della stringa di query di 2048 caratteri. Per modificare questi valori predefiniti, aggiungere il codice XML seguente al file App.config:  
  
 `<system.webServer>`  
  
 `<security>`  
  
 `<requestFiltering>`  
  
 `<requestLimits maxUrl="8192" maxQueryString="8192" />`  
  
 `</requestFiltering>`  
  
 `</security>`  
  
 `</system.webServer>`  
  
## <a name="see-also"></a>Vedere anche  
 [Architettura di attivazione di WAS](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)  
 [Configurazione di WAS per l'uso con WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)  
 [Procedura: Installare e configurare componenti di attivazione WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)  
 [Windows Server AppFabric con funzionalità di Hosting](http://go.microsoft.com/fwlink/?LinkId=201276)
