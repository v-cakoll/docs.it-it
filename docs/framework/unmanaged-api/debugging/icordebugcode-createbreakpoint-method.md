---
title: Metodo ICorDebugCode::CreateBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f8be1a1831bc00eea3cfb659b46b67b6a78711
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747729"
---
# <a name="icordebugcodecreatebreakpoint-method"></a>Metodo ICorDebugCode::CreateBreakpoint
Crea un punto di interruzione in questo segmento di codice in corrispondenza dell'offset specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `offset`  
 [in] Offset da cui creare il punto di interruzione.  
  
 `ppBreakpoint`  
 [out] Un puntatore all'indirizzo di un oggetto "ICorDebugFunctionBreakpoint" che rappresenta il punto di interruzione.  
  
## <a name="remarks"></a>Note  
 Prima che il punto di interruzione è attivo, è necessario aggiungerlo all'oggetto processo.  
  
 Se questo codice è codice Microsoft intermediate language (MSIL) e vi è un just-in-time (JIT)-versione nativa compilata del codice, il punto di interruzione verrà applicati anche il codice compilato tramite JIT. (Lo stesso vale se il codice viene compilato tramite JIT in un secondo momento.)  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
