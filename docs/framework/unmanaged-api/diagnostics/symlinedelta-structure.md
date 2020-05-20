---
title: Struttura SYMLINEDELTA
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: fb3b89d25b4c2e23c3980b167db4279246c4d27b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609300"
---
# <a name="symlinedelta-structure"></a>Struttura SYMLINEDELTA
Fornisce informazioni al gestore di simboli sui metodi spostati in seguito a modifiche.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`mdMethod`|Token di metadati del metodo.|  
|`delta`|Il numero di righe in cui è stato spostato il metodo.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl  
  
## <a name="see-also"></a>Vedere anche

- [Strutture dell'archivio simboli di diagnostica](diagnostics-symbol-store-structures.md)
