---
title: Interfaccia ICLRRuntimeInfo
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo
helpviewer_keywords:
- ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 287e5ede-b3a7-4ef8-a756-4fca3f285a82
topic_type:
- apiref
ms.openlocfilehash: cafb85ed5f6a1245dd520ab3a5e94f95c8d37608
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762552"
---
# <a name="iclrruntimeinfo-interface"></a>Interfaccia ICLRRuntimeInfo
Fornisce metodi che restituiscono informazioni su una specifica Common Language Runtime (CLR), inclusi la versione, la directory e lo stato di caricamento. Questa interfaccia fornisce anche funzionalità specifiche del runtime senza inizializzare il Runtime. Include il metodo [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) relativo al runtime, il metodo [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) specifico del modulo di runtime e le interfacce fornite dal runtime tramite il metodo [GetInterface](iclrruntimeinfo-getinterface-method.md) .  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Associa questo runtime per tutte le decisioni legacy relative ai criteri di attivazione di CLR versione 2.|  
|[Metodo GetDefaultStartupFlags](iclrruntimeinfo-getdefaultstartupflags-method.md)|Ottiene i flag di avvio e il file di configurazione dell'host CLR.|  
|[Metodo GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|Carica CLR nel processo corrente e restituisce i puntatori dell'interfaccia di runtime, ad esempio [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) e [IMetaDataDispenser](../metadata/imetadatadispenser-interface.md). Questo metodo sostituisce tutte le `CorBindTo*` funzioni.|  
|[Metodo GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|Ottiene l'indirizzo di una funzione specificata esportata da CLR associato a questa interfaccia. Questo metodo sostituisce il metodo [GetRealProcAddress](getrealprocaddress-function.md) .|  
|[Metodo GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|Ottiene la directory di installazione del CLR associato a questa interfaccia. Questo metodo sostituisce il metodo [GetCORSystemDirectory](getcorsystemdirectory-function.md) .|  
|[Metodo GetVersionString](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|Ottiene le informazioni sulla versione di Common Language Runtime (CLR) associate a un'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) specificata. Questo metodo sostituisce i metodi [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) e [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) .|  
|[Metodo IsLoadable](iclrruntimeinfo-isloadable-method.md)|Indica se il runtime associato a questa interfaccia può essere caricato nel processo corrente, tenendo conto di altri runtime che potrebbero essere già stati caricati nel processo.|  
|[Metodo IsLoaded](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|Indica se il CLR associato all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) viene caricato in un processo.|  
|[Metodo IsStarted](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|Indica se il CLR associato all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) è stato avviato.|  
|[Metodo LoadErrorString](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate. Questo metodo sostituisce i metodi [LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) e [LoadStringRCEx](loadstringrcex-function.md) .|  
|[Metodo LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|Carica una libreria dalla directory del Framework di CLR rappresentata da un'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) . Questo metodo sostituisce il metodo [LoadLibraryShim](loadlibraryshim-function.md) .|  
|[Metodo SetDefaultStartupFlags](iclrruntimeinfo-setdefaultstartupflags-method.md)|Imposta i flag di avvio e il file di configurazione dell'host CLR.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
