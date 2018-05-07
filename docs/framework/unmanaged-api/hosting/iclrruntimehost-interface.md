---
title: Interfaccia ICLRRuntimeHost
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95dd084520d1e93803a91f0c4d01214ed0d3744d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrruntimehost-interface"></a>Interfaccia ICLRRuntimeHost
Fornisce una funzionalità simile a quello del [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interfaccia fornita in .NET Framework versione 1, con le modifiche seguenti:  
  
-   L'aggiunta del [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) per impostare l'interfaccia del controllo host.  
  
-   L'omissione di alcuni metodi forniti da `ICorRuntimeHost`.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|Utilizzato in scenari di distribuzione basato su manifesto ClickOnce per specificare l'attivazione in un nuovo dominio dell'applicazione.|  
|[Metodo ExecuteInAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Specifica il <xref:System.AppDomain> in cui eseguire il codice gestito specificato.|  
|[Metodo ExecuteInDefaultAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Richiama il metodo specificato nel tipo specificato nell'assembly specificato.|  
|[Metodo GetCLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Ottiene un puntatore a interfaccia di tipo [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) che gli host possono usare per personalizzare gli aspetti di common language runtime (CLR).|  
|[Metodo GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Ottiene l'identificatore numerico del <xref:System.AppDomain> che è attualmente in esecuzione.|  
|[Metodo SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Imposta l'interfaccia del controllo host. È necessario chiamare `SetHostControl` prima di chiamare `Start`.|  
|[Metodo Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Inizializza il CLR in un processo.|  
|[Metodo Stop](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Arresta l'esecuzione di codice dal runtime.|  
|[Metodo UnloadAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Consente di scaricare il <xref:System.AppDomain> che corrisponde all'identificatore numerico specificato.|  
  
## <a name="remarks"></a>Note  
 A partire dal [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], utilizzare il [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interfaccia da ottenere un puntatore al [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia e quindi chiamare il [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) metodo per ottenere un puntatore a `ICLRRuntimeHost`. Nelle versioni precedenti di .NET Framework, l'host ottiene un puntatore a un `ICLRRuntimeHost` istanza chiamando [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Per fornire l'implementazione delle tecnologie fornite con .NET Framework versione 2.0, è necessario utilizzare `ICLRRuntimeHost` anziché `ICorRuntimeHost`.  
  
> [!IMPORTANT]
>  Non chiamare il [avviare](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo prima di chiamare il [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) metodo per attivare un'applicazione basata su manifesto. Se il `Start` metodo viene chiamato per primo, il `ExecuteApplication` chiamata al metodo avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Coclasse CLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
