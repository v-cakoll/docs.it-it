---
title: Interfaccia ISymUnmanagedWriter3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
ms.openlocfilehash: 006045ce101884119f676e4f6324815eb21a10a4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614656"
---
# <a name="isymunmanagedwriter3-interface"></a>Interfaccia ISymUnmanagedWriter3
Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili. Questa interfaccia estende l'interfaccia [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Commit (metodo)](isymunmanagedwriter3-commit-method.md)|Consente di eseguire il commit delle modifiche scritte finora nel flusso.|  
|[Metodo OpenMethod2](isymunmanagedwriter3-openmethod2-method.md)|Apre un metodo e fornisce la relativa offset della sezione reale nell'immagine.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Interfaccia ISymUnmanagedWriter2](isymunmanagedwriter2-interface.md)
