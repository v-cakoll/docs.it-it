---
title: Uso di ServiceThrottlingBehavior per controllare le prestazioni dei servizi WCF
ms.date: 03/30/2017
helpviewer_keywords:
- behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
ms.openlocfilehash: e42f44b5fa103d5c083bdce3086b6499c5bb3673
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767188"
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a>Uso di ServiceThrottlingBehavior per controllare le prestazioni dei servizi WCF
La classe <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> espone proprietà che possono essere usate per limitare il numero di istanze o sessioni create al livello dell'applicazione. Tramite questo comportamento, è possibile ottimizzare le prestazioni dell'applicazione Windows Communication Foundation (WCF).  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Controllo delle istanze di servizio e delle chiamate contemporanee  
 Usare la proprietà <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> per specificare il numero massimo di messaggi elaborati attivamente in una classe <xref:System.ServiceModel.ServiceHost> e la proprietà <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> per specificare il numero massimo di oggetti <xref:System.ServiceModel.InstanceContext> nel servizio.  
  
 Poiché che determina le impostazioni per queste proprietà in genere avviene dopo l'esperienza in scenari reali eseguendo l'applicazione con carichi, le impostazioni per il <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> proprietà viene in genere specificate in un file di configurazione dell'applicazione tramite il [ \<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) elemento.  
  
 L'esempio di codice seguente mostra come usare la classe <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> da un file di configurazione dell'applicazione che imposta le proprietà <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> e <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> su 1 a scopo di esempio. L'esperienza in scenari reali determina le impostazioni ottimali per qualsiasi applicazione specifica.  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 L'esatto comportamento in fase di esecuzione dipende dai valori delle proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> e <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> che controllano rispettivamente il numero dei messaggi che possono essere eseguiti simultaneamente in un'operazione e la durata della classe <xref:System.ServiceModel.InstanceContext> del servizio relativa alle sessioni del canale in ingresso.  
  
 Per informazioni dettagliate, vedere <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> e <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
