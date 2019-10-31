---
title: Struttura CodeChunkInfo
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
ms.openlocfilehash: d33c8b31473e389e07fb24076dc32272e9dde387
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132396"
---
# <a name="codechunkinfo-structure"></a>Struttura CodeChunkInfo

Rappresenta un singolo blocco di codice in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`startAddr`|Valore `CORDB_ADDRESS` che specifica l'indirizzo iniziale del blocco.|  
|`length`|Dimensione, in byte, del blocco.|  
  
## <a name="remarks"></a>Note  
 Il singolo blocco di codice è un'area di codice nativo che fa parte di un oggetto di codice, ad esempio una funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetCodeChunks](icordebugcode2-getcodechunks-method.md)
- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
