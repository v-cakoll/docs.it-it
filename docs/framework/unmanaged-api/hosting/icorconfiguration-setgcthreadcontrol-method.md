---
title: Metodo ICorConfiguration::SetGCThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 7874424150e0f4e1818ad9c72e31fd584e016829
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762396"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a>Metodo ICorConfiguration::SetGCThreadControl
Imposta l'interfaccia di callback per la pianificazione di thread per le attività non di runtime che altrimenti verrebbero bloccate per un Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pGCThreadControl`  
 in Puntatore a un oggetto [IGCThreadControl](igcthreadcontrol-interface.md) che notifica all'host la sospensione dei thread per le attività non in fase di esecuzione.  
  
## <a name="remarks"></a>Osservazioni  
 L'host può scegliere all'interno del callback [IGCThreadControl:: ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) se ripianificare un thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorConfiguration](icorconfiguration-interface.md)
