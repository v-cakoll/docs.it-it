---
title: Funzione CoEEShutDownCOM
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
ms.openlocfilehash: 4e85a9a98bf0550fa906f8b905c73890948f4ac1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124935"
---
# <a name="coeeshutdowncom-function"></a>Funzione CoEEShutDownCOM
Forza la Common Language Runtime (CLR) a rilasciare tutti i puntatori di interfaccia contenuti in Runtime Callable Wrapper (RCW). Questo ha l'effetto di rilasciare tutte le cache RCW. Questa funzione globale è deprecata nel .NET Framework 4. Usare invece il punto di ingresso per un runtime specifico.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Note  
 La funzione `CoEEShutDownCOM` rilascia innanzitutto tutti i RCW in tutti i contesti e in tutte le cache, quindi rimuove eventuali notifiche di chiusura presenti nel programma di installazione. Non viene eseguito lo scaricamento della DLL.  
  
> [!CAUTION]
> Questa funzione ha effetto su tutti i runtime caricati nel processo.  
  
 A partire da .NET Framework 4, chiamare il punto di ingresso per questa funzione sul runtime specifico che si vuole modificare. Per ottenere il punto di ingresso, chiamare il metodo [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) e specificare "CoEEShutDownCOM".  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
