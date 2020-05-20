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
ms.openlocfilehash: 45ae947cda5b4ddadfb10f5b2bdc78a95f031703
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420688"
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
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`StackOffset`|Il puntatore dello stack o il puntatore di stack di immissione (ESP) sulle piattaforme x86.|  
|`FrameOffset`|Offset del frame oppure il registro EBP sulle piattaforme x86.|  
|`InstructionOffset`|Puntatore all'istruzione oppure il puntatore all'istruzione Enter (PEI) sulle piattaforme x86.|  
  
## <a name="remarks"></a>Osservazioni  
 Poiché le funzioni di analisi dello stack in genere devono restituire solo l'indirizzo, l'offset del frame e l'indirizzo dello stack, è possibile usare facoltativamente la `SimpleContext` struttura anziché una struttura di grandi dimensioni `CONTEXT` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** SOS_Stacktrace. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
