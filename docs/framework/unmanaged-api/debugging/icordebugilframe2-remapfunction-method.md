---
title: Metodo ICorDebugILFrame2::RemapFunction
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdcc2eccbb24a92643415db8e5d267033ac1ca0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758757"
---
# <a name="icordebugilframe2remapfunction-method"></a>Metodo ICorDebugILFrame2::RemapFunction
Esegue un nuovo mapping di una funzione modificata specificando il nuovo offset di Microsoft intermediate language (MSIL)  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `newILOffset`  
 [in] Nuovo offset MSIL dello stack frame in corrispondenza del quale deve essere posizionato il puntatore all'istruzione. Questo valore deve essere un punto di sequenza.  
  
 È responsabilità del chiamante per garantire la validità del valore. Ad esempio, l'offset MSIL non valida se è esterno ai limiti della funzione.  
  
## <a name="remarks"></a>Note  
 Funzione del frame è stata modificata, il debugger può chiamare il `RemapFunction` metodo per sostituire la versione più recente della funzione del frame in modo da poter essere eseguito. Verrà avviata l'esecuzione del codice in corrispondenza dell'offset MSIL specificato.  
  
> [!NOTE]
>  La chiamata `RemapFunction`, ad esempio la chiamata [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), immediatamente invalida tutte le interfacce di debug che sono correlate alla generazione di un'analisi dello stack del thread. Tali interfacce includono [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame e ICorDebugNativeFrame.  
  
 Il `RemapFunction` metodo può essere chiamato solo nel contesto del frame corrente e solo in uno dei seguenti casi:  
  
- Dopo la ricezione di un [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback non è ancora stata derivate.  
  
- Durante l'esecuzione di codice viene arrestato a causa di un [EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) eventi per questo frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
