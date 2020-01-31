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
ms.openlocfilehash: 7eda9bfff6de6b386c16ad0a188931d9d3adcb93
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793664"
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
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget2](iclrdatatarget2-interface.md)
- [Metodo AllocVirtual](iclrdatatarget2-allocvirtual-method.md)
