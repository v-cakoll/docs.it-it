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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 77cd8b7d791d11f6d40386f4747c60cd4832521a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428094"
---
# <a name="symlinedelta-structure"></a>Struttura SYMLINEDELTA
Fornisce informazioni per il gestore dei simboli sui metodi che sono stati spostati in seguito a modifiche.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`mdMethod`|Token di metadati del metodo.|  
|`delta`|Il numero di righe, che il metodo è stato spostato.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
