---
title: Concetti relativi alla sicurezza usati in WCF
ms.date: 03/30/2017
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
ms.openlocfilehash: f852ba4e1100103289bc5fd879b19ebd40443b8d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595180"
---
# <a name="security-concepts-used-in-wcf"></a>Concetti relativi alla sicurezza usati in WCF
La sicurezza Windows Communication Foundation (WCF) si basa su concetti già in uso e distribuiti in diverse infrastrutture di sicurezza.  
  
 WCF supporta alcune di queste infrastrutture, ad esempio Secure Sockets Layer (SSL) su HTTP (HTTPS). Tuttavia, WCF va oltre il supporto di infrastrutture di sicurezza esistenti implementando gli standard di sicurezza interoperativi più recenti, ad esempio WS-Security, su messaggi con codifica SOAP. Tanto per l'utilizzo di meccanismi esistenti che di standard interoperativi nuovi, i concetti di sicurezza alla base di entrambi sono gli stessi. La comprensione di concetti sottostanti le infrastrutture esistenti e gli standard più recenti è fondamentale per l'implementazione del modello di sicurezza migliore per un'applicazione.  
  
## <a name="introduction-to-security-for-wcf-web-services"></a>Introduzione alla sicurezza per i servizi Web WCF  

Il gruppo Microsoft Patterns and Practices ha scritto una white paper approfondita denominata [Guida alla sicurezza di WCF](https://archive.codeplex.com/?p=wcfsecurityguide). In questo white paper vengono descritti i concetti fondamentali sulla sicurezza in relazione ai servizi Web, ai concetti chiave relativi alla sicurezza WCF, agli scenari di applicazioni Intranet e agli scenari di applicazioni Internet.  
  
## <a name="industry-wide-security-specifications"></a>Specifiche di sicurezza del settore  
  
### <a name="public-key-infrastructure"></a>Infrastruttura a chiave pubblica (PKI)  

L'infrastruttura a chiave pubblica (PKI) è un sistema di certificati digitali, autorità di certificazione e altre autorità di registrazione che verificano e autenticano ogni parte che partecipa a una transazione elettronica tramite l'uso della crittografia a chiave pubblica.
  
### <a name="kerberos-protocol"></a>Protocollo Kerberos  
 Il *protocollo Kerberos* è una specifica per la creazione di un meccanismo di sicurezza che autentica gli utenti in un dominio Windows. Consente a un utente di stabilire un contesto protetto con altre entità in un dominio. Windows 2000 e le piattaforme successive utilizzano il protocollo Kerberos per impostazione predefinita. La comprensione dei meccanismi del sistema è utile in caso di creazione di un servizio che dovrà interagire con i client Intranet. Inoltre, poiché il *Web Services Security associazione Kerberos* è ampiamente pubblicato, è possibile utilizzare il protocollo Kerberos per comunicare con i client Internet (ovvero, il protocollo Kerberos è interoperativo). Per ulteriori informazioni sulla modalità di implementazione del protocollo Kerberos in Windows, vedere [Microsoft Kerberos](/windows/win32/secauthn/microsoft-kerberos).  
  
### <a name="x509-certificates"></a>Certificati X.509  
 I certificati X.509 costituiscono un form di credenziali primario utilizzato nelle applicazioni di sicurezza. Per ulteriori informazioni sui certificati X. 509, vedere [certificati di chiave pubblica x. 509](/windows/win32/seccertenroll/about-x-509-public-key-certificates). I certificati X.509 vengono archiviati all'interno di un archivio certificati. I computer che eseguono Windows dispongono di vari tipi di archivi certificati, ognuno dei quali con un scopo diverso. Per ulteriori informazioni sui diversi archivi, vedere [archivi certificati](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc757138(v=ws.10)).  
  
## <a name="web-services-security-specifications"></a>Specifiche di sicurezza dei servizi Web  
 Le associazioni definite dal sistema supportano molte specifiche di sicurezza di servizi Web di uso comune. Per un elenco completo delle associazioni fornite dal sistema e delle specifiche dei servizi Web supportate, vedere: [protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
  
## <a name="access-control-mechanisms"></a>Meccanismi del controllo di accesso  
 WCF fornisce numerosi modi per controllare l'accesso a un servizio o un'operazione, tra i quali:  
  
1. <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2. Provider di appartenenze ASP.NET  
  
3. Provider di ruoli ASP.NET  
  
4. Gestione autorizzazioni  
  
5. Modello di identità  
  
 Per ulteriori informazioni su questi argomenti, vedere [meccanismi di controllo degli accessi](access-control-mechanisms.md)  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](security-overview.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
