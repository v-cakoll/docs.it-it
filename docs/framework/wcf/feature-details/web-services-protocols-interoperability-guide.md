---
title: Guida all'interoperabilità dei protocolli di servizi Web
ms.date: 03/30/2017
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
ms.openlocfilehash: 1b949880b3ebbaf121b79a958d17cf5708affcf3
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636146"
---
# <a name="web-services-protocols-interoperability-guide"></a>Guida all'interoperabilità dei protocolli di servizi Web

Windows Communication Foundation (WCF) implementa una serie di protocolli di servizi Web. Molti di questi protocolli includono diverse opzioni e punti estendibilità lasciati alla discrezione dell'implementatore. In questo argomento viene fornito un elenco di protocolli di servizi Web implementati da WCF. Altri argomenti di questa sezione forniscono dettagli di implementazione per ogni protocollo supportato.

## <a name="web-services-protocols-implemented-by-wcf"></a>Protocolli dei servizi Web implementati da WCF

WCF fornisce il supporto per i protocolli di infrastruttura di servizi Web (WS) tramite canali e protocolli applicativi di servizi Web tramite la funzionalità contratti. L'interoperabilità per i protocolli di applicazioni è ottenuta tramite il linguaggio XSD (XML Description Language) 1.0 e il linguaggio WSDL (Web Services Description Language) 1.1.

L'interoperabilità dei protocolli dell'infrastruttura è garantita dalle specifiche WS-*. I canali WCF offrono il supporto per numerosi protocolli dell'infrastruttura WS-\*. I canali WCF vengono configurati tramite elementi di associazione. Le tabelle seguenti contengono l'elenco completo dei protocolli dell'infrastruttura WS-\* implementati da vari elementi di associazione WCF.

<xref:System.ServiceModel.Channels.HttpTransportBindingElement> supporta le specifiche indicate nella tabella seguente.

