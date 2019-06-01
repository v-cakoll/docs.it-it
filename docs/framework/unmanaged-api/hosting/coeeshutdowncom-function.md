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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a28b9d6e41d0572d423576f5b4024a60a70216c
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456870"
---
# <a name="coeeshutdowncom-function"></a>Funzione CoEEShutDownCOM
Forza common language runtime (CLR) per rilasciare tutti i puntatori di interfaccia che vengono mantenuti all'interno di runtime callable wrapper (RCW). Questo ha l'effetto di rilascio di tutte le cache RCW. Questa funzione globale è deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Usare invece il punto di ingresso per un runtime specifico.  
  
## <a name="syntax"></a>Sintassi  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Note  
 Il `CoEEShutDownCOM` funzione prima di tutto rilascia tutti i RCW in tutti i contesti e in tutte le cache e quindi rimuove qualsiasi notifica di chiusura esistente nel programma di installazione. Non lo scaricamento di DLL si verifica.  
  
> [!CAUTION]
>  Questa funzione influisce su tutti i runtime caricati nel processo.  
  
 A partire da .NET Framework 4, chiamare il punto di ingresso per questa funzione runtime specifico che si vuole modificare. Per ottenere il punto di ingresso, chiamare il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) (metodo) e specificare "CoEEShutDownCOM".  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
