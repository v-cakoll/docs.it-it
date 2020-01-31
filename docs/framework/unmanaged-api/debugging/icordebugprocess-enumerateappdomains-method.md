---
title: Metodo ICorDebugProcess::EnumerateAppDomains
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
ms.openlocfilehash: 35e3e37b1487b5dda9945402c6a3338384147f9a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792633"
---
# <a name="icordebugprocessenumerateappdomains-method"></a>Metodo ICorDebugProcess::EnumerateAppDomains
Enumera tutti i domini applicazione in questo processo.  
  
## <a name="syntax"></a>Sintassi  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppAppDomains`  
 out Puntatore all'indirizzo di un [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) che rappresenta un enumeratore per i domini applicazione in questo processo.  
  
## <a name="remarks"></a>Note  
 Questo metodo può essere utilizzato prima del callback [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
