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
ms.openlocfilehash: 4be232ab557d582f3521b8775108c004b5a3dd78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403305"
---
# <a name="clrdebuggingversion-structure"></a>Struttura CLR_DEBUGGING_VERSION
Definisce la versione del prodotto di Common Language Runtime (CLR) per fini di debug.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Typedef struct _CLR_DEBUGGING_VERSION  
{  
WORD wStructVersion;  
WORD wMajor;   
WORD wMinor;  
WORD wBuild;  
WORD wRevision;  
}  CLR_DEBUGGING_VERSION;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`wStructVersion`|Il numero di versione della struttura|  
|`wMajor`|Numero di versione principale.|  
|`wMinor`|Numero di versione secondario.|  
|`wBuild`|Il numero di build.|  
|`wRevision`|Il numero di revisione.|  
  
## <a name="remarks"></a>Note  
 Il `CLR_DEBUGGING_VERSION` struttura è identica alla struttura COR_VERSION, tuttavia, il `CLR_DEBUGGING_VERSION` struttura fornisce un campo di versione della struttura aggiuntiva (`wStructVersion`). Attualmente questo campo deve essere impostato su zero.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
