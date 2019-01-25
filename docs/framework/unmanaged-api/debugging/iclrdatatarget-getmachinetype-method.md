---
title: Metodo ICLRDataTarget::GetMachineType
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15890bb4052905ef448501ae759669f8a1dfd444
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735597"
---
# <a name="iclrdatatargetgetmachinetype-method"></a>Metodo ICLRDataTarget::GetMachineType
Ottiene l'identificatore per il tipo di set di istruzioni che utilizza il processo di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `machineType`  
 [out] Usa puntatore a un valore che indica che il set di istruzioni che il processo di destinazione. L'oggetto restituito `machineType` è una delle costanti IMAGE_FILE_MACHINE, che sono definite nel file di intestazione Winnt. H.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData.idl, ClrData.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
