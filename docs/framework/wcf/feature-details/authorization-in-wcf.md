---
title: Autorizzazione in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 8c605b310f19a05f994296d8f4268b91b408fb18
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881199"
---
# <a name="authorization-in-wcf"></a>Autorizzazione in WCF
L'autorizzazione è il processo di controllo dell'accesso e dei diritti alle risorse, ad esempio servizi o file. Gli argomenti in questa sezione illustrano come eseguire questa attività di base in Windows Communication Foundation (WCF) in diversi modi.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Meccanismi del controllo di accesso](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 Fornisce una breve descrizione dei meccanismi di autorizzazione in WCF e Usa suggerita.  
  
 [Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Viene illustrato il processo di restrizione dell'accesso a un servizio con l'attributo <xref:System.Security.Permissions.PrincipalPermissionAttribute>.  
  
 [Procedura: Usare il Provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Illustra in dettaglio la configurazione di un servizio per poter usare la funzionalità di provider di ruoli di ASP.NET.  
  
 [Procedura: Usare il Provider di ruoli ASP.NET di gestione autorizzazioni con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 ASP.NET è possibile utilizzare il gestore dell'autorizzazione per gestire le autorizzazioni per un sito Web. WCF allo stesso modo possibile sfruttare la combinazione di ASP.NET/Authorization Manager per l'autorizzazione dei client.  
  
 [Gestione delle attestazioni e dell'autorizzazione con il modello di identità](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 Vengono spiegate le nozioni di base dell'utilizzo dell'infrastruttura del modello di identità per l'autorizzazione basata su richieste.  
  
 [Delega e rappresentazione](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 Viene spiegata la differenza tra delega e rappresentazione.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Autenticazione](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Modello di sicurezza per Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
