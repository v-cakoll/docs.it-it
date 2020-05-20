---
title: Interfaccia ISymUnmanagedScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 1ee406c97fa4ccb7f87098cba2925568d8ce069f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615345"
---
# <a name="isymunmanagedscope-interface"></a>Interfaccia ISymUnmanagedScope
Rappresenta un ambito lessicale all'interno di un metodo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetChildren](isymunmanagedscope-getchildren-method.md)|Ottiene gli elementi figlio di questo ambito.|  
|[Metodo GetEndOffset](isymunmanagedscope-getendoffset-method.md)|Ottiene l'offset finale per questo ambito.|  
|[Metodo GetLocalCount](isymunmanagedscope-getlocalcount-method.md)|Ottiene un conteggio delle variabili locali definite in questo ambito.|  
|[Metodo GetLocals](isymunmanagedscope-getlocals-method.md)|Ottiene le variabili locali definite in questo ambito.|  
|[Metodo GetMethod](isymunmanagedscope-getmethod-method.md)|Ottiene il metodo che contiene questo ambito.|  
|[Metodo GetNamespaces](isymunmanagedscope-getnamespaces-method.md)|Ottiene gli spazi dei nomi utilizzati all'interno di questo ambito.|  
|[Metodo GetParent](isymunmanagedscope-getparent-method.md)|Ottiene l'ambito padre di questo ambito.|  
|[Metodo GetStartOffset](isymunmanagedscope-getstartoffset-method.md)|Ottiene l'offset iniziale per questo ambito.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedScope2](isymunmanagedscope2-interface.md)
