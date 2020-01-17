---
title: Formati dei metadati
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: e7208a8d5fd6d100ac2a2c4fb1369a571c63e7fc
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212178"
---
# <a name="metadata-formats"></a>Formati dei metadati
Windows Communication Foundation (WCF) supporta i formati di metadati nella tabella seguente.  
  
## <a name="metadata-specifications-and-usage"></a>Specifiche e utilizzo dei metadati  
  
|Protocollo|Specifica e utilizzo|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1,1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF utilizza Web Services Description Language (WSDL) per descrivere i servizi.|  
|XML Schema|[XML Schema Part 2: Datatypes Second Edition](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/) e [XML Schema Part 1: Structures Second Edition](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> WCF utilizza lo schema XML per descrivere i tipi di dati utilizzati nei messaggi.|  
|WS Policy|[Criteri dei servizi Web 1,2-Framework (WS-Policy)](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Criteri dei servizi Web 1,5-Framework](https://www.w3.org/TR/ws-policy/)<br /><br /> WCF utilizza le specifiche WS-Policy 1,2 o 1,5 con le asserzioni specifiche del dominio per descrivere le funzionalità e i requisiti del servizio.|  
|WS Policy Attachments|[Criteri dei servizi Web 1,2-allegato (WS-PolicyAttachment)](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> WCF implementa gli allegati WS-Policy per allegare espressioni di criteri in diversi ambiti in WSDL.|  
|WS Metadata Exchange|[Web Services Metadata Exchange (WS-MetadataExchange) versione 1,1](https://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
|WS Addressing Binding per WSDL|[Web Services Addressing 1,0-WSDL binding](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> WCF implementa il binding WS-Addressing per WSDL per allegare le informazioni di indirizzamento in WSDL.|  
  
## <a name="see-also"></a>Vedere anche

- [Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL e criteri](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
