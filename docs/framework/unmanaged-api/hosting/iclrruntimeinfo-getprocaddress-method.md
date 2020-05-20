---
title: Metodo ICLRRuntimeInfo::GetProcAddress
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: 2690a5c2e7c499d68ef9e903c62bff8f85e72e8e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703871"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a>Metodo ICLRRuntimeInfo::GetProcAddress
Ottiene l'indirizzo di una funzione specificata esportata dalla Common Language Runtime (CLR) associata a questa interfaccia.  
  
 Questo metodo sostituisce la funzione [GetRealProcAddress](getrealprocaddress-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a>Parametri  
 `pszProcName`  
 in Nome della funzione esportata.  
  
 `ppProc`  
 out Indirizzo della funzione esportata.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pszProcName` o `ppProc` è null.|  
|CLR_E_SHIM_RUNTIMEEXPORT|La funzione specificata non è una funzione esportata.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo fa sì che CLR venga caricato ma non inizializzato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
