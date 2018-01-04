---
title: Trasferimento dati e serializzazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8daadec1eef20e62747cdbfcafd1fd13cfc16093
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="data-transfer-and-serialization"></a>Trasferimento dati e serializzazione
In un sistema collegato, per eseguire qualsiasi attività, servizi e client dipendono dallo scambio di dati. Gli sviluppatori di un servizio o di un client devono comprendere inoltre come [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] gestisce i dati e la serializzazione dei dati per creare applicazioni efficienti e facili da gestire.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Definizione del trasferimento dati nei contratti di servizio](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 Descrive i concetti di base del trasferimento dati nei servizi.  
  
 [Uso di contratti di dati](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 Descrive i contratti dati, come crearli e utilizzarli.  
  
 [Serializzatore dei contratti di dati](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 Descrive come eseguire la serializzazione di dati con la classe <xref:System.Runtime.Serialization.DataContractSerializer> o qualsiasi estensione della classe <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 [Uso della classe XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 Descrive come e perché utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>, un'alternativa alla classe <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 [Uso di contratti di messaggio](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 Descrive in che modo i contratti di messaggio consentono il controllo accurato di messaggi SOAP.  
  
 [Uso della classe Message](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 Descrive come utilizzare le funzionalità di una classe Message.  
  
 [Applicazione di filtri](../../../../docs/framework/wcf/feature-details/filtering.md)  
 Descrive il filtraggio, che consente la pre-elaborazione di un messaggio basata su vari criteri.  
  
 [Dati di grandi dimensioni e streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 Descrive come inviare un grande blocco di dati, ad esempio un file binario.  
  
 [Considerazioni sulla sicurezza per i dati](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 Descrive gli elementi da prendere in considerazione quando si programma il trasferimento dei dati e la serializzazione.  
  
 [Panoramica dell'architettura di trasferimento dati](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 Descrive il principio generale del trasferimento dei dati in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Estensione di codificatori e serializzatori](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Procedure consigliate: Controllo delle versioni del contratto di dati](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [Controllo delle versioni dei servizi](../../../../docs/framework/wcf/service-versioning.md)
