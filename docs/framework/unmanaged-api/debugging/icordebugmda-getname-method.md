---
title: Metodo ICorDebugMDA::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
ms.openlocfilehash: 6a6769265a2e140f1fa001bb8240bc5d4bd76018
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213673"
---
# <a name="icordebugmdagetname-method"></a>Metodo ICorDebugMDA::GetName
Ottiene una stringa contenente il nome dell'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](icordebugmda-interface.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cchName`  
 [in] Dimensione della matrice `szName`.  
  
 `pcchName`  
 out Puntatore alla lunghezza del nome.  
  
 `szName`  
 out Matrice in cui archiviare il nome.  
  
## <a name="remarks"></a>Osservazioni  
 I nomi dell'assistente al debug gestito sono valori univoci. Il `GetName` metodo rappresenta una pratica alternativa alle prestazioni per ottenere il flusso XML ed estrarre il nome dal flusso in base allo schema.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugMDA](icordebugmda-interface.md)
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
