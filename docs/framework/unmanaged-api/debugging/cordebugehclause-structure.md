---
title: Struttura CorDebugEHClause
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
ms.openlocfilehash: a889d6ba00c4a0eb96a9923a7dbe52f3b93aaba5
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795961"
---
# <a name="cordebugehclause-structure"></a>Struttura CorDebugEHClause
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Rappresenta una clausola di gestione delle eccezioni (EH, Exception Handling) per una determinata parte di codice del linguaggio intermedio (IL, Intermediate Language).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Description|  
|------------|-----------------|  
|`Flags`|Campo di bit che descrive le informazioni sull'eccezione nella clausola di gestione delle eccezioni. Per altre informazioni, vedere la sezione Osservazioni.|  
|`TryOffset`|Offset, in byte, del blocco `try` dall'inizio del corpo del metodo.|  
|`TryLength`|Lunghezza in byte del blocco `try`.|  
|`HandlerOffset`|Il percorso del gestore per questo blocco `try`.|  
|`HandlerLength`|Le dimensioni in byte del codice del gestore.|  
|`ClassToken`|Il token dei metadati per un gestore di eccezioni basato sul tipo.|  
|`FilterOffset`|Offset, in byte, dall'inizio del corpo del metodo per un gestore di eccezioni basato sul filtro.|  
  
## <a name="remarks"></a>Osservazioni  
 Una matrice di `CoreDebugEHClause` valori viene restituita dal metodo [GetEHClauses](icordebugilcode-getehclauses-method.md) .  
  
 Le informazioni sulla clausola di gestione delle eccezioni sono definite dalla specifica CLI. Per ulteriori informazioni, vedere [standard ECMA-355: Common Language Infrastructure (CLI), 6a Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 Il campo `flags` può contenere i flag seguenti. Si noti che non sono definiti in CorDebug.idl o CorDebug.h.  
  
|Flag|Valore|Descrizione|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|0x00000000|Clausola dell'eccezione tipizzata.|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|0x00000001|Clausola del gestore e del filtro eccezioni.|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|0x00000002|Clausola `finally`.|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|0x00000004|Clausola fault (una clausola `finally` che viene chiamata solo quando viene generata un'eccezione).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetEHClauses](icordebugilcode-getehclauses-method.md)
- [Strutture di debug](debugging-structures.md)