|Specifica/documento|Collegamento|
|-----------------------------|----------|
|HTTP 1.1|[RFC 2616](https://www.rfc-editor.org/rfc/rfc2616.txt)|
|Associazione SOAP 1,1 HTTP|[Simple Object Access Protocol (SOAP) 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), sezione 7|
|Associazione SOAP 1,2 HTTP|[SOAP versione 1,2 parte 2: aggiunte (seconda edizione)](https://www.w3.org/TR/soap12-part2/), sezione 7|

<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> e <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> supportano le specifiche indicate nella tabella seguente.

|Specifica/documento|Collegamento|
|-----------------------------|----------|
|XML|[Extensible Markup Language (XML) 1,0 (quarta edizione)](https://www.w3.org/TR/REC-xml/)|
|SOAP 1,1|[Simple Object Access Protocol (SOAP) 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)|
|SOAP 1.2 Core|[Versione SOAP 1,2 parte 1: Framework di messaggistica (seconda edizione)](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)|
|WS-Addressing 2004/08|[Indirizzamento dei servizi Web (WS-Addressing)](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)|
|W3C Web Services Addressing 1.0 - Core|[Web Services Addressing 1,0-Core](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509/)|
|W3C Web Services Addressing 1.0 - SOAP Binding|[Indirizzamento dei servizi Web 1,0-binding SOAP](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509/)|
|W3C Web Services Addressing 1.0 - WSDL Binding*|[Web Services Addressing 1,0-WSDL binding](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)|
|W3C Web Services Addressing 1.0 - Metadata|[Indirizzamento dei servizi Web 1,0-metadati](https://www.w3.org/TR/ws-addr-metadata/)|
|Associazione WSDL SOAP1.1|[Web Services Description Language (WSDL) 1,1](https://www.w3.org/TR/wsdl/)|
|WSDL SOAP1.2 Binding|[Estensione di binding WSDL 1,1 per SOAP 1,2](https://www.w3.org/Submission/wsdl11soap12/)|

<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> supporta le specifiche indicate nella tabella seguente.

|Specifica/documento|Collegamento|
|-----------------------------|----------|
|XOP|[Creazione di pacchetti con ottimizzazione binaria XML](https://www.w3.org/TR/xop10/)|
|Associazione MTOM + SOAP1.2|[Meccanismo di ottimizzazione della trasmissione del messaggio SOAP](https://www.w3.org/TR/soap12-mtom/)|
|Associazione MTOM SOAP 1.1|[Binding SOAP 1,1 per MTOM 1,0](https://www.w3.org/Submission/soap11mtom10/)|
|MTOM WS-PolicyAssertions|[Asserzione di criteri di serializzazione MTOM (WS-MTOMPolicy)](https://www.w3.org/Submission/WS-MTOMPolicy/)|

<xref:System.ServiceModel.Channels.SecurityBindingElement> supporta le specifiche indicate nella tabella seguente.

|Specifica/documento|Collegamento|
|-----------------------------|----------|
|WSS: SOAP Message Security 1,0|[Web Services Security: sicurezza messaggio SOAP 1,0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)|
|WSS: Username Token Profile 1.0|[Web Services Security UsernameToken profilo 1,0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> Richiedi Password/@Type= PasswordText (impostazione predefinita)|
|WSS: X.509 Token Profile 1.0|[Profilo del token del certificato X. 509 Web Services Security](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)|
|WSS: SAML 1.1 Token Profile 1.0|[Web Services Security: profilo token SAML](https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf)|
|WSS: SOAP Message Security 1.1|[Web Services Security: sicurezza messaggio SOAP 1,1](https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf)|
|WSS Username Token Profile 1.1|[Web Services Security UsernameToken profilo 1,1](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> non implementare la funzionalità di derivazione della chiave basata su password;<br /><br /> Richiedi Password/@Type= PasswordText (impostazione predefinita)|
|WSS: X509 Token Profile 1.1|[Web Services Security profilo token certificato X. 509 1,1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)|
|WSS: Kerberos Token Profile 1.1|[Web Services Security il profilo del token Kerberos 1,1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)|
|WSS: SAML 1.1 Token Profile 1.1|[Web Services Security profilo token SAML 1,1](https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf)|
|WS-Secure Conversation|[Linguaggio di conversazione protetta dei servizi Web](https://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)|
|WS-Trust 1.4|[Lingua del trust dei servizi Web](https://docs.oasis-open.org/ws-sx/ws-trust/200802)|
|WS-SecurityPolicy 2005/07|[Linguaggio di conversazione protetta dei servizi Web](https://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> Rettificato in base all'errata corrige inviato all'OASIS WS-SX TC.<br /><br /> [messaggio WS-SX](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html)|
|WS-ReliableMessaging 1.1|[Protocollo Reliable Messaging versione 1.1](reliable-messaging-protocol-version-1-1.md)|

<xref:System.ServiceModel.Channels.TransactionFlowBindingElement> supporta le specifiche indicate nella tabella seguente.

|Specifica/documento|Collegamento|
|-----------------------------|----------|
|WS-Coordination|[Coordinamento dei servizi Web](https://docs.microsoft.com/previous-versions/ms951231(v=msdn.10))|
|WS-AtomicTransaction|[Transazione atomica dei servizi Web](https://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)|

Le classi <xref:System.ServiceModel.Description.MetadataExporter>, <xref:System.ServiceModel.Description.MetadataImporter>, <xref:System.ServiceModel.Description.WsdlExporter>, <xref:System.ServiceModel.Description.WsdlImporter> e <xref:System.ServiceModel.Description.MetadataResolver> forniscono il supporto per le specifiche di metadati seguenti:

- [XML Schema Part 1: Structures Second Edition](https://www.w3.org/TR/xmlschema-1/)

- [XML Schema Part 2: tipi di dati seconda edizione](https://www.w3.org/TR/xmlschema-2/)

- [WSDL 1.1](https://www.w3.org/TR/wsdl/)

- [WS-Policy 1,2](https://www.w3.org/Submission/2006/SUBM-WS-Policy-20060425/)

- [WS-Policy 1,5](https://www.w3.org/TR/ws-policy/)

- [WS-PolicyAttachment 1,2](https://www.w3.org/Submission/2006/SUBM-WS-PolicyAttachment-20060425/)

- [WS-MetadataExchange 1.1](https://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)

- [WS-Transfer Get per il recupero dei metadati](https://www.w3.org/Submission/2006/SUBM-WS-Transfer-20060315/)

Inoltre, i profili di interoperabilità seguenti vengono implementati in WCF:

- [Profilo di base 1,1](http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html)

- [Binding SOAP semplice 1,0](http://www.ws-i.org/Profiles/SimpleSoapBindingProfile-1.0-2004-08-24.html)

- [Bozza di lavoro di Basic Security Profile 1,0](http://www.ws-i.org/Profiles/BasicSecurityProfile-1.0-2006-03-29.html)

## <a name="see-also"></a>Vedere anche

- [Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [Protocolli di messaggistica](messaging-protocols.md)
- [Informazioni di riferimento sullo schema del contratto di dati](data-contract-schema-reference.md)
- [WSDL e criteri](wsdl-and-policy.md)
- [Protocolli di sicurezza](security-protocols.md)
- [Protocollo Reliable Messaging versione 1.0](reliable-messaging-protocol-version-1-0.md)
- [Protocollo Reliable Messaging versione 1.1](reliable-messaging-protocol-version-1-1.md)
- [Protocolli di transazione](transaction-protocols.md)
- [Protocollo di scambio del contesto](context-exchange-protocol.md)
