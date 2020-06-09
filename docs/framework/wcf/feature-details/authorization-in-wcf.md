---
title: Autorizzazione in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: d67d64dcf0003de28775ac947f8b5f72d7c2ba2a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597631"
---
# <a name="authorization-in-wcf"></a>Autorizzazione in WCF
L'autorizzazione è il processo di controllo dell'accesso e dei diritti alle risorse, ad esempio servizi o file. Negli argomenti di questa sezione viene illustrato come eseguire questa attività di base in Windows Communication Foundation (WCF) in diversi modi.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Meccanismi del controllo di accesso](access-control-mechanisms.md)  
 Viene fornita una breve descrizione dei meccanismi di autorizzazione in WCF e degli utilizzi consigliati.  
  
 [Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Viene illustrato il processo di restrizione dell'accesso a un servizio con l'attributo <xref:System.Security.Permissions.PrincipalPermissionAttribute>.  
  
 [Procedura: usare il provider di ruoli ASP.NET con un servizio](how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Viene illustrata la configurazione di un servizio per consentire l'uso della funzionalità del provider di ruoli di ASP.NET.  
  
 [Procedura: usare il provider di ruoli ASP.NET di Gestione autorizzazioni con un servizio](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 ASP.NET può utilizzare Gestione autorizzazioni per gestire l'autorizzazione per un sito Web. WCF può sfruttare in modo analogo la combinazione di ASP.NET/Authorization Manager per l'autorizzazione dei client.  
  
 [Gestione di attestazioni e autorizzazioni con il modello di identità](managing-claims-and-authorization-with-the-identity-model.md)  
 Vengono spiegate le nozioni di base dell'utilizzo dell'infrastruttura del modello di identità per l'autorizzazione basata su richieste.  
  
 [Delega e rappresentazione](delegation-and-impersonation-with-wcf.md)  
 Viene spiegata la differenza tra delega e rappresentazione.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [autenticazione](authentication-in-wcf.md)  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](security-overview.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
