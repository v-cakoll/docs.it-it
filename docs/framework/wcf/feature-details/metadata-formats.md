---
title: Formati dei metadati
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: 55f68f4b56e50b19da19ecc941e9ec537b846006
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038571"
---
# <a name="metadata-formats"></a>Formati dei metadati
Windows Communication Foundation (WCF) supporta i formati dei metadati nella tabella seguente.  
  
## <a name="metadata-specifications-and-usage"></a>Specifiche e utilizzo dei metadati  
  
|Protocollo|Specifica e utilizzo|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1.1](https://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF Usa Web Services Description Language (WSDL) per descrivere i servizi.|  
|XML Schema|[XML Schema Part 2: Tipi di dati seconda edizione](https://go.microsoft.com/fwlink/?LinkId=94861) e [XML Schema Part 1: Strutture Second Edition](https://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> WCF Usa lo Schema XML per descrivere i tipi di dati utilizzati nei messaggi.|  
|WS Policy|[Web Services Policy 1.2 - Framework (WS-Policy)](https://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Web Services Policy 1.5 - Framework](https://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> WCF Usa WS-Policy 1.2 o 1.5 insieme con asserzioni specifiche del dominio per descrivere le funzionalità e requisiti del servizio.|  
|WS Policy Attachments|[Web Services Policy 1.2 - Attachment (WS-PolicyAttachment)](https://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> WCF implementa WS-PolicyAttachments per allegare espressioni di criteri a vari ambiti in WSDL.|  
|WS Metadata Exchange|[Web Services Metadata Exchange (WS-MetadataExchange) versione 1.1](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
|WS Addressing Binding per WSDL|[Web Services Addressing 1.0 - WSDL Binding](https://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> WCF implementa WS-Addressing Binding per WSDL per collegare informazioni di indirizzamento in WSDL.|  
  
## <a name="see-also"></a>Vedere anche

- [Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL e criteri](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
