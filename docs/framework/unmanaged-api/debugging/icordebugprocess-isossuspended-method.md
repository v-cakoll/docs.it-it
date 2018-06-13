---
title: Metodo ICorDebugProcess::IsOSSuspended
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b65a621541f2b4a800f6b3708a6b257374c5866
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419819"
---
# <a name="icordebugprocessisossuspended-method"></a>Metodo ICorDebugProcess::IsOSSuspended
Ottiene un valore che indica se il thread specificato è stato sospeso in seguito il debugger di interruzione del processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a>Parametri  
 `threadID`  
 [in] L'ID del thread in questione.  
  
 `pbSuspended`  
 [out] Un puntatore a un valore booleano che è `true` se il thread specificato è stato sospeso; in caso contrario *`pbSuspended` è `false`.  
  
## <a name="remarks"></a>Note  
 Quando il thread specificato è stata sospesa a causa del debugger di interruzione del processo, un conteggio di sospensione Win32 del thread specificato viene incrementato di uno. L'interfaccia utente (UI) di debugger può tenere conto di questa informazioni se viene visualizzato il sistema operativo delle sospensioni conteggio del thread per l'utente.  
  
 Il `IsOSSuspended` metodo ha senso solo nel contesto di debug non gestito. Durante il debug gestito, i thread sono in modo cooperativo sospeso anziché sospeso del sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
