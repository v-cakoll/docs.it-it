---
title: Autorizzazione in WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0c2afafa1d645ec0e95b7b41ff8389873969c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="authorization-in-wcf"></a>Autorizzazione in WCF
L'autorizzazione è il processo di controllo dell'accesso e dei diritti alle risorse, ad esempio servizi o file. Negli argomenti di questa sezione viene illustrato come eseguire questa attività di base in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in una serie di modi.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Meccanismi di controllo di accesso](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 Viene fornita una breve descrizione dei meccanismi di autorizzazione in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e degli utilizzi consigliati.  
  
 [Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Viene illustrato il processo di restrizione dell'accesso a un servizio con l'attributo <xref:System.Security.Permissions.PrincipalPermissionAttribute>.  
  
 [Procedura: utilizzare il Provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Viene illustrata la configurazione di un servizio per attivare l'utilizzo della funzionalità del provider di ruoli di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
 [Procedura: utilizzare il Provider di ruoli ASP.NET di gestione autorizzazioni con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 In [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] è possibile utilizzare Gestione autorizzazioni per gestire l'autorizzazione di un sito Web. In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è allo stesso modo possibile sfruttare la combinazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Gestione autorizzazioni per l'autorizzazione di client.  
  
 [Gestione attestazioni e autorizzazioni con il modello di identità](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 Vengono spiegate le nozioni di base dell'utilizzo dell'infrastruttura del modello di identità per l'autorizzazione basata su richieste.  
  
 [Delega e rappresentazione](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 Viene spiegata la differenza tra delega e rappresentazione.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Autenticazione](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Modello di sicurezza per Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
