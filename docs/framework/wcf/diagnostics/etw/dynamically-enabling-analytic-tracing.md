---
title: Abilitazione dinamica della traccia analitica
ms.date: 03/30/2017
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
ms.openlocfilehash: 22d122f802e82c2aa04d72a996cb872e06fcaeaa
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674948"
---
# <a name="dynamically-enabling-analytic-tracing"></a>Abilitazione dinamica della traccia analitica
Utilizzando gli strumenti forniti con il sistema operativo Windows, è possibile abilitare o disabilitare la traccia in modo dinamico utilizzando Traccia eventi per Windows (ETW). Per [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] tutti i servizi Windows Communication Foundation (WCF), la traccia analitica può essere abilitata e disabilitata in modo dinamico senza modificare il file Web.config dell'applicazione o riavviare il servizio. In questo modo l'applicazione che genera gli eventi di traccia non subisce variazioni.  
  
 Le opzioni di traccia WCF possono essere configurate in modo simile. È ad esempio possibile impostare il livello di gravità da **Error** su **Information** senza interferire con l'applicazione. A tale scopo utilizzare gli strumenti seguenti:  
  
- **Logman** : strumento da riga di comando per la configurazione, il controllo e l'esecuzione di query sui dati di traccia. Per ulteriori informazioni, vedere [Logman Create Trace](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc788036(v=ws.10)) and [Logman Update Trace](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc788128(v=ws.10)).  
  
- **EventViewer** : strumento di gestione grafica Windows per visualizzare i risultati della traccia. Per ulteriori informazioni, vedere [Servizi WCF e traccia eventi per Windows](../../samples/wcf-services-and-event-tracing-for-windows.md) e [Visualizzatore eventi](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc766042(v=ws.11)).  
  
- **Perfmon** : strumento di gestione grafica Windows che utilizza contatori per monitorare i contatori di tracce e gli effetti della traccia sulle prestazioni. Per ulteriori informazioni, vedere Creare manualmente un insieme agenti [di raccolta dati.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc766404(v=ws.11))  
  
### <a name="keywords"></a>Parole chiave  
 In caso di utilizzo della classe <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> , i messaggi di traccia di .NET Framework vengono in genere filtrati in base al livello di gravità (ad esempio, Error, Warning e Information). ETW supporta il concetto del livello di gravità, ma introduce un nuovo meccanismo di filtro flessibile mediante parole chiave. Le parole chiave sono costituite da valori testuali arbitrari che consentono agli eventi di traccia di fornire contesto aggiuntivo sul significato dell'evento.  
  
 Per la traccia analitica WCF, ogni evento di traccia dispone di due tipi di parole chiave. Ogni evento dispone in primo luogo di una o più parole chiave di scenari. Queste parole chiave indicano gli scenari che l'evento deve supportare. Sono presenti tre parole chiave di scenari, ognuna progettata per un fine specifico, come indicato nella tabella seguente. Il filtro tramite parole chiave può essere modificato in modo dinamico senza disturbare il servizio WCF. Ciò significa che è possibile modificare in modo dinamico lo scenario di traccia corrente e la quantità di informazioni raccolte sulla traccia. È ad esempio possibile impostare `HealthMonitoring` su `Troubleshooting` e aumentare la granularità dell'evento di traccia.  
  
|Parola chiave|Descrizione|  
|-------------|-----------------|  
|`HealthMonitoring`|Traccia molto leggera, minima che consente di monitorare l'attività del servizio.|  
|`EndToEndMonitoring`|Eventi utilizzati per supportare la traccia del flusso di messaggi.|  
|`Troubleshooting`|Eventi più granulari intorno ai punti di estendibilità di WCF.|  
  
 Il secondo gruppo di parole chiave definisce quale componente di .NET Framework ha generato l'evento.  
  
|Parola chiave|Descrizione|  
|-------------|-----------------|  
|`UserEvents`|Eventi generati dal codice utente e non da .NET Framework.|  
|`ServiceModel`|Eventi generati dal runtime WCF.|  
|`ServiceHost`|Eventi generati dall'host del servizio.|  
|`WCFMessageLogging`|Eventi di registrazione dei messaggi WCF.|  
  
## <a name="see-also"></a>Vedere anche

- [WCF Services and Event Tracing for Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
