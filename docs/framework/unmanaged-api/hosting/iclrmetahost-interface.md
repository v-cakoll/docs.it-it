---
title: Interfaccia ICLRMetaHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost
helpviewer_keywords: ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type: apiref
caps.latest.revision: "28"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d271a69847e3bd4dc972ed8e697b8cd15f049fb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahost-interface"></a>Interfaccia ICLRMetaHost
Fornisce metodi che restituiscono una versione specifica di common language runtime (CLR) in base al relativo numero di versione, elencano tutti i runtime installati, tutti i runtime caricati in un determinato processo, individuano la versione CLR utilizzata per compilare un assembly, uscire da un processo con un arresto Pulisci runtime e l'associazione API legacy di query.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[EnumerateInstalledRuntimes (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|Restituisce un'enumerazione che contiene un valore valido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) puntatore a interfaccia per ogni versione CLR installata in un computer.|  
|[EnumerateLoadedRuntimes (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|Restituisce un'enumerazione che contiene un valore valido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) puntatore a interfaccia per ogni CLR che viene caricato in un processo specifico. Questo metodo sostituisce [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).|  
|[ExitProcess (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|Tenta di arrestare normalmente caricati tutti i Runtime e quindi termina il processo. Sostituisce il [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) (funzione).|  
|[GetRuntime (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|Ottiene il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia che corrisponde a una particolare versione CLR. Questo metodo sostituisce il [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funzione utilizzato con il [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.|  
|[GetVersionFromFile (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|Ottiene la versione dell'assembly originale .NET Framework compilazione (archiviata nei metadati), data il percorso del file. Questo metodo sostituisce [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).|  
|[QueryLegacyV2RuntimeBinding (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|Restituisce un'interfaccia che rappresenta un runtime a cui sono stati associati i criteri di attivazione legacy, ad esempio utilizzando il `useLegacyV2RuntimeActivationPolicy` attributo la [ \<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) voce file di configurazione mediante l'utilizzo diretto l'API di attivazione legacy o chiamando il [ICLRRuntimeInfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) metodo.|  
|[RequestRuntimeLoadedNotification (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|Garantisce un callback al puntatore a funzione specificato quando è caricata una versione di CLR, ma non ancora avviata. Questo metodo sostituisce [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)|  
  
## <a name="remarks"></a>Note  
 L'unico modo per ottenere un'istanza di questa interfaccia è tramite la chiamata di [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funzione come segue:  
  
```  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
