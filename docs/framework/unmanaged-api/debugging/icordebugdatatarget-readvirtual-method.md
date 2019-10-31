---
title: Metodo ICorDebugDataTarget::ReadVirtual
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
ms.openlocfilehash: 87316b20c5835d9b887355a1f9374fa5f2156e5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122176"
---
# <a name="icordebugdatatargetreadvirtual-method"></a>Metodo ICorDebugDataTarget::ReadVirtual
Ottiene un blocco di memoria contigua a partire dall'indirizzo specificato e lo restituisce nel buffer fornito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 in Indirizzo iniziale della memoria richiesta.  
  
 `pbuffer`  
 out Buffer in cui verrà archiviata la memoria.  
  
 `bytesRequested`  
 in Numero di byte da ottenere dall'indirizzo di destinazione.  
  
 `pBytesRead`  
 out Numero di byte effettivamente letti dall'indirizzo di destinazione. Questa operazione può essere inferiore a `bytesRequested`.  
  
## <a name="remarks"></a>Note  
 Se è possibile leggere il primo byte (all'indirizzo iniziale specificato), la chiamata dovrebbe restituire esito positivo (per supportare una lettura efficiente delle strutture di dati con lunghezza autodescrittiva, ad esempio stringhe con terminazione null).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
