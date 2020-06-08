---
title: Interfaccia ICLRMetaHost
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
ms.openlocfilehash: bb7c3659930f308328cba121c06a88cb6a95eb26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504160"
---
# <a name="iclrmetahost-interface"></a>Interfaccia ICLRMetaHost
Fornisce metodi che restituiscono una versione specifica del Common Language Runtime (CLR) in base al relativo numero di versione, elencare tutti CLR installati, elencare tutti i runtime caricati in un processo specifico, individuare la versione CLR utilizzata per compilare un assembly, uscire da un processo con un arresto del runtime pulito ed eseguire query sull'associazione API legacy.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateInstalledRuntimes](iclrmetahost-enumerateinstalledruntimes-method.md)|Restituisce un'enumerazione che contiene un puntatore a interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) valido per ogni versione CLR installata in un computer.|  
|[Metodo EnumerateLoadedRuntimes](iclrmetahost-enumerateloadedruntimes-method.md)|Restituisce un'enumerazione che contiene un puntatore a interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) valido per ogni CLR caricato in un determinato processo. Questo metodo sostituisce [GetVersionFromProcess](getversionfromprocess-function.md).|  
|[Metodo ExitProcess](iclrmetahost-exitprocess-method.md)|Tenta di arrestare correttamente tutti i runtime caricati, quindi termina il processo. Sostituisce la funzione [CorExitProcess](corexitprocess-function.md) .|  
|[Metodo GetRuntime](iclrmetahost-getruntime-method.md)|Ottiene l'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che corrisponde a una particolare versione di CLR. Questo metodo sostituisce la funzione [CorBindToRuntimeEx](corbindtoruntimeex-function.md) utilizzata con il flag [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .|  
|[Metodo GetVersionFromFile](iclrmetahost-getversionfromfile-method.md)|Ottiene la versione originale del .NET Framework di compilazione dell'assembly (archiviata nei metadati), dato il percorso del file. Questo metodo sostituisce [GetFileVersion](getfileversion-function.md).|  
|[Metodo QueryLegacyV2RuntimeBinding](iclrmetahost-querylegacyv2runtimebinding-method.md)|Restituisce un'interfaccia che rappresenta un runtime a cui sono stati associati i criteri di attivazione legacy, ad esempio usando l' `useLegacyV2RuntimeActivationPolicy` attributo nella voce del file di configurazione degli [ \<startup> elementi](../../configure-apps/file-schema/startup/startup-element.md) , usando direttamente le API di attivazione legacy oppure chiamando il metodo [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .|  
|[Metodo RequestRuntimeLoadedNotification](iclrmetahost-requestruntimeloadednotification-method.md)|Garantisce un callback al puntatore a funzione specificato quando una versione CLR viene caricata per la prima volta, ma non ancora avviata. Questo metodo sostituisce [LockClrVersion](lockclrversion-function.md)|  
  
## <a name="remarks"></a>Osservazioni  
 L'unico modo per ottenere un'istanza di questa interfaccia consiste nel chiamare la funzione [CLRCreateInstance](clrcreateinstance-function.md) come segue:  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
