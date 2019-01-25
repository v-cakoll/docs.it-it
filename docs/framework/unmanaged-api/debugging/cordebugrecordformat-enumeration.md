---
title: Enumerazione CorDebugRecordFormat
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45278b116ce1ea1a910d806df408c8692338d9a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634376"
---
# <a name="cordebugrecordformat-enumeration"></a>Enumerazione CorDebugRecordFormat
Descrive il formato dei dati in una matrice di byte che contiene informazioni su un evento di debug per le eccezioni native.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|I dati corrispondono a un record di eccezione Windows a 32 bit.|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|I dati corrispondono a un record di eccezione Windows a 64 bit.|  
  
## <a name="remarks"></a>Note  
 Un membro del `CorDebugRecordFormat` enumerazione viene passata al [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) metodo per indicare il formato della matrice di byte nella relativa `pRecord` argomento.  
  
> [!NOTE]
>  Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
