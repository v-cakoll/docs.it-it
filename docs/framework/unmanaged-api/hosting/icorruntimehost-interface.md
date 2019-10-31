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
ms.openlocfilehash: e66e1468a864ec85d88f759c481c7a9707d37f7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139539"
---
# <a name="icorruntimehost-interface"></a>Interfaccia ICorRuntimeHost
Fornisce metodi che consentono all'host di avviare e arrestare in modo esplicito il Common Language Runtime (CLR), per creare e configurare i domini applicazione, per accedere al dominio predefinito e per enumerare tutti i domini in esecuzione nel processo.  
  
 In .NET Framework versione 2,0 questa interfaccia viene sostituita da [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CloseEnum](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Reimposta un enumeratore di dominio all'inizio dell'elenco di domini.|  
|[Metodo CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Crea un dominio applicazione. Il chiamante riceve un puntatore di interfaccia di tipo <xref:System._AppDomain> a un'istanza di tipo <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[Metodo CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Crea un dominio applicazione. Questo metodo consente al chiamante di passare un'istanza di IAppDomainSetup per configurare funzionalità aggiuntive dell'istanza di <xref:System._AppDomain> restituita.|  
|[Metodo CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Ottiene un puntatore a interfaccia di tipo `IAppDomainSetup` a un'istanza di <xref:System.AppDomainSetup>. `IAppDomainSetup` fornisce i metodi per configurare gli aspetti di un dominio applicazione prima che venga creato.|  
|[Metodo CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Ottiene un puntatore a interfaccia di tipo <xref:System.Security.Principal.IIdentity>, che consente all'host di creare evidenze di sicurezza da passare a [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) o [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).|  
|[Metodo CreateLogicalThreadState](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|Non usare.|  
|[Metodo CurrentDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain> che rappresenta il dominio caricato sul thread corrente.|  
|[Metodo DeleteLogicalThreadState](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|Non usare.|  
|[Metodo EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Ottiene un enumeratore per i domini nel processo corrente.|  
|[Metodo GetConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|Ottiene un oggetto che consente all'host di specificare la configurazione di callback di CLR.|  
|[Metodo GetDefaultDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain> che rappresenta il dominio predefinito per il processo corrente.|  
|[Metodo LocksHeldByLogicalThread](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|Non usare.|  
|[Metodo MapFile](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Esegue il mapping del file specificato in memoria. Questo metodo è obsoleto.|  
|[Metodo NextDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Ottiene un puntatore a interfaccia al dominio successivo nell'enumerazione.|  
|[Metodo Start](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|Avvia CLR.|  
|[Metodo Stop](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Arresta l'esecuzione del codice nel runtime per il processo corrente.|  
|[Metodo SwitchInLogicalThreadState](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|Non usare.|  
|[Metodo SwitchOutLogicalThreadState](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|Non usare.|  
|[Metodo UnloadDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Scarica il dominio applicazione specificato dal processo corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomain>
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Interfaccia ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [Host di runtime](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Coclasse CorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
