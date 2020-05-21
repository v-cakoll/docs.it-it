---
title: Metodo ICorRuntimeHost::LocksHeldByLogicalThread
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
ms.openlocfilehash: 265ab5ae03b7b42c4f5f429df5d659d60e55f18e
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760719"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a>Metodo ICorRuntimeHost::LocksHeldByLogicalThread
Recupera il numero di blocchi presenti nel thread corrente.  
  
 Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pCount`  
 out Puntatore al numero di blocchi presenti nel thread corrente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorRuntimeHost](icorruntimehost-interface.md)
