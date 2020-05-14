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
ms.openlocfilehash: 70255a89cee13abfe63b01351f8ffba51e54665a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396396"
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
 Valore dell'enumerazione [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) che specifica il tipo di processo da recuperare. Nella versione corrente solo COR_PUB_MANAGEDONLY è valido.  
  
 `ppIEnum`  
 Puntatore all'indirizzo di un'istanza di [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) che rappresenta l'enumeratore dei processi.  
  
## <a name="remarks"></a>Commenti  
 La raccolta di processi dell'enumeratore si basa su uno snapshot dei processi in esecuzione quando `EnumProcesses` viene chiamato il metodo. L'enumeratore non includerà i processi che terminano prima o che si avvia dopo `EnumProcesses` la chiamata a.  
  
 Il `EnumProcesses` metodo può essere chiamato più di una volta in questa istanza di [ICorPublish](icorpublish-interface.md) per creare una nuova raccolta aggiornata di processi. Le raccolte esistenti non saranno interessate dalle chiamate successive del `EnumProcesses` metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorPublish](icorpublish-interface.md)
