---
title: Interfaccia ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: eaf2e8e60d9812ab6a31fb3b9050cbaae0f1a9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609469"
---
# <a name="isymunmanagedwriter4-interface"></a>Interfaccia ISymUnmanagedWriter4
Interfaccia ISymUnmanagedWriter4.  
  
## <a name="syntax"></a>Sintassi  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a>Metodi  
 Per l'interfaccia sono disponibili i seguenti metodi:  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetDebugInfoWithPadding](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|Funziona allo stesso modo del [Metodo GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , con la differenza che la stringa di percorso viene riempita con zeri che seguono il carattere null di terminazione per fare in modo che i dati della stringa siano di dimensioni fisse `MAX_PATH` . La spaziatura interna viene specificata solo se la lunghezza della stringa di percorso è minore di `MAX_PATH` .<br /><br /> In questo modo è più semplice scrivere strumenti che differenziano i file PE.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)
