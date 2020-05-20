---
title: Interfaccia ISymUnmanagedScope2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 886ba693183a6b99eb03635e95a9661d105de40e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610860"
---
# <a name="isymunmanagedscope2-interface"></a>Interfaccia ISymUnmanagedScope2
Rappresenta un ambito lessicale all'interno di un metodo. Questa interfaccia estende l'interfaccia [ISymUnmanagedScope](isymunmanagedscope-interface.md) con metodi che ottengono informazioni sulle costanti definite nell'ambito.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetConstantCount](isymunmanagedscope2-getconstantcount-method.md)|Ottiene un conteggio delle costanti definite in questo ambito.|  
|[Metodo GetConstants](isymunmanagedscope2-getconstants-method.md)|Ottiene le costanti locali definite all'interno di questo ambito.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedScope](isymunmanagedscope-interface.md)
