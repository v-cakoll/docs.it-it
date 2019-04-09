---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce3c135e031d0c8425e990811fedc40f4ec45243
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226612"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a>Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
Imposta il metodo inizio che avvia l'operazione asincrona.  
  
## <a name="syntax"></a>Sintassi  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce `HRESULT`.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
