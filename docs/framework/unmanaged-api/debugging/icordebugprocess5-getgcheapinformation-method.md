---
title: Metodo ICorDebugProcess5::GetGCHeapInformation
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
ms.openlocfilehash: 3aa9fe884b16a239f5105dd262edeb8fc3e4abaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084410"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a>Metodo ICorDebugProcess5::GetGCHeapInformation
Fornisce informazioni generali sull'heap di Garbage Collection, ad esempio se è attualmente enumerabile.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pHeapInfo`  
 out Puntatore a un valore [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) che fornisce informazioni generali sull'heap Garbage Collection.  
  
## <a name="remarks"></a>Note  
 È necessario chiamare il metodo `ICorDebugProcess5::GetGCHeapInformation` prima di enumerare le aree heap o singoli heap per assicurarsi che le strutture Garbage Collection nel processo siano attualmente valide. Non è possibile eseguire il percorso dell'heap Garbage Collection mentre è in corso una raccolta. In caso contrario, è possibile che l'enumerazione acquisisca Garbage Collection strutture che non sono valide.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
