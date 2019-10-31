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
ms.openlocfilehash: 568c63681b84d0ab3642d84e4a6715ad230582db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120386"
---
# <a name="iclrruntimehost-interface"></a>Interfaccia ICLRRuntimeHost
Fornisce una funzionalità simile a quella dell'interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) fornita in .NET Framework versione 1, con le modifiche seguenti:  
  
- Aggiunta del metodo [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) per impostare l'interfaccia del controllo host.  
  
- Omissione di alcuni metodi forniti da `ICorRuntimeHost`.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|Utilizzato negli scenari di distribuzione ClickOnce basati su manifesto per specificare l'applicazione da attivare in un nuovo dominio.|  
|[Metodo ExecuteInAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Specifica il <xref:System.AppDomain> in cui eseguire il codice gestito specificato.|  
|[Metodo ExecuteInDefaultAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Richiama il metodo specificato del tipo specificato nell'assembly specificato.|  
|[Metodo GetCLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Ottiene un puntatore a interfaccia di tipo [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) che può essere utilizzato dagli host per personalizzare gli aspetti del Common Language Runtime (CLR).|  
|[Metodo GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Ottiene l'identificatore numerico del <xref:System.AppDomain> attualmente in esecuzione.|  
|[Metodo SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Imposta l'interfaccia del controllo host. Prima di chiamare `Start`, è necessario chiamare `SetHostControl`.|  
|[Metodo Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Inizializza il CLR in un processo.|  
|[Metodo Stop](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Arresta l'esecuzione del codice dal runtime.|  
|[Metodo UnloadAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Scarica l'<xref:System.AppDomain> corrispondente all'identificatore numerico specificato.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework 4, usare l'interfaccia [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) per ottenere un puntatore all'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) e quindi chiamare il metodo [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) per ottenere un puntatore a `ICLRRuntimeHost`. Nelle versioni precedenti del .NET Framework, l'host ottiene un puntatore a un'istanza di `ICLRRuntimeHost` chiamando [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Per fornire implementazioni di qualsiasi tecnologia fornita nella .NET Framework versione 2,0, è necessario utilizzare `ICLRRuntimeHost` invece di `ICorRuntimeHost`.  
  
> [!IMPORTANT]
> Non chiamare il metodo [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) prima di chiamare il metodo [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) per attivare un'applicazione basata su manifesto. Se il metodo `Start` viene chiamato per primo, la chiamata al metodo `ExecuteApplication` avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Coclasse CLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
