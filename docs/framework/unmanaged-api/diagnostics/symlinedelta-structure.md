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
ms.openlocfilehash: fabc8f77b12865d0d971b5934d7de27b52f3e813
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914641"
---
# <a name="symlinedelta-structure"></a>Struttura SYMLINEDELTA
Fornisce informazioni sul gestore di simboli sui metodi che sono state spostate in seguito a modifiche.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`mdMethod`|Token di metadati del metodo.|  
|`delta`|Il numero di righe che è stato spostato il metodo.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl  
  
## <a name="see-also"></a>Vedere anche

- [Strutture dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
