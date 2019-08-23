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
ms.openlocfilehash: 0f159c0b57f2087b608fac8cbc9b9c64ceb063a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965998"
---
# <a name="iclrruntimehost-interface"></a>Interfaccia ICLRRuntimeHost
Fornisce una funzionalità simile a quella dell'interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) fornita in .NET Framework versione 1, con le modifiche seguenti:  
  
- Aggiunta del metodo [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) per impostare l'interfaccia del controllo host.  
  
- Omissione di alcuni metodi forniti da `ICorRuntimeHost`.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|Utilizzato negli scenari di distribuzione ClickOnce basati su manifesto per specificare l'applicazione da attivare in un nuovo dominio.|  
|[Metodo ExecuteInAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Specifica l' <xref:System.AppDomain> oggetto in cui eseguire il codice gestito specificato.|  
|[Metodo ExecuteInDefaultAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Richiama il metodo specificato del tipo specificato nell'assembly specificato.|  
|[Metodo GetCLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Ottiene un puntatore a interfaccia di tipo [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) che può essere utilizzato dagli host per personalizzare gli aspetti del Common Language Runtime (CLR).|  
|[Metodo GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Ottiene l'identificatore numerico dell'oggetto <xref:System.AppDomain> attualmente in esecuzione.|  
|[Metodo SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Imposta l'interfaccia del controllo host. È necessario chiamare `SetHostControl` prima di `Start`chiamare.|  
|[Metodo Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Inizializza il CLR in un processo.|  
|[Metodo Stop](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Arresta l'esecuzione del codice dal runtime.|  
|[Metodo UnloadAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Scarica l'oggetto <xref:System.AppDomain> che corrisponde all'identificatore numerico specificato.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework 4, usare l'interfaccia [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) per ottenere un puntatore all'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) e quindi chiamare il metodo [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) per ottenere un puntatore a. `ICLRRuntimeHost` Nelle versioni precedenti del .NET Framework, l'host ottiene un puntatore a un' `ICLRRuntimeHost` istanza chiamando [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Per fornire implementazioni di qualsiasi tecnologia fornita nella .NET Framework versione 2,0, è necessario usare `ICLRRuntimeHost` `ICorRuntimeHost`anziché.  
  
> [!IMPORTANT]
> Non chiamare il metodo [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) prima di chiamare il metodo [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) per attivare un'applicazione basata su manifesto. Se il `Start` metodo viene chiamato per primo, `ExecuteApplication` la chiamata al metodo avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Coclasse CLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
