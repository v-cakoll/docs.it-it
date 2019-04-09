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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 809368ea19528a7ce00d4fcada06ef5724eb79a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228159"
---
# <a name="isymunmanagedscope-interface"></a>Interfaccia ISymUnmanagedScope
Rappresenta un ambito lessicale in un metodo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetChildren](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|Ottiene gli elementi figlio di questo ambito.|  
|[Metodo GetEndOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|Ottiene l'offset finale per l'ambito corrente.|  
|[Metodo GetLocalCount](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|Ottiene un conteggio delle variabili locali definite all'interno di questo ambito.|  
|[Metodo GetLocals](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|Ottiene le variabili locali definite all'interno di questo ambito.|  
|[Metodo GetMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|Ottiene il metodo che contiene questo ambito.|  
|[Metodo GetNamespaces](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|Ottiene gli spazi dei nomi utilizzati all'interno di questo ambito.|  
|[Metodo GetParent](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|Ottiene l'ambito padre di questo ambito.|  
|[Metodo GetStartOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|Ottiene l'offset iniziale per l'ambito corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedScope2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
