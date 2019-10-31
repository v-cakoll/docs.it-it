---
title: Metodo ICorPublish::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 5f0dd814ad5adfa1b0dd7199530a3f993634a548
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121788"
---
# <a name="icorpublishenumprocesses-method"></a>Metodo ICorPublish::EnumProcesses
Ottiene un enumeratore per i processi gestiti in esecuzione nel computer.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `Type`  
 Valore dell'enumerazione [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) che specifica il tipo di processo da recuperare. Nella versione corrente, solo COR_PUB_MANAGEDONLY è valido.  
  
 `ppIEnum`  
 Puntatore all'indirizzo di un'istanza di [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) che rappresenta l'enumeratore dei processi.  
  
## <a name="remarks"></a>Note  
 La raccolta di processi dell'enumeratore si basa su uno snapshot dei processi in esecuzione quando viene chiamato il metodo `EnumProcesses`. L'enumeratore non includerà i processi che terminano prima o si avviano dopo la chiamata di `EnumProcesses`.  
  
 Il metodo `EnumProcesses` può essere chiamato più di una volta in questa istanza di [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) per creare una nuova raccolta aggiornata di processi. Le raccolte esistenti non saranno interessate dalle chiamate successive del metodo `EnumProcesses`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
