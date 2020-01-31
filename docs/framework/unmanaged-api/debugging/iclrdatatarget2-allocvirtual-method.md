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
ms.openlocfilehash: 51c06a7f8ea22fc73236131954781d8755274041
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789080"
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
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget2](iclrdatatarget2-interface.md)
- [Metodo FreeVirtual](iclrdatatarget2-freevirtual-method.md)
