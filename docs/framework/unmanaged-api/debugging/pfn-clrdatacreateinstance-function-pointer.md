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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ee003d668916baec313c6115cc12826286f6cdd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a>Puntatore alla funzione PFN_CLRDataCreateInstance
Punta a una funzione che crea un oggetto di interfaccia per l'elemento di destinazione specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `iid`  
 [in] Identificatore dell'interfaccia per creare un'istanza.  
  
 `target`  
 [in] Un puntatore a un utente implementato [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) oggetto che rappresenta l'elemento di destinazione per cui creare l'oggetto di interfaccia.  
  
 `iface`  
 [out] Un puntatore all'indirizzo dell'oggetto interfaccia restituita.  
  
## <a name="remarks"></a>Note  
 Il `ICLRDataTarget` oggetto è implementato dal writer dell'applicazione di debug. L'implementazione varia a seconda del tipo di elemento di destinazione rappresentato. L'elemento di destinazione potrebbe essere un processo, i dump di memoria, computer remoto e così via.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Clrdata. idl  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
