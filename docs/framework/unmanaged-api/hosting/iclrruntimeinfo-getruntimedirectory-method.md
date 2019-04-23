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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c09f57ad805b4ba17b4bdafd3ced533199277a0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196684"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a>Metodo ICLRRuntimeInfo::GetRuntimeDirectory
Ottiene la directory di installazione di common language runtime (CLR) associato a questa interfaccia.  
  
 Questo metodo sostituisce le [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) funzione fornita nelle versioni di .NET Framework 2.0, 3.0 e 3.5.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzBuffer`  
 [out] Restituisce la directory di installazione di CLR. Il percorso di installazione è completo. ad esempio, "c:\windows\microsoft.net\framework\v1.0.3705\\".  
  
 `pchBuffer`  
 [in, out] Specifica la dimensione del `pwzBuffer` per evitare i sovraccarichi del buffer. Se `pwzBuffer` è null, `pchBuffer` restituisce la dimensione necessaria della `pwzBuffer`.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pwzBuffer` o `pchBuffer` è null.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
