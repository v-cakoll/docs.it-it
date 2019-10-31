---
title: Puntatore alla funzione PFN_CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
ms.openlocfilehash: 426a8acf2e9319725cf592db00dc97c8960bca4f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139172"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a>Puntatore alla funzione PFN_CLRDataCreateInstance
Punta a una funzione che crea un oggetto interfaccia per l'elemento di destinazione specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `iid`  
 in Identificatore dell'interfaccia di cui creare un'istanza.  
  
 `target`  
 in Puntatore a un oggetto [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) implementato dall'utente che rappresenta l'elemento di destinazione per il quale creare l'oggetto interfaccia.  
  
 `iface`  
 out Puntatore all'indirizzo dell'oggetto interfaccia restituito.  
  
## <a name="remarks"></a>Note  
 L'oggetto `ICLRDataTarget` viene implementato dal writer dell'applicazione di debug. L'implementazione dipende dal tipo di elemento di destinazione rappresentato. L'elemento di destinazione può essere un processo, un dump della memoria, un computer remoto e così via.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
