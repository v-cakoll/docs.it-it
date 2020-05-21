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
ms.openlocfilehash: ac4787379436faa568727329e7b012f83d0a53d5
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760732"
---
# <a name="icorruntimehost-interface"></a>Interfaccia ICorRuntimeHost
Fornisce metodi che consentono all'host di avviare e arrestare in modo esplicito il Common Language Runtime (CLR), per creare e configurare i domini applicazione, per accedere al dominio predefinito e per enumerare tutti i domini in esecuzione nel processo.  
  
 In .NET Framework versione 2,0 questa interfaccia viene sostituita da [ICLRRuntimeHost](iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CloseEnum](icorruntimehost-closeenum-method.md)|Reimposta un enumeratore di dominio all'inizio dell'elenco di domini.|  
|[Metodo CreateDomain](icorruntimehost-createdomain-method.md)|Crea un dominio applicazione. Il chiamante riceve un puntatore di interfaccia di tipo <xref:System._AppDomain> a un'istanza di tipo <xref:System.AppDomain?displayProperty=nameWithType> .|  
|[Metodo CreateDomainEx](icorruntimehost-createdomainex-method.md)|Crea un dominio applicazione. Questo metodo consente al chiamante di passare un'istanza di IAppDomainSetup per configurare funzionalità aggiuntive dell'istanza restituita <xref:System._AppDomain> .|  
|[Metodo CreateDomainSetup](icorruntimehost-createdomainsetup-method.md)|Ottiene un puntatore a interfaccia di tipo `IAppDomainSetup` a un' <xref:System.AppDomainSetup> istanza di. `IAppDomainSetup`fornisce metodi per configurare gli aspetti di un dominio applicazione prima che venga creato.|  
|[Metodo CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Ottiene un puntatore a interfaccia di tipo <xref:System.Security.Principal.IIdentity> , che consente all'host di creare evidenze di sicurezza da passare a [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) o [CreateDomainEx](icorruntimehost-createdomainex-method.md).|  
|[Metodo CreateLogicalThreadState](icorruntimehost-createlogicalthreadstate-method.md)|Non usare.|  
|[Metodo CurrentDomain](icorruntimehost-currentdomain-method.md)|Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain> che rappresenta il dominio caricato sul thread corrente.|  
|[Metodo DeleteLogicalThreadState](icorruntimehost-deletelogicalthreadstate-method.md)|Non usare.|  
|[Metodo EnumDomains](icorruntimehost-enumdomains-method.md)|Ottiene un enumeratore per i domini nel processo corrente.|  
|[Metodo GetConfiguration](icorruntimehost-getconfiguration-method.md)|Ottiene un oggetto che consente all'host di specificare la configurazione di callback di CLR.|  
|[Metodo GetDefaultDomain](icorruntimehost-getdefaultdomain-method.md)|Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain> che rappresenta il dominio predefinito per il processo corrente.|  
|[Metodo LocksHeldByLogicalThread](icorruntimehost-locksheldbylogicalthread-method.md)|Non usare.|  
|[Metodo MapFile](icorruntimehost-mapfile-method.md)|Esegue il mapping del file specificato in memoria. Questo metodo è obsoleto.|  
|[Metodo NextDomain](icorruntimehost-nextdomain-method.md)|Ottiene un puntatore a interfaccia al dominio successivo nell'enumerazione.|  
|[Metodo Start](icorruntimehost-start-method.md)|Avvia CLR.|  
|[Metodo Stop](icorruntimehost-stop-method.md)|Arresta l'esecuzione del codice nel runtime per il processo corrente.|  
|[Metodo SwitchInLogicalThreadState](icorruntimehost-switchinlogicalthreadstate-method.md)|Non usare.|  
|[Metodo SwitchOutLogicalThreadState](icorruntimehost-switchoutlogicalthreadstate-method.md)|Non usare.|  
|[Metodo UnloadDomain](icorruntimehost-unloaddomain-method.md)|Scarica il dominio applicazione specificato dal processo corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomain>
- [Hosting](index.md)
- [Interfaccia ICLRRuntimeHost](iclrruntimehost-interface.md)
- [Host di runtime](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))
- [Interfacce di hosting](hosting-interfaces.md)
- [Coclasse CorRuntimeHost](corruntimehost-coclass.md)
