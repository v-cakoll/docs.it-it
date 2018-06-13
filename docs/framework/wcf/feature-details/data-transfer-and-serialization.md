---
title: Trasferimento dati e serializzazione
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 53c1421bf14c598611e116c61353c4ecd465f1aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489206"
---
# <a name="data-transfer-and-serialization"></a>Trasferimento dati e serializzazione
In un sistema collegato, per eseguire qualsiasi attività, servizi e client dipendono dallo scambio di dati. Gli sviluppatori di un servizio o client, è necessario comprendere come Windows Communication Foundation (WCF) gestisce dati e la serializzazione dei dati per poter creare applicazioni efficienti e facili da gestire.  
  
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
 Descrive una visualizzazione della struttura complessiva di trasferimento dei dati in WCF.  
  
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
