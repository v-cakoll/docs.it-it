---
title: Metodo ICLRDataTarget2::AllocVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
ms.openlocfilehash: 7640f7fafd0bf52a302ac0da1e5df39b5da22d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091152"
---
# <a name="iclrdatatarget2allocvirtual-method"></a>Metodo ICLRDataTarget2::AllocVirtual
Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per allocare memoria nello spazio degli indirizzi del processo di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `addr`  
 in Valore `CLRDATA_ADDRESS` che specifica l'indirizzo iniziale richiesto della memoria da allocare.  
  
 `size`  
 in Dimensione, in byte, della memoria da allocare.  
  
 `typeFlags`  
 in Flag che controllano l'allocazione della memoria. Vedere la funzione Win32 `VirtualAlloc`.  
  
 `protectFlags`  
 in Attributi di protezione per la memoria allocata. Vedere la funzione Win32 `VirtualAlloc`.  
  
 `virt`  
 out Puntatore a un valore `CLRDATA_ADDRESS` che specifica l'indirizzo iniziale effettivo della memoria allocata.  
  
## <a name="remarks"></a>Note  
 Il metodo `AllocVirtual` funge da wrapper logico per la funzione di `VirtualAlloc` Win32.  
  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [Metodo FreeVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
