---
title: Struttura StackTrace_SimpleContext
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
ms.openlocfilehash: 1cd3c34fc292e4a050fa8a75078283e34425fc8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139125"
---
# <a name="stacktrace_simplecontext-structure"></a>Struttura StackTrace_SimpleContext
Fornisce un contesto semplice che può essere usato invece di una struttura `CONTEXT` completa.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`StackOffset`|Il puntatore dello stack o il puntatore di stack di immissione (ESP) sulle piattaforme x86.|  
|`FrameOffset`|Offset del frame oppure il registro EBP sulle piattaforme x86.|  
|`InstructionOffset`|Puntatore all'istruzione oppure il puntatore all'istruzione Enter (PEI) sulle piattaforme x86.|  
  
## <a name="remarks"></a>Note  
 Poiché le funzioni di analisi dello stack in genere devono restituire solo l'indirizzo, l'offset del frame e l'indirizzo dello stack, è possibile usare facoltativamente la struttura di `SimpleContext` anziché una struttura di `CONTEXT` di grandi dimensioni.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** SOS_Stacktrace. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
