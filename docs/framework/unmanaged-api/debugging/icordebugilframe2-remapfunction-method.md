---
title: Metodo ICorDebugILFrame2::RemapFunction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2.RemapFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9fed4759576d1b6d2fec1a5e9c1e36019e5944c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe2remapfunction-method"></a>Metodo ICorDebugILFrame2::RemapFunction
Riesegue il mapping di una funzione modificata specificando il nuovo offset di Microsoft intermediate language (MSIL)  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `newILOffset`  
 [in] Nuovo offset MSIL dello stack frame in corrispondenza del quale deve essere posizionato il puntatore all'istruzione. Questo valore deve essere un punto di sequenza.  
  
 È responsabilità del chiamante per garantire la validità di questo valore. Ad esempio, l'offset MSIL non è valido se è presente all'esterno dei limiti della funzione.  
  
## <a name="remarks"></a>Note  
 Funzione di una cornice è stata modificata, il debugger può chiamare il `RemapFunction` metodo per passare alla versione più recente della funzione del frame in modo da poter essere eseguito. L'esecuzione del codice inizierà in corrispondenza dell'offset MSIL specificato.  
  
> [!NOTE]
>  La chiamata `RemapFunction`, ad esempio la chiamata [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), invaliderà immediatamente tutte le interfacce di debug che relative alla generazione di una traccia dello stack per il thread. Tali interfacce includono [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame e ICorDebugNativeFrame.  
  
 Il `RemapFunction` metodo può essere chiamato solo nel contesto del frame corrente e solo in uno dei seguenti casi:  
  
-   Dopo la ricezione di un [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback che non è ancora continuata l'esecuzione.  
  
-   Durante l'esecuzione di codice viene interrotta a causa di un [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) evento per questo frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
