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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45b6b8593331801dd237d0a730afbd5a6a714bbf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774187"
---
# <a name="esymbolreadingpolicy-enumeration"></a>Enumerazione ESymbolReadingPolicy
Contiene valori che impostano i criteri per la lettura dei file di programma (PDB) del database.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`eSymbolReadingAlways`|Specifica che il debugger deve sempre leggere i file PDB.|  
|`eSymbolReadingFullTrustOnly`|Specifica che il debugger deve leggere solo i file PDB associati ad assembly completamente attendibili.|  
|`eSymbolReadingNever`|Specifica che il debugger mai deve leggere i file PDB.|  
  
## <a name="remarks"></a>Note  
 Il `ESymbolReadingPolicy` enumerazione viene utilizzata con il [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
