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
ms.openlocfilehash: 20b73549d30fe210e4d44902d2f459ea9c682360
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860489"
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
 in `CLRDATA_ADDRESS` Valore che specifica l'indirizzo iniziale richiesto della memoria da allocare.  
  
 `size`  
 in Dimensione, in byte, della memoria da allocare.  
  
 `typeFlags`  
 in Flag che controllano l'allocazione della memoria. Vedere la funzione `VirtualAlloc` Win32.  
  
 `protectFlags`  
 in Attributi di protezione per la memoria allocata. Vedere la funzione `VirtualAlloc` Win32.  
  
 `virt`  
 out Puntatore a un `CLRDATA_ADDRESS` valore che specifica l'indirizzo iniziale effettivo della memoria allocata.  
  
## <a name="remarks"></a>Osservazioni  
 Il `AllocVirtual` metodo funge da wrapper logico per la funzione Win32 `VirtualAlloc` .  
  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget2](iclrdatatarget2-interface.md)
- [Metodo FreeVirtual](iclrdatatarget2-freevirtual-method.md)
