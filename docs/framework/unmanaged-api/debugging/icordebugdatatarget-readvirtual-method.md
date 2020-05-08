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
ms.openlocfilehash: 36a18d92f05db55957bba55de84490c0da1a1f86
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976512"
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
 out Numero di byte effettivamente letti dall'indirizzo di destinazione. Questo può essere minore di `bytesRequested`.  
  
## <a name="remarks"></a>Osservazioni  
 Se è possibile leggere il primo byte (all'indirizzo iniziale specificato), la chiamata dovrebbe restituire esito positivo (per supportare una lettura efficiente delle strutture di dati con lunghezza autodescrittiva, ad esempio stringhe con terminazione null).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget](icordebugdatatarget-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
