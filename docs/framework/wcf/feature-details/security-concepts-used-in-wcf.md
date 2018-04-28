---
title: Concetti relativi alla sicurezza usati in WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
caps.latest.revision: 15
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 72712e0934646a39c1e03a38716179384051003a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="security-concepts-used-in-wcf"></a>Concetti relativi alla sicurezza usati in WCF
La sicurezza [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] viene generata su concetti già in uso e distribuita in varie infrastrutture di sicurezza.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supporta alcune di quelle infrastrutture, ad esempio Secure Sockets Layer (SSL) su HTTP (HTTPS). [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], tuttavia, va oltre, supportando infrastrutture di sicurezza esistenti tramite l'implementazione di standard di sicurezza interoperativi più recenti (ad esempio WS-Security) su messaggi con codifica SOAP. Tanto per l'utilizzo di meccanismi esistenti che di standard interoperativi nuovi, i concetti di sicurezza alla base di entrambi sono gli stessi. La comprensione di concetti sottostanti le infrastrutture esistenti e gli standard più recenti è fondamentale per l'implementazione del modello di sicurezza migliore per un'applicazione.  
  
## <a name="introduction-to-security-for-wcf-web-services"></a>Introduzione alla sicurezza per i servizi Web WCF  
 Il gruppo Microsoft Patterns and Practices ha scritto un white paper di approfondite sui indicazioni sulla sicurezza WCF che può essere scaricato qui: [Guida alla protezione di WCF](http://go.microsoft.com/fwlink/?LinkId=210210). In questo white paper vengono descritti i concetti di sicurezza fondamentali relativi ai servizi Web, i principali concetti di sicurezza di WCF, gli scenari di applicazione nell'Intranet e gli scenari di applicazione in Internet.  
  
## <a name="industry-wide-security-specifications"></a>Specifiche di sicurezza del settore  
  
### <a name="public-key-infrastructure"></a>Infrastruttura a chiave pubblica  
 L'infrastruttura a chiave pubblica (PKI) è un sistema di certificati digitali, autorità di certificazione e altre autorità di registrazione che verificano e autenticano ogni parte coinvolta in una transazione elettronica tramite l'utilizzo di crittografia a chiave pubblica. Per altre informazioni, vedere [Servizi certificati di Windows Server 2008 R2](http://go.microsoft.com/fwlink/?LinkId=210211).  
  
### <a name="kerberos-protocol"></a>Protocollo Kerberos  
 Il *protocollo Kerberos* è una specifica per la creazione di un meccanismo di sicurezza che autentica gli utenti in un dominio Windows. Consente a un utente di stabilire un contesto protetto con altre entità in un dominio. Windows 2000 e le piattaforme successive utilizzano il protocollo Kerberos per impostazione predefinita. La comprensione dei meccanismi del sistema è utile in caso di creazione di un servizio che dovrà interagire con i client Intranet. Poiché, inoltre, il *associazione Kerberos di Web Services Security* è ampiamente pubblicato, è possibile utilizzare il protocollo Kerberos per comunicare con i client Internet (ovvero, il protocollo Kerberos è interoperativo). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] come il protocollo Kerberos viene implementato in Windows, vedere [Microsoft Kerberos](http://go.microsoft.com/fwlink/?LinkId=210212).  
  
### <a name="x509-certificates"></a>Certificati X.509  
 I certificati X.509 costituiscono un form di credenziali primario utilizzato nelle applicazioni di sicurezza. Per ulteriori informazioni sui certificati x. 509 certificati vedere [certificati x. 509 a chiave pubblica](http://go.microsoft.com/fwlink/?LinkId=210213). I certificati X.509 vengono archiviati all'interno di un archivio certificati. I computer che eseguono Windows dispongono di vari tipi di archivi certificati, ognuno dei quali con un scopo diverso. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] gli archivi diversi, vedere [archivi certificati](http://go.microsoft.com/fwlink/?LinkID=87787).  
  
## <a name="web-services-security-specifications"></a>Specifiche di sicurezza dei servizi Web  
 Le associazioni definite dal sistema supportano molte specifiche di sicurezza di servizi Web di uso comune. Per un elenco completo delle associazioni fornite dal sistema e le specifiche di servizi web che supportano vedere: [protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
  
## <a name="access-control-mechanisms"></a>Meccanismi del controllo di accesso  
 WCF fornisce numerosi modi per controllare l'accesso a un servizio o un'operazione, tra i quali:  
  
1.  <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2.  Provider di appartenenze ASP.NET  
  
3.  Provider di ruoli ASP.NET  
  
4.  Gestione autorizzazioni  
  
5.  Modello di identità  
  
 Per ulteriori informazioni, vedere questi argomenti [meccanismi del controllo di accesso](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Modello di sicurezza per Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
