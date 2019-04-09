---
title: Interfaccia ICorRuntimeHost
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec893c898a6cd4abffd525056ed0d0169fcbb288
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184782"
---
# <a name="icorruntimehost-interface"></a>Interfaccia ICorRuntimeHost
Fornisce metodi che consentono all'host avviare e arrestare in modo esplicito, common language runtime (CLR) per creare e configurare domini dell'applicazione, accedere al dominio predefinito di enumerare tutti i domini in esecuzione nel processo.  
  
 In .NET Framework versione 2.0, questa interfaccia è stata sostituita da [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CloseEnum](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Reimposta un enumeratore di dominio fino all'inizio dell'elenco dei domini.|  
|[Metodo CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Crea un dominio dell'applicazione. Il chiamante riceve un puntatore a interfaccia typu <xref:System._AppDomain> a un'istanza del tipo <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[Metodo CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Crea un dominio dell'applicazione. Questo metodo consente al chiamante di passare un'istanza IAppDomainSetup per configurare le funzionalità aggiuntive del valore restituito <xref:System._AppDomain> istanza.|  
|[Metodo CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Ottiene un puntatore a interfaccia typu `IAppDomainSetup` a un <xref:System.AppDomainSetup> istanza. `IAppDomainSetup` fornisce metodi per configurare gli aspetti di un dominio dell'applicazione prima che venga creato.|  
|[Metodo CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Ottiene un puntatore a interfaccia typu <xref:System.Security.Principal.IIdentity>, che consente all'host creare l'evidenza di sicurezza da passare al [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) oppure [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).|  
|[Metodo CreateLogicalThreadState](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|Non usare.|  
|[Metodo CurrentDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Ottiene un puntatore di interfaccia di tipo <xref:System._AppDomain> che rappresenta il dominio caricato sul thread corrente.|  
|[Metodo DeleteLogicalThreadState](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|Non usare.|  
|[Metodo EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Ottiene un enumeratore per i domini nel processo corrente.|  
|[Metodo GetConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|Ottiene un oggetto che consente all'host specificare la configurazione di callback di CLR.|  
|[Metodo GetDefaultDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Ottiene un puntatore di interfaccia di tipo <xref:System._AppDomain> che rappresenta il dominio predefinito per il processo corrente.|  
|[Metodo LocksHeldByLogicalThread](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|Non usare.|  
|[Metodo MapFile](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Il file specificato viene eseguito il mapping in memoria. Questo metodo è obsoleto.|  
|[Metodo NextDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Ottiene un puntatore di interfaccia al dominio successivo nell'enumerazione.|  
|[Metodo Start](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|Avvia il CLR.|  
|[Metodo Stop](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Arresta l'esecuzione di codice in fase di esecuzione per il processo corrente.|  
|[Metodo SwitchInLogicalThreadState](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|Non usare.|  
|[Metodo SwitchOutLogicalThreadState](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|Non usare.|  
|[Metodo UnloadDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Scarica il dominio applicazione specificato dal processo corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomain>
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Interfaccia ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [Host di runtime](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Coclasse CorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
