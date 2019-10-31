---
title: Metodo ICorDebugEval::NewString
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
ms.openlocfilehash: 8a5d421bf0eb8ec5a34fe21d6efc79bbe56c294c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137649"
---
# <a name="icordebugevalnewstring-method"></a>Metodo ICorDebugEval::NewString
Alloca una nuova istanza di stringa con il contenuto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `string`  
 in Puntatore al contenuto della stringa.  
  
## <a name="remarks"></a>Note  
 La stringa viene sempre creata nel dominio applicazione in cui è attualmente in esecuzione il thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
