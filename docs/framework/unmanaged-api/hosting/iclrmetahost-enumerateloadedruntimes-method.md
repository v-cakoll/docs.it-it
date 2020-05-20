---
title: Metodo ICLRMetaHost::EnumerateLoadedRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: 2e22b8a2d0213b3bd766d80218d6f396721a90e1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703762"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a>Metodo ICLRMetaHost::EnumerateLoadedRuntimes
Restituisce un'enumerazione che include un puntatore all'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) valido per ogni versione di Common Language Runtime (CLR) caricata in un determinato processo. Questo metodo sostituisce la funzione [GetVersionFromProcess](getversionfromprocess-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hndProcess`  
 in Handle del processo da controllare per i runtime caricati.  
  
 `ppEnumerator`  
 out <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>Enumerazione delle interfacce [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che corrispondono a ogni CLR caricato dal processo.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`ppEnumerator` è null.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo elenca tutti i runtime caricati, anche se sono stati caricati con funzioni deprecate, ad esempio [CorBindToRuntime](corbindtoruntime-function.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMetaHost](iclrmetahost-interface.md)
- [Hosting](index.md)
