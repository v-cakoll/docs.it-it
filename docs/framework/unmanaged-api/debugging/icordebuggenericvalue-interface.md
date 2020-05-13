---
title: Interfaccia ICorDebugGenericValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: 7c5359ddf2c021f77ad1ea0a8579316c3c773fd5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209786"
---
# <a name="icordebuggenericvalue-interface"></a>Interfaccia ICorDebugGenericValue

Sottoclasse di "ICorDebugValue" che si applica a tutti i valori. Questa interfaccia fornisce i metodi Get e Set per il valore.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetValue](icordebuggenericvalue-getvalue-method.md)|Copia il valore nel buffer specificato.|  
|[Metodo SetValue](icordebuggenericvalue-setvalue-method.md)|Copia un nuovo valore dal buffer specificato.|  
  
## <a name="remarks"></a>Osservazioni  
 `ICorDebugGenericValue`è un'interfaccia secondaria perché non utilizzabile in remoto.  
  
 Per i tipi di riferimento, il valore è il riferimento anziché il contenuto del riferimento.  
  
 Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
