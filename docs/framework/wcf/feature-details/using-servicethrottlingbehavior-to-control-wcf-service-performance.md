---
title: Uso di ServiceThrottlingBehavior per controllare le prestazioni dei servizi WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 01f3815c095012d10fdfd56893125135c35f8009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a>Uso di ServiceThrottlingBehavior per controllare le prestazioni dei servizi WCF
La classe <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> espone proprietà che possono essere usate per limitare il numero di istanze o sessioni create al livello dell'applicazione. Usando questo comportamento è possibile ottimizzare le prestazioni dell'applicazione [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Controllo delle istanze di servizio e delle chiamate contemporanee  
 Usare la proprietà <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> per specificare il numero massimo di messaggi elaborati attivamente in una classe <xref:System.ServiceModel.ServiceHost> e la proprietà <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> per specificare il numero massimo di oggetti <xref:System.ServiceModel.InstanceContext> nel servizio.  
  
 Carica poiché determinate le impostazioni per queste proprietà in genere avviene dopo l'esecuzione dell'applicazione con esperienza in scenari reali, le impostazioni per il <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> proprietà viene in genere specificato in un file di configurazione dell'applicazione utilizzando la [ \<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) elemento.  
  
 L'esempio di codice seguente mostra come usare la classe <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> da un file di configurazione dell'applicazione che imposta le proprietà <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> e <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> su 1 a scopo di esempio. L'esperienza in scenari reali determina le impostazioni ottimali per qualsiasi applicazione specifica.  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 L'esatto comportamento in fase di esecuzione dipende dai valori delle proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> e <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> che controllano rispettivamente il numero dei messaggi che possono essere eseguiti simultaneamente in un'operazione e la durata della classe <xref:System.ServiceModel.InstanceContext> del servizio relativa alle sessioni del canale in ingresso.  
  
 Per informazioni dettagliate, vedere <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> e <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
