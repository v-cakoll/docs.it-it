---
title: Metodo ICLRRuntimeInfo::GetRuntimeDirectory
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
ms.openlocfilehash: d744abf5c502e9b9510cf9fd6479149b6c2177cc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762214"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a>Metodo ICLRRuntimeInfo::GetRuntimeDirectory
Ottiene la directory di installazione del Common Language Runtime (CLR) associato a questa interfaccia.  
  
 Questo metodo sostituisce la funzione [GetCORSystemDirectory](getcorsystemdirectory-function.md) fornita in .NET Framework versioni 2,0, 3,0 e 3,5.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzBuffer`  
 out Restituisce la directory di installazione CLR. Il percorso di installazione è completo. ad esempio, "c:\Windows\Microsoft.net\framework\v1.0.3705 \\ ".  
  
 `pchBuffer`  
 [in, out] Specifica la dimensione di `pwzBuffer` per evitare sovraccarichi del buffer. Se `pwzBuffer` è null, `pchBuffer` restituisce la dimensione richiesta di `pwzBuffer` .  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pwzBuffer` o `pchBuffer` è null.|  
  
## <a name="remarks"></a>Osservazioni  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Hosting](index.md)
