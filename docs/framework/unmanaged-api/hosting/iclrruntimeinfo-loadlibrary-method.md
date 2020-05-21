---
title: Metodo ICLRRuntimeInfo::LoadLibrary
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: 09c80c3a56d86943ebe00e5222bb5452ab44e150
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762175"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a>Metodo ICLRRuntimeInfo::LoadLibrary
Carica una libreria di .NET Framework dalla Common Language Runtime (CLR) rappresentata da un'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .  
  
 Questo metodo sostituisce la funzione [LoadLibraryShim](loadlibraryshim-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzDllName`  
 in Nome dell'assembly da caricare.  
  
 `phndModule`  
 out Handle per l'assembly caricato.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pwzDllName` o `phndModule` è null.|  
|E_OUTOFMEMORY|La memoria disponibile non è sufficiente per gestire la richiesta.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo carica solo le DLL incluse nel pacchetto ridistribuibile .NET Framework. Non è in grado di caricare assembly generati dall'utente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
