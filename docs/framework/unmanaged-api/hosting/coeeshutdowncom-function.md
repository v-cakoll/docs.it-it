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
ms.openlocfilehash: f0b30cc2c499644ffc97a734e1554e4e352b34af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="coeeshutdowncom-function"></a>Funzione CoEEShutDownCOM
Impone a common language runtime (CLR) per rilasciare tutti i puntatori di interfaccia, contiene all'interno di runtime callable wrapper (RCW). Questo ha l'effetto di rilascio di tutte le cache RCW. Questa funzione globale è deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Utilizzare invece il punto di ingresso per una specifica del runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Note  
 Il `CoEEShutDownCOM` funzione innanzitutto rilascia tutti i RCW in tutti i contesti e in tutte le cache e quindi rimuove qualsiasi notifica di chiusura esistente nel programma di installazione. Non lo scaricamento di DLL si verifica.  
  
> [!CAUTION]
>  Questa funzione influisce su tutti i runtime caricati nel processo.  
  
 A partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], chiamare il punto di ingresso per questa funzione sull'ambiente di esecuzione specifico che si vuole modificare. Per ottenere il punto di ingresso, chiamare il [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) (metodo) e specificare "CoEEShutDownCOM".  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
