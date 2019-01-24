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
ms.openlocfilehash: 2d534ae381e0dc105731cf0a537f81afe80d87e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732739"
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`mdMethod`|Token di metadati del metodo.|  
|`delta`|Il numero di righe che è stato spostato il metodo.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl  
  
## <a name="see-also"></a>Vedere anche
- [Strutture dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
