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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4096b0ae083e0b6c0598ea18cc8b33c2fdfe3e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116295"
---
# <a name="icorpublishenumprocesses-method"></a>Metodo ICorPublish::EnumProcesses
Ottiene un enumeratore per i processi gestiti in esecuzione nel computer.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `Type`  
 Valore di [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumerazione che specifica il tipo di processo da recuperare. Nella versione corrente, solo COR_PUB_MANAGEDONLY è valido.  
  
 `ppIEnum`  
 Un puntatore all'indirizzo di un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) istanza che rappresenta l'enumeratore dei processi.  
  
## <a name="remarks"></a>Note  
 Raccolta dell'enumeratore dei processi si basa su uno snapshot dei processi in esecuzione quando il `EnumProcesses` viene chiamato il metodo. L'enumeratore non verrà inclusi tutti i processi che termina prima o dopo l'avvio `EnumProcesses` viene chiamato.  
  
 Il `EnumProcesses` metodo può essere chiamato più volte su questo [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) istanza per creare un nuovo insieme aggiornato di processi. Le raccolte esistenti non influiranno dalle chiamate successive del `EnumProcesses` (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub.idl, CorPub.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
