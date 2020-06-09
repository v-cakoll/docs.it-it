---
title: Trasferimento dati e serializzazione
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: b07937b0a94c24a934b17d6cf21b726ee0d4362e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593487"
---
# <a name="data-transfer-and-serialization"></a>Trasferimento dati e serializzazione
In un sistema collegato, per eseguire qualsiasi attività, servizi e client dipendono dallo scambio di dati. In qualità di sviluppatore di un servizio o di un client, è inoltre necessario comprendere il modo in cui Windows Communication Foundation (WCF) gestisce i dati e la serializzazione dei dati per creare applicazioni efficienti e facili da gestire.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Specifying Data Transfer in Service Contracts](specifying-data-transfer-in-service-contracts.md)  
 Descrive i concetti di base del trasferimento dati nei servizi.  
  
 [Using Data Contracts](using-data-contracts.md)  
 Descrive i contratti dati, come crearli e utilizzarli.  
  
 [Serializzatore dei contratti dati](data-contract-serializer.md)  
 Descrive come eseguire la serializzazione di dati con la classe <xref:System.Runtime.Serialization.DataContractSerializer> o qualsiasi estensione della classe <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 [Utilizzo della classe XmlSerializer](using-the-xmlserializer-class.md)  
 Descrive come e perché utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>, un'alternativa alla classe <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 [Utilizzo dei contratti di messaggio](using-message-contracts.md)  
 Descrive in che modo i contratti di messaggio consentono il controllo accurato di messaggi SOAP.  
  
 [Utilizzo della classe Message](using-the-message-class.md)  
 Descrive come utilizzare le funzionalità di una classe Message.  
  
 [Filtro](filtering.md)  
 Descrive il filtraggio, che consente la pre-elaborazione di un messaggio basata su vari criteri.  
  
 [Flussi e dati di grandi dimensioni](large-data-and-streaming.md)  
 Descrive come inviare un grande blocco di dati, ad esempio un file binario.  
  
 [Considerazioni sulla sicurezza per i dati](security-considerations-for-data.md)  
 Descrive gli elementi da prendere in considerazione quando si programma il trasferimento dei dati e la serializzazione.  
  
 [Panoramica dell'architettura di trasferimento dei dati](data-transfer-architectural-overview.md)  
 Viene descritta una visualizzazione della progettazione complessiva del trasferimento dei dati in WCF.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Estensione di codificatori e serializzatori](../extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a>Vedere anche

- [Procedure consigliate: controllo delle versioni del contratto dati](../best-practices-data-contract-versioning.md)
- [Controllo delle versioni dei servizi](../service-versioning.md)
