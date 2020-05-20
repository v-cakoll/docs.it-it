---
title: Metodo ICLRMetaHost::EnumerateInstalledRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
ms.openlocfilehash: c99607bfe5fda01eb1abfd7771cb3907ddabeec5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703782"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a>Metodo ICLRMetaHost::EnumerateInstalledRuntimes
Restituisce un'enumerazione che contiene un'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) valida per ogni versione di Common Language Runtime (CLR) installata in un computer.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppEnumerator`  
 out Enumerazione delle interfacce [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che corrispondono a ogni versione di CLR installata nel computer.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`ppEnumerator` è null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMetaHost](iclrmetahost-interface.md)
- [Hosting](index.md)
