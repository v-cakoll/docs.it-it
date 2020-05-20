---
title: Enumerazione ESymbolReadingPolicy
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 5c3d1d0ebc56ee93c950afb4f015c8e10ec6a0f7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616177"
---
# <a name="esymbolreadingpolicy-enumeration"></a>Enumerazione ESymbolReadingPolicy
Contiene valori che impostano i criteri per la lettura dei file di database di programma (PDB).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`eSymbolReadingAlways`|Specifica che il debugger deve sempre leggere i file PDB.|  
|`eSymbolReadingFullTrustOnly`|Specifica che il debugger deve leggere solo i file PDB associati a assembly con attendibilità totale.|  
|`eSymbolReadingNever`|Specifica che il debugger non deve mai leggere i file PDB.|  
  
## <a name="remarks"></a>Osservazioni  
 L' `ESymbolReadingPolicy` enumerazione viene utilizzata con il metodo [ICLRDebugManager:: SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](hosting-enumerations.md)
