---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce462c4e7e9c8fb11ee74a91f3ece2465a44a834
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a>Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
Imposta l'offset per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono IL.  
  
 Offset IL di catch generato viene utilizzata dal debugger per gestire catch come se si trattasse di codice non utente, anche se potrebbe verificarsi in un metodo del codice utente. In particolare, viene utilizzato in risposta a un **CatchHandlerFound** evento dell'eccezione.  
  
## <a name="syntax"></a>Sintassi  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce `HRESULT`.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
