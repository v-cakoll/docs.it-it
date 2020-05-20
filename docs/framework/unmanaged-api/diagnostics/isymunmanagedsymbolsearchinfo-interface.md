---
title: Interfaccia ISymUnmanagedSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: 308c501e17446719067d2dc0580d698c1770bf53
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610665"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a>Interfaccia ISymUnmanagedSymbolSearchInfo
Fornisce metodi che consentono di ottenere informazioni sul percorso di ricerca. Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetHRESULT](isymunmanagedsymbolsearchinfo-gethresult-method.md)|Ottiene HRESULT.|  
|[Metodo GetSearchPath](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|Ottiene il percorso di ricerca.|  
|[Metodo GetSearchPathLength](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|Ottiene la lunghezza del percorso di ricerca.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
