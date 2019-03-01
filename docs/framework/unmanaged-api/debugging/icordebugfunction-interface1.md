---
title: Interfaccia ICorDebugFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c2a4dc823768b722e9069c411be787a66989b2a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977110"
---
# <a name="icordebugfunction-interface"></a>Interfaccia ICorDebugFunction

Rappresenta una funzione o un metodo gestito.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|Crea un punto di interruzione all'inizio di questa funzione.|  
|[Metodo GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|Ottiene un oggetto ICorDebugClass che rappresenta la classe di di che questa funzione è un membro.|  
|[Metodo GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|Ottiene il numero di versione dell'ultima modifica apportata a questa funzione.|  
|[Metodo GetILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|Ottiene il codice Microsoft intermediate language (MSIL) per questa funzione.|  
|[Metodo GetLocalVarSigToken](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|Ottiene i metadati del token per la firma della variabile locale della funzione che è rappresentata da questo `ICorDebugFunction` istanza.|  
|[Metodo GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Ottiene il modulo in cui questa funzione è definita.|  
|[Metodo GetNativeCode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|Ottiene il codice nativo per questa funzione.|  
|[Metodo GetToken](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|Ottiene i metadati del token per questa funzione.|  
  
## <a name="remarks"></a>Note  
 Il `ICorDebugFunction` interfaccia non rappresenta una funzione con parametri di tipo generico. Ad esempio, un' `ICorDebugFunction` istanza rappresenterebbe `Func<T>` ma non `Func<string>`. Chiamare [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) per recuperare i parametri di tipo generico.  
  
 La relazione tra i token di metadati del metodo `mdMethodDef`e un metodo `ICorDebugFunction` oggetto è dipende dal fatto che modifica e continuazione è consentita nella funzione:  
  
-   Se Modifica e continuazione non è consentito nella funzione, esiste una relazione uno a uno tra i `ICorDebugFunction` oggetto e il `mdMethodDef` token. Vale a dire, la funzione di disponibile `ICorDebugFunction` oggetto e l'altra `mdMethodDef` token.  
  
-   Se Modifica e continuazione è consentito nella funzione, esiste una relazione molti-a-uno tra i `ICorDebugFunction` oggetto e il `mdMethodDef` token. Vale a dire, la funzione può avere molte istanze di `ICorDebugFunction`, uno per ogni versione della funzione, ma una sola `mdMethodDef` token.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:**  CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
