---
title: Metodo ICLRRuntimeInfo::IsLoaded
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: 45e27ac3c2d4912d2ed3e5d43ea3020b9db5dbdc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504030"
---
# <a name="iclrruntimeinfoisloaded-method"></a>Metodo ICLRRuntimeInfo::IsLoaded
Indica se il Common Language Runtime (CLR) associato all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) viene caricato in un processo. È possibile caricare un runtime anche senza avviare.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a>Parametri  
 `hndProcess`  
 in Handle per il processo.  
  
 `pbLoaded`  
 [out] `true` Se CLR viene caricato nel processo; in caso contrario, `false` .  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pbLoaded` è null.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo è compatibile con le versioni precedenti con le funzioni e le interfacce seguenti:  
  
- Interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) (nell'API di hosting .NET Framework versione 1).  
  
- Interfaccia [ICLRRuntimeHost](iclrruntimehost-interface.md) (nell'API di hosting .NET Framework 2,0).  
  
- Funzioni deprecate `CorBindTo*` (vedere [funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md) nell'API di hosting .NET Framework 2,0).  
  
 Un host può chiamare una delle funzioni deprecate `CorBindTo*` , ad esempio la funzione [CorBindToRuntime](corbindtoruntime-function.md) , per creare un'istanza di una specifica versione di CLR. L'host può quindi chiamare il metodo [ICLRMetaHost:: GetRuntime](iclrmetahost-getruntime-method.md) e specificare lo stesso numero di versione per ottenere un'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .  
  
 Se l'host chiama quindi il `IsLoaded` metodo sull'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) restituita, `pbLoaded` restituisce `true` ; in caso contrario, restituisce `false` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
