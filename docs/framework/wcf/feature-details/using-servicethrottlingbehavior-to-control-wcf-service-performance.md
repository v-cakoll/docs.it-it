---
title: Uso di ServiceThrottlingBehavior per controllare le prestazioni dei servizi WCF
ms.date: 03/30/2017
helpviewer_keywords:
- behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
ms.openlocfilehash: 9cc5141805504bc46391105f475860b032f12d32
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600231"
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a>Uso di ServiceThrottlingBehavior per controllare le prestazioni dei servizi WCF
La classe <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> espone proprietà che possono essere usate per limitare il numero di istanze o sessioni create al livello dell'applicazione. Utilizzando questo comportamento, è possibile ottimizzare le prestazioni dell'applicazione Windows Communication Foundation (WCF).  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Controllo delle istanze di servizio e delle chiamate contemporanee  
 Usare la proprietà <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> per specificare il numero massimo di messaggi elaborati attivamente in una classe <xref:System.ServiceModel.ServiceHost> e la proprietà <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> per specificare il numero massimo di oggetti <xref:System.ServiceModel.InstanceContext> nel servizio.  
  
 Poiché la determinazione delle impostazioni per queste proprietà viene in genere eseguita dopo l'esperienza del mondo reale che esegue l'applicazione rispetto ai carichi, le impostazioni per le <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> proprietà vengono in genere specificate in un file di configurazione dell'applicazione utilizzando l' [\<serviceThrottling>](../../configure-apps/file-schema/wcf/servicethrottling.md) elemento.  
  
 L'esempio di codice seguente mostra come usare la classe <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> da un file di configurazione dell'applicazione che imposta le proprietà <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> e <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> su 1 a scopo di esempio. L'esperienza in scenari reali determina le impostazioni ottimali per qualsiasi applicazione specifica.  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 L'esatto comportamento in fase di esecuzione dipende dai valori delle proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> e <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> che controllano rispettivamente il numero dei messaggi che possono essere eseguiti simultaneamente in un'operazione e la durata della classe <xref:System.ServiceModel.InstanceContext> del servizio relativa alle sessioni del canale in ingresso.  
  
 Per informazioni dettagliate, vedere <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> e <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
