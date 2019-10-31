---
title: Interfaccia ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: a656777461c50b5a1593917278eb54abda982dc2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134572"
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
|[Metodo GetDebugInfoWithPadding](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|Funziona allo stesso modo del [Metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , con la differenza che la stringa di percorso viene riempita con zeri che seguono il carattere null di terminazione per fare in modo che i dati della stringa siano di dimensioni fisse `MAX_PATH`. La spaziatura interna viene specificata solo se la lunghezza della stringa di percorso è minore di `MAX_PATH`.<br /><br /> In questo modo è più semplice scrivere strumenti che differenziano i file PE.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedWriter3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
