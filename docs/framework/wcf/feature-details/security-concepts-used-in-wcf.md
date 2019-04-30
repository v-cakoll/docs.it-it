---
title: Concetti relativi alla sicurezza usati in WCF
ms.date: 03/30/2017
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
ms.openlocfilehash: 3ef2b9c104fa15de17a769c9ca9354e5cef085bf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990873"
---
# <a name="security-concepts-used-in-wcf"></a>Concetti relativi alla sicurezza usati in WCF
Sicurezza di Windows Communication Foundation (WCF) viene generata su concetti già in uso e distribuita in varie infrastrutture di sicurezza.  
  
 WCF supporta alcune di quelle infrastrutture, ad esempio SSL Secure Sockets Layer () su HTTP (HTTPS). Tuttavia, WCF va oltre, supportando infrastrutture di sicurezza esistenti tramite l'implementazione standard di sicurezza interoperativi più recenti (ad esempio WS-Security) su messaggi con codifica SOAP. Tanto per l'utilizzo di meccanismi esistenti che di standard interoperativi nuovi, i concetti di sicurezza alla base di entrambi sono gli stessi. La comprensione di concetti sottostanti le infrastrutture esistenti e gli standard più recenti è fondamentale per l'implementazione del modello di sicurezza migliore per un'applicazione.  
  
## <a name="introduction-to-security-for-wcf-web-services"></a>Introduzione alla sicurezza per i servizi Web WCF  
 Il gruppo Microsoft Patterns and Practices ha scritto un white paper dettagliato sui indicazioni sulla sicurezza WCF disponibile per il download qui: [Guida alla sicurezza WCF](https://go.microsoft.com/fwlink/?LinkId=210210). In questo white paper vengono descritti i concetti di sicurezza fondamentali relativi ai servizi Web, i principali concetti di sicurezza di WCF, gli scenari di applicazione nell'Intranet e gli scenari di applicazione in Internet.  
  
## <a name="industry-wide-security-specifications"></a>Specifiche di sicurezza del settore  
  
### <a name="public-key-infrastructure"></a>Infrastruttura a chiave pubblica  
 L'infrastruttura a chiave pubblica (PKI) è un sistema di certificati digitali, autorità di certificazione e altre autorità di registrazione che verificano e autenticano ogni parte coinvolta in una transazione elettronica tramite l'utilizzo di crittografia a chiave pubblica. Per altre informazioni, vedere [Servizi certificati di Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=210211).  
  
### <a name="kerberos-protocol"></a>Protocollo Kerberos  
 Il *protocollo Kerberos* è una specifica per la creazione di un meccanismo di sicurezza che autentica gli utenti in un dominio di Windows. Consente a un utente di stabilire un contesto protetto con altre entità in un dominio. Windows 2000 e le piattaforme successive utilizzano il protocollo Kerberos per impostazione predefinita. La comprensione dei meccanismi del sistema è utile in caso di creazione di un servizio che dovrà interagire con i client Intranet. Poiché, inoltre, il *associazione Kerberos di Web Services Security* è ampiamente pubblicato, è possibile usare il protocollo Kerberos per comunicare con i client Internet (ovvero, il protocollo Kerberos è interoperativo). Per altre informazioni sulle modalità di implementazione del protocollo Kerberos in Windows, vedere [Microsoft Kerberos](https://go.microsoft.com/fwlink/?LinkId=210212).  
  
### <a name="x509-certificates"></a>Certificati X.509  
 I certificati X.509 costituiscono un form di credenziali primario utilizzato nelle applicazioni di sicurezza. Per altre informazioni su X.509 Vedere certificati [certificati chiave pubblica X.509](https://go.microsoft.com/fwlink/?LinkId=210213). I certificati X.509 vengono archiviati all'interno di un archivio certificati. I computer che eseguono Windows dispongono di vari tipi di archivi certificati, ognuno dei quali con un scopo diverso. Per altre informazioni sugli archivi diversi, vedere [archivi certificati](https://go.microsoft.com/fwlink/?LinkID=87787).  
  
## <a name="web-services-security-specifications"></a>Specifiche di sicurezza dei servizi Web  
 Le associazioni definite dal sistema supportano molte specifiche di sicurezza di servizi Web di uso comune. Per un elenco completo delle associazioni fornite dal sistema e le specifiche dei servizi web supportate, vedere: [Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
  
## <a name="access-control-mechanisms"></a>Meccanismi del controllo di accesso  
 WCF fornisce numerosi modi per controllare l'accesso a un servizio o un'operazione, tra i quali:  
  
1. <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2. Provider di appartenenze ASP.NET  
  
3. Provider di ruoli ASP.NET  
  
4. Gestione autorizzazioni  
  
5. Modello di identità  
  
 Per altre informazioni su questi argomenti, vedere [meccanismi di controllo di accesso](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Modello di sicurezza per Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
