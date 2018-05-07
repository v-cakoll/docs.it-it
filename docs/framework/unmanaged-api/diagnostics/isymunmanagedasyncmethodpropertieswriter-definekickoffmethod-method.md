---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a476d92486d7f2523dfbcc8b25e9c11e26c55f2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a>Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
Imposta il metodo di avvio che avvia l'operazione asincrona.  
  
## <a name="syntax"></a>Sintassi  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce `HRESULT`.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
