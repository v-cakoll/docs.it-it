---
title: Metodo ICLRMetaHost::GetRuntime
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
ms.openlocfilehash: d482e25c7bf0f028e2478c8e7b7863bc54d7aeb9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504193"
---
# <a name="iclrmetahostgetruntime-method"></a>Metodo ICLRMetaHost::GetRuntime
Ottiene l'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che corrisponde a una particolare versione di Common Language Runtime (CLR). Questo metodo sostituisce la funzione [CorBindToRuntimeEx](corbindtoruntimeex-function.md) utilizzata con il flag [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzVersion`  
 in La versione di compilazione .NET Framework archiviata nei metadati, nel formato "v*a*. *B*[.* X*] ". *A*, *B*e *X* sono numeri decimali che corrispondono alla versione principale, alla versione secondaria e al numero di Build.  
  
> [!NOTE]
> Questo parametro deve corrispondere al nome della directory per la versione .NET Framework, come appare in C:\Windows\Microsoft.NET\Framework o C:\Windows\Microsoft.NET\Framework64.  
  
 I valori di esempio sono "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" e "v 4.0. *X*", dove *x* dipende dal numero di build installato. Il prefisso "v" è obbligatorio.  
  
 `riid`  
 in Identificatore dell'interfaccia desiderata. Attualmente, l'unico valore valido per questo parametro è IID_ICLRRuntimeInfo.  
  
 `ppRuntime`  
 out Puntatore all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che corrisponde al runtime richiesto.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pwzVersion` o `ppRuntime` è null.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo interagisce costantemente con le interfacce legacy, ad esempio l'interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) e le funzioni legacy, ad esempio le funzioni deprecate `CorBindTo*` (vedere [funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md) nell'API di hosting .NET Framework 2,0). Ovvero, i runtime caricati con l'API legacy sono visibili alla nuova API e i runtime caricati con la nuova API sono visibili all'API legacy.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMetaHost](iclrmetahost-interface.md)
- [Interfacce di hosting CLR deprecate e coclassi](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [Interfacce di hosting CLR](clr-hosting-interfaces.md)
- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
- [Hosting](index.md)
