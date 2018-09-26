---
title: Guida di interoperabilità dei protocolli di servizi Web
ms.date: 03/30/2017
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
ms.openlocfilehash: 37416a80c8b6f2ac086dbface1cda37609698bfc
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47204427"
---
# <a name="web-services-protocols-interoperability-guide"></a>Guida di interoperabilità dei protocolli di servizi Web
Windows Communication Foundation (WCF) implementi una serie di protocolli di servizi Web. Molti di questi protocolli includono diverse opzioni e punti estendibilità lasciati alla discrezione dell'implementatore. In questo argomento fornisce un elenco di protocolli di servizi Web che WCF implementa. Altri argomenti di questa sezione forniscono dettagli di implementazione per ogni protocollo supportato.  
  
## <a name="web-services-protocols-implemented-by-wcf"></a>Protocolli di servizi Web implementati da WCF  
 WCF fornisce supporto per protocolli dell'infrastruttura di Web services (WS) attraverso canali e protocolli di applicazione tramite la funzionalità dei contratti di servizi Web. L'interoperabilità per i protocolli di applicazioni è ottenuta tramite il linguaggio XSD (XML Description Language) 1.0 e il linguaggio WSDL (Web Services Description Language) 1.1.  
  
 L'interoperabilità dei protocolli dell'infrastruttura è garantita dalle specifiche WS-*. Canali WCF forniscono il supporto per un numero di WS -\* protocolli dell'infrastruttura. Canali WCF vengono configurati mediante elementi di associazione. Le tabelle seguenti contengono l'elenco completo di WS -\* protocolli dell'infrastruttura implementati da vari elementi di associazione di WCF.  
  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> supporta le specifiche indicate nella tabella seguente.  
  
