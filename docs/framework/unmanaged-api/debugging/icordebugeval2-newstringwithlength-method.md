---
title: Metodo ICorDebugEval2::NewStringWithLength
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
ms.openlocfilehash: a2b76cb59a95082e0cf9c0884b8277cca3c8fe8d
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976070"
---
# <a name="icordebugeval2newstringwithlength-method"></a>Metodo ICorDebugEval2::NewStringWithLength
Crea una stringa della lunghezza specificata, con il contenuto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `string`  
 in Puntatore al valore stringa.  
  
 `uiLength`  
 in Lunghezza della stringa.  
  
## <a name="remarks"></a>Osservazioni  
 Se si prevede che il carattere null finale della stringa si trovi nella stringa gestita, il chiamante del `NewStringWithLength` metodo deve garantire che la lunghezza della stringa includa il carattere null finale.  
  
 La stringa viene sempre creata nel dominio applicazione in cui è attualmente in esecuzione il thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
