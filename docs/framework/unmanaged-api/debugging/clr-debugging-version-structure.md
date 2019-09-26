---
title: Struttura CLR_DEBUGGING_VERSION
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4528ccd77fed2ea2a9b2d08243ffa1535bfad1ae
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274079"
---
# <a name="clr_debugging_version-structure"></a>Struttura CLR_DEBUGGING_VERSION
Definisce la versione del prodotto di Common Language Runtime (CLR) per fini di debug.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`wStructVersion`|Numero di versione della struttura|  
|`wMajor`|Numero di versione principale.|  
|`wMinor`|Numero di versione secondario.|  
|`wBuild`|Numero di Build.|  
|`wRevision`|Numero di revisione.|  
  
## <a name="remarks"></a>Note  
 La `CLR_DEBUGGING_VERSION` struttura corrisponde alla struttura COR_VERSION, tuttavia, la `CLR_DEBUGGING_VERSION` struttura fornisce un campo della versione della struttura aggiuntiva (`wStructVersion`). Attualmente, questo campo deve essere impostato su zero.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