|Specifica/documento|Collegamento|  
|-----------------------------|----------|  
|HTTP 1.1|[RFC 2616](https://go.microsoft.com/fwlink/?LinkId=90372)|  
|Associazione SOAP 1,1 HTTP|[Simple Object Access Protocol (SOAP) 1.1](https://go.microsoft.com/fwlink/?LinkId=90520), sezione 7|  
|Associazione SOAP 1,2 HTTP|[SOAP versione 1.2 parte 2: Aggiunte (seconda edizione)](https://go.microsoft.com/fwlink/?LinkId=95329), sezione 7|  
  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> e <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> supportano le specifiche indicate nella tabella seguente.  
  
|Specifica/documento|Collegamento|  
|-----------------------------|----------|  
|XML|[Extensible Markup Language (XML) 1.0 (Fourth Edition)](https://go.microsoft.com/fwlink/?LinkId=15139)|  
|SOAP 1,1|[Simple Object Access Protocol (SOAP) 1.1](https://go.microsoft.com/fwlink/?LinkId=96687)|  
|SOAP 1.2 Core|[Versione di SOAP 1.2-parte 1: Framework di messaggistica (seconda edizione)](https://go.microsoft.com/fwlink/?LinkId=94664)|  
|WS-Addressing 2004/08|[Web Services Addressing (WS-Addressing)](https://go.microsoft.com/fwlink/?LinkId=81239)|  
|W3C Web Services Addressing 1.0 - Core|[Web Services Addressing 1.0 - Core](https://go.microsoft.com/fwlink/?LinkId=96688)|  
|W3C Web Services Addressing 1.0 - SOAP Binding|[Web Services Addressing 1.0 - SOAP Binding](https://go.microsoft.com/fwlink/?LinkId=96689)|  
|W3C Web Services Addressing 1.0 - WSDL Binding*|[Web Services Addressing 1.0 - WSDL Binding](https://go.microsoft.com/fwlink/?LinkId=96690)|  
|W3C Web Services Addressing 1.0 - Metadata|[Web Services Addressing 1.0 - Metadata](http://www.w3.org/TR/ws-addr-metadata/)|  
|Associazione WSDL SOAP1.1|[Web Services Description Language (WSDL) 1.1](https://go.microsoft.com/fwlink/?LinkId=96160)|  
|Associazione WSDL SOAP1.2|[Estensione di Binding 1.1 WSDL per SOAP 1.2](https://go.microsoft.com/fwlink/?LinkId=96691)|  
  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> supporta le specifiche indicate nella tabella seguente.  
  
|Specifica/documento|Collegamento|  
|-----------------------------|----------|  
|XOP|[XML binario ottimizzato per la creazione di pacchetti](https://go.microsoft.com/fwlink/?LinkId=96714)|  
|Associazione MTOM + SOAP1.2|[SOAP MTOM](https://go.microsoft.com/fwlink/?LinkId=96713)|  
|Associazione MTOM SOAP 1.1|[SOAP 1.1 associazione relativa a MTOM 1.0](https://go.microsoft.com/fwlink/?LinkId=96712)|  
|MTOM WS-PolicyAssertions|Non ancora pubblicato.|  
  
 <xref:System.ServiceModel.Channels.SecurityBindingElement> supporta le specifiche indicate nella tabella seguente.  
  
|Specifica/documento|Collegamento|  
|-----------------------------|----------|  
|WSS: SOAP Message Security 1,0|[Web Services Security: SOAP Message Security 1,0](https://go.microsoft.com/fwlink/?LinkId=94684)|  
|WSS: Username Token Profile 1.0|[Web Services Security Kerberos token Profile 1.0](https://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> Richiedi Password/@Type= PasswordText (impostazione predefinita)|  
|WSS: X.509 Token Profile 1.0|[Web Services Security X.509 Certificate Token Profile](https://go.microsoft.com/fwlink/?LinkId=95335)|  
|WSS: SAML 1.1 Token Profile 1.0|[Web Services Security: SAML Token Profile](https://go.microsoft.com/fwlink/?LinkId=96693)|  
|WSS: SOAP Message Security 1.1|[Web Services Security: SOAP Message Security 1.1](https://go.microsoft.com/fwlink/?LinkId=91240)|  
|WSS Username Token Profile 1.1|[Web Services Security UsernameToken Profile 1.1](https://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> non implementare la funzionalità di derivazione della chiave basata su password;<br /><br /> Richiedi Password/@Type= PasswordText (impostazione predefinita)|  
|WSS: X509 Token Profile 1.1|[Web Services Security X.509 Certificate Token Profile 1.1](https://go.microsoft.com/fwlink/?LinkId=95332)|  
|WSS: Kerberos Token Profile 1.1|[Web Services Security Kerberos Token Profile 1.1](https://go.microsoft.com/fwlink/?LinkId=95333)|  
|WSS: SAML 1.1 Token Profile 1.1|[Web Services Security SAML Token Profile 1,1](https://go.microsoft.com/fwlink/?LinkId=96694)|  
|WS-Secure Conversation|[Linguaggio di conversazione sicura dei servizi Web](https://go.microsoft.com/fwlink/?LinkId=95317)|  
|WS-Trust 1.4|[Lingua dell'attendibilità dei servizi Web](https://go.microsoft.com/fwlink/?LinkId=169514)|  
|WS-SecurityPolicy 2005/07|[Linguaggio di conversazione sicura dei servizi Web](https://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> Rettificato in base all'errata corrige inviato all'OASIS WS-SX TC.<br /><br /> [messaggio di ws-sx TC](https://go.microsoft.com/fwlink/?LinkId=96700)|  
|WS-ReliableMessaging 1.1|[Protocollo Reliable Messaging versione 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)|  
  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> supporta le specifiche indicate nella tabella seguente.  
  
|Specifica/documento|Collegamento|  
|-----------------------------|----------|  
|WS-Coordination|[Coordinamento di servizi Web](https://go.microsoft.com/fwlink/?LinkId=95324)|  
|WS-AtomicTransaction|[Transazione atomica dei servizi Web](https://go.microsoft.com/fwlink/?LinkId=95323)|  
  
 Le classi <xref:System.ServiceModel.Description.MetadataExporter>, <xref:System.ServiceModel.Description.MetadataImporter>, <xref:System.ServiceModel.Description.WsdlExporter>, <xref:System.ServiceModel.Description.WsdlImporter> e <xref:System.ServiceModel.Description.MetadataResolver> forniscono il supporto per le specifiche di metadati seguenti:  
  
-   [XML Schema Part 1: Strutture Second Edition](https://go.microsoft.com/fwlink/?LinkId=3536)  
  
-   [XML Schema Part 2: I tipi di dati seconda edizione](https://go.microsoft.com/fwlink/?LinkId=40138)  
  
-   [WSDL 1.1](https://go.microsoft.com/fwlink/?LinkId=96160)  
  
-   [WS-Policy 1.2](https://go.microsoft.com/fwlink/?LinkId=96705)  
  
-   [WS-Policy 1.5](https://go.microsoft.com/fwlink/?LinkId=96706)  
  
-   [1.2 di WS-PolicyAttachment](https://go.microsoft.com/fwlink/?LinkId=96707)  
  
-   [1.1 di WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)  
  
-   [WS-Transfer Get per il recupero dei metadati](https://go.microsoft.com/fwlink/?LinkId=96708)  
  
 Inoltre, vengono implementati i seguenti profili di interoperabilità tra WCF:  
  
-   [Basic Profile 1.1](https://go.microsoft.com/fwlink/?LinkId=69313)  
  
-   [SOAP semplice associazione 1.0](https://go.microsoft.com/fwlink/?LinkId=96710)  
  
-   [Sicurezza di base del profilo 1.0 Working Draft](https://go.microsoft.com/fwlink/?LinkId=96711)  
  
## <a name="see-also"></a>Vedere anche  
 [Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [Protocolli di messaggistica](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)  
 [Informazioni di riferimento sullo schema del contratto di dati](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)  
 [WSDL e criteri](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)  
 [Protocolli di sicurezza](../../../../docs/framework/wcf/feature-details/security-protocols.md)  
 [Protocollo Reliable Messaging versione 1.0](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-0.md)  
 [Protocollo Reliable Messaging versione 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)  
 [Protocolli di transazione](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)  
 [Protocollo di scambio del contesto](../../../../docs/framework/wcf/feature-details/context-exchange-protocol.md)
