---
title: Interfaccia ICorRuntimeHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost
helpviewer_keywords: ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 844648cd2cfafc561e27bea870703ee3a55fb404
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehost-interface"></a>Interfaccia ICorRuntimeHost
Fornisce metodi che consentono all'host avviare e arrestare in modo esplicito, common language runtime (CLR) per creare e configurare i domini applicazione, per accedere al dominio predefinito e per enumerare tutti i domini in esecuzione nel processo.  
  
 In .NET Framework versione 2.0, questa interfaccia è stata sostituita da [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CloseEnum (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Reimposta un enumeratore di dominio fino all'inizio dell'elenco di domini.|  
|[CreateDomain (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Crea un dominio applicazione. Il chiamante riceve un puntatore a interfaccia di tipo <xref:System._AppDomain> a un'istanza di tipo <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[CreateDomainEx (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Crea un dominio applicazione. Questo metodo consente al chiamante di passare un'istanza di IAppDomainSetup per configurare le funzionalità aggiuntive dell'oggetto restituito <xref:System._AppDomain> istanza.|  
|[CreateDomainSetup (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Ottiene un puntatore a interfaccia di tipo `IAppDomainSetup` per un <xref:System.AppDomainSetup> istanza. `IAppDomainSetup`fornisce metodi per configurare gli aspetti di un dominio applicazione prima che venga creato.|  
|[CreateEvidence (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Ottiene un puntatore a interfaccia di tipo <xref:System.Security.Principal.IIdentity>, che consente all'host creare l'evidenza di sicurezza da passare al [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) o [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).|  
|[CreateLogicalThreadState (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|Non usare.|  
|[CurrentDomain (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain> che rappresenta il dominio caricato sul thread corrente.|  
|[DeleteLogicalThreadState (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|Non usare.|  
|[EnumDomains (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Ottiene un enumeratore per i domini nel processo corrente.|  
|[GetConfiguration (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|Ottiene un oggetto che consente all'host specificare la configurazione di callback di CLR.|  
|[GetDefaultDomain (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain> che rappresenta il dominio predefinito per il processo corrente.|  
|[LocksHeldByLogicalThread (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|Non usare.|  
|[MapFile (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Il file specificato viene eseguito il mapping in memoria. Questo metodo è obsoleto.|  
|[NextDomain (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Ottiene un puntatore a interfaccia per il dominio successivo nell'enumerazione.|  
|[Start (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|Avvia il CLR.|  
|[Stop (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Arresta l'esecuzione di codice in fase di esecuzione per il processo corrente.|  
|[SwitchInLogicalThreadState (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|Non usare.|  
|[SwitchOutLogicalThreadState (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|Non usare.|  
|[UnloadDomain (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Scarica il dominio di applicazione specificata dal processo corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.AppDomain>  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRRuntimeHost (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [Host di runtime](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Coclasse CorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
