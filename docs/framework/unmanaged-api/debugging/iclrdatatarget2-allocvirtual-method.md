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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46532592057f4fa6d9883d46dcef2f8f9e5f7228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdatatarget2allocvirtual-method"></a>Metodo ICLRDataTarget2::AllocVirtual
Chiamato dai servizi di accesso ai dati di common language runtime (CLR) di allocazione della memoria nello spazio degli indirizzi di questo processo di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `addr`  
 [in] Oggetto `CLRDATA_ADDRESS` valore che specifica l'indirizzo iniziale richiesto della memoria da allocare.  
  
 `size`  
 [in] Le dimensioni in byte, della memoria da allocare.  
  
 `typeFlags`  
 [in] Flag che controllano l'allocazione di memoria. Vedere Win32 `VirtualAlloc` (funzione).  
  
 `protectFlags`  
 [in] Attributi di protezione per la memoria allocata. Vedere Win32 `VirtualAlloc` (funzione).  
  
 `virt`  
 [out] Un puntatore a un `CLRDATA_ADDRESS` valore che specifica l'indirizzo iniziale effettivo della memoria allocata.  
  
## <a name="remarks"></a>Note  
 Il `AllocVirtual` metodo funge da wrapper logico per Win32 `VirtualAlloc` (funzione).  
  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Clrdata. idl, Clrdata. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [Metodo FreeVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
