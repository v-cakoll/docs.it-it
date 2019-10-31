---
title: 'Metodo ICorDebugMutableDataTarget:: WriteVirtual'
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 5947caa8dfb97574bb4b3c5634d962df153211c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132685"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a>Metodo ICorDebugMutableDataTarget:: WriteVirtual
Scrive dalla memoria nello spazio degli indirizzi del processo di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 [in] Indirizzo in cui scrivere il contenuto di `pBuffer`.  
  
 `pBuffer`  
 [in] Puntatore a una matrice di byte che contiene i byte da scrivere.  
  
 `address`  
 [in] Numero di byte in `pBuffer`.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` in caso di esito positivo o qualsiasi altro `HRESULT` in caso di errore.  
  
## <a name="remarks"></a>Note  
 Se non è possibile scrivere dei byte, la chiamata al metodo non riesce e non modifica i byte nello spazio degli indirizzi di destinazione (altrimenti la destinazione potrebbe trovarsi in uno stato incoerente che renderebbe il debug successivo inaffidabile).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugMutableDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
