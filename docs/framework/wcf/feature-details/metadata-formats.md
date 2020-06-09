---
title: Formati dei metadati
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: a74a57843beaba09b969678a34cad3ad8bed7050
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598840"
---
# <a name="metadata-formats"></a>Formati dei metadati
Windows Communication Foundation (WCF) supporta i formati di metadati nella tabella seguente.  
  
## <a name="metadata-specifications-and-usage"></a>Specifiche e utilizzo dei metadati  
  
|Protocollo|Specifica e utilizzo|  
|--------------|-----------------------------|  
|WSDL 1.1|[Pagina relativa a WSDL (Web Services Description Language) 1.1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF utilizza Web Services Description Language (WSDL) per descrivere i servizi.|  
|XML Schema|[XML Schema Part 2: Datatypes Second Edition](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/) e [XML Schema Part 1: Structures Second Edition](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> WCF utilizza lo schema XML per descrivere i tipi di dati utilizzati nei messaggi.|  
|WS Policy|[Web Services Policy 1.2 - Framework (WS-Policy)  (la pagina potrebbe essere in inglese)](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Web Services Policy 1.5 - Framework  (la pagina potrebbe essere in inglese)](https://www.w3.org/TR/ws-policy/)<br /><br /> WCF utilizza le specifiche WS-Policy 1,2 o 1,5 con le asserzioni specifiche del dominio per descrivere le funzionalità e i requisiti del servizio.|  
|WS Policy Attachments|[Web Services Policy 1.2 - Attachment (WS-PolicyAttachment)  (la pagina potrebbe essere in inglese)](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> WCF implementa gli allegati WS-Policy per allegare espressioni di criteri in diversi ambiti in WSDL.|  
|WS Metadata Exchange|[Web Services Metadata Exchange (WS-MetadataExchange) versione 1.1  (la pagina potrebbe essere in inglese)](https://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
|WS Addressing Binding per WSDL|[Pagina relativa a Web Services Addressing 1.0 - WSDL Binding](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> WCF implementa il binding WS-Addressing per WSDL per allegare le informazioni di indirizzamento in WSDL.|  
  
## <a name="see-also"></a>Vedere anche

- [Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL e criteri](wsdl-and-policy.md)
