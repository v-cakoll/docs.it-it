---
title: Metodo ICorDebugAppDomain::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d172af14aba418d6e97fe77724bf91b0eaf1c56a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403114"
---
# <a name="icordebugappdomaingetprocess-method"></a>Metodo ICorDebugAppDomain::GetProcess
Ottiene il processo che contiene il dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppProcess`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
