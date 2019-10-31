---
title: Metodo ICLRDataTarget2::FreeVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
ms.openlocfilehash: c084a3fcbbc02504124a511c6e136be32f408d21
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112321"
---
# <a name="iclrdatatarget2freevirtual-method"></a>Metodo ICLRDataTarget2::FreeVirtual
Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per liberare memoria allocata in precedenza nello spazio degli indirizzi del processo di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `addr`  
 in Valore `CLRDATA_ADDRESS` che specifica l'indirizzo iniziale della memoria da liberare.  
  
 `size`  
 in Dimensione, in byte, della memoria da liberare.  
  
 `typeFlags`  
 in Flag che controllano la liberazione della memoria. Vedere la funzione Win32 `VirtualFree`.  
  
## <a name="remarks"></a>Note  
 Il metodo `FreeVirtual` funge da wrapper logico per la funzione di `VirtualFree` Win32.  
  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [Metodo AllocVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
