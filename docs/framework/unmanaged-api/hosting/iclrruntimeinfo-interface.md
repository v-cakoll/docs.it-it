---
title: Interfaccia ICLRRuntimeInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo
helpviewer_keywords: ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 287e5ede-b3a7-4ef8-a756-4fca3f285a82
topic_type: apiref
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86861ae1742cf520d1a5251c70a112b090ec429e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfo-interface"></a>Interfaccia ICLRRuntimeInfo
Fornisce metodi che restituiscono informazioni su un determinato common language runtime (CLR), inclusi versione, directory e lo stato di caricamento. Questa interfaccia fornisce anche funzionalità specifiche di runtime senza l'inizializzazione di runtime. Include il relativo runtime [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) (metodo), il runtime specifiche [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) (metodo) e interfacce fornite dal runtime tramite il [GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)metodo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[BindAsLegacyV2Runtime (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Associa questo runtime per tutte le precedenti CLR versione 2 attivazione decisioni relative ai criteri.|  
|[GetDefaultStartupFlags (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getdefaultstartupflags-method.md)|Ottiene i flag di avvio CLR e i file di configurazione host.|  
|[GetInterface (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|Carica CLR nel processo corrente e restituisce runtime puntatori di interfaccia, ad esempio [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) e [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md). Questo metodo sostituisce tutte le `CorBindTo*` funzioni.|  
|[GetProcAddress (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|Ottiene l'indirizzo di una funzione specificata è stata esportata da CLR associato a questa interfaccia. Questo metodo sostituisce il [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) metodo.|  
|[GetRuntimeDirectory (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|Ottiene la directory di installazione di CLR associata a questa interfaccia. Questo metodo sostituisce il [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) metodo.|  
|[GetVersionString (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|Ottiene common language runtime (CLR) informazioni sulla versione associate a un determinato [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia. Questo metodo sostituisce il [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) e [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) metodi.|  
|[IsLoadable (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloadable-method.md)|Indica se il runtime associato a questa interfaccia può essere caricato nel processo corrente, prendendo in considerazione altri runtime che potrebbero essere già stato caricato nel processo.|  
|[IsLoaded (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|Indica se Common Language Runtime è associato il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia viene caricata in un processo.|  
|[IsStarted (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|Indica se Common Language Runtime che è associato il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia è stata avviata.|  
|[LoadErrorString (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate. Questo metodo sostituisce il [LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) e [LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md) metodi.|  
|[LoadLibrary (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|Carica una libreria dalla directory del framework di CLR rappresentato da un [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia. Questo metodo sostituisce il [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) metodo.|  
|[SetDefaultStartupFlags (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)|Imposta il flag di avvio CLR e l'host di file di configurazione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
