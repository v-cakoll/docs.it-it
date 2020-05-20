---
title: Interfaccia ISymUnmanagedWriter2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
ms.openlocfilehash: 1fe6055d930c6d30e947d6bc774d0520a9e175ae
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614682"
---
# <a name="isymunmanagedwriter2-interface"></a>Interfaccia ISymUnmanagedWriter2
Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili. Questa interfaccia estende l'interfaccia [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DefineConstant2](isymunmanagedwriter2-defineconstant2-method.md)|Definisce un nome per un valore costante.|  
|[Metodo DefineGlobalVariable2](isymunmanagedwriter2-defineglobalvariable2-method.md)|Definisce una variabile globale singola.|  
|[Metodo DefineLocalVariable2](isymunmanagedwriter2-definelocalvariable2-method.md)|Definisce una singola variabile nell'ambito lessicale corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Interfaccia ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)
