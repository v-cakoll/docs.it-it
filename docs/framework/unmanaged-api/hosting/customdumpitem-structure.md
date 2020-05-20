---
title: Struttura CustomDumpItem
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
ms.openlocfilehash: 5c77a332593ba470d2e29b87cba182a770d5db7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616437"
---
# <a name="customdumpitem-structure"></a>Struttura CustomDumpItem
Descrive un elemento da aggiungere a un dump personalizzato nella segnalazione degli errori.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`itemKind`|Valore [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) che indica il tipo di elemento da aggiungere.|  
|`pReserved`|Attualmente non utilizzato. Gli elementi aggiunti all'Unione non devono essere maggiori delle dimensioni del puntatore. Se `struct` è necessario, è necessario allocarlo separatamente e puntare a tale oggetto.|  
  
## <a name="remarks"></a>Osservazioni  
 [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) accetta un parametro di tipo `CustomDumpItem` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. idl  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](hosting-structures.md)
