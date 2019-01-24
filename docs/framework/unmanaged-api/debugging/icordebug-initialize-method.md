---
title: Metodo ICorDebug::Initialize
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7b4cf6c50d624f82a75f19b8e3f42c73910c4e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709299"
---
# <a name="icordebuginitialize-method"></a>Metodo ICorDebug::Initialize
Inizializza il `ICorDebug` oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a>Note  
 Il debugger deve chiamare `Initialize` al momento della creazione di servizi tempo necessario per inizializzare il debug. Questo metodo deve essere chiamato prima di qualsiasi altro metodo nel `ICorDebug` viene chiamato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
