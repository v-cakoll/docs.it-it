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
ms.openlocfilehash: 3eb8bffee9d30a89c39a900e600ebf171456b9f3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616788"
---
# <a name="coeeshutdowncom-function"></a>Funzione CoEEShutDownCOM
Forza la Common Language Runtime (CLR) a rilasciare tutti i puntatori di interfaccia contenuti in Runtime Callable Wrapper (RCW). Questo ha l'effetto di rilasciare tutte le cache RCW. Questa funzione globale è deprecata nel .NET Framework 4. Usare invece il punto di ingresso per un runtime specifico.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Osservazioni  
 La `CoEEShutDownCOM` funzione rilascia innanzitutto tutti i RCW in tutti i contesti e in tutte le cache, quindi rimuove eventuali notifiche di chiusura presenti nel programma di installazione. Non viene eseguito lo scaricamento della DLL.  
  
> [!CAUTION]
> Questa funzione ha effetto su tutti i runtime caricati nel processo.  
  
 A partire da .NET Framework 4, chiamare il punto di ingresso per questa funzione sul runtime specifico che si vuole modificare. Per ottenere il punto di ingresso, chiamare il metodo [ICLRRuntimeInfo:: GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) e specificare "CoEEShutDownCOM".  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../metadata/metadata-global-static-functions.md)
