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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7351dfb046653e4f3e20e0dc8a4bba8653ec36e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdatatarget2freevirtual-method"></a>Metodo ICLRDataTarget2::FreeVirtual
Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per liberare memoria precedentemente allocato nello spazio degli indirizzi del processo di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `addr`  
 [in] Oggetto `CLRDATA_ADDRESS` valore che specifica l'indirizzo iniziale della memoria da liberare.  
  
 `size`  
 [in] Le dimensioni in byte, della memoria da liberare.  
  
 `typeFlags`  
 [in] Flag che controllano la liberazione della memoria. Vedere Win32 `VirtualFree` (funzione).  
  
## <a name="remarks"></a>Note  
 Il `FreeVirtual` metodo funge da wrapper logico per Win32 `VirtualFree` (funzione).  
  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Clrdata. idl, Clrdata. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [Metodo AllocVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
