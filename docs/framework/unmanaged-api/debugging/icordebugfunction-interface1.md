---
title: ICorDebugFunction Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction
helpviewer_keywords: ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327ef9f74e94e3b1b20e78eb6a833038b5bfe16d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction-interface1"></a>ICorDebugFunction Interface1
Rappresenta una funzione o un metodo gestito.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CreateBreakpoint (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|Crea un punto di interruzione all'inizio di questa funzione.|  
|[GetClass (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|Ottiene un oggetto ICorDebugClass che rappresenta la classe di che questa funzione è membro.|  
|[GetCurrentVersionNumber (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|Ottiene il numero di versione dell'ultima modifica apportata a questa funzione.|  
|[GetILCode (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|Ottiene il codice di Microsoft intermediate language (MSIL) per questa funzione.|  
|[Metodo GetLocalVarSigToken](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|Ottiene i metadati di token per la firma di variabile locale della funzione che è rappresentata da questo `ICorDebugFunction` istanza.|  
|[GetModule (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Ottiene il modulo in cui questa funzione è definita.|  
|[GetNativeCode (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|Ottiene il codice nativo per questa funzione.|  
|[GetToken (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|Ottiene i metadati del token per questa funzione.|  
  
## <a name="remarks"></a>Note  
 Il `ICorDebugFunction` interfaccia non rappresenta una funzione con parametri di tipo generico. Ad esempio, un `ICorDebugFunction` istanza rappresenterebbero `Func<T>` ma non `Func<string>`. Chiamare [ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) per recuperare i parametri di tipo generico.  
  
 La relazione tra il token di metadati di un metodo `mdMethodDef`e un metodo `ICorDebugFunction` dipende se Modifica e continuazione è consentito nella funzione:  
  
-   Se non è consentita, un tipo di relazione esiste tra la `ICorDebugFunction` oggetto e `mdMethodDef` token. Ovvero, la funzione ha un `ICorDebugFunction` oggetto e una `mdMethodDef` token.  
  
-   Se Modifica e continuazione è consentito nella funzione, è presente una relazione molti-a-uno tra il `ICorDebugFunction` oggetto e `mdMethodDef` token. Ovvero, la funzione può avere molte istanze di `ICorDebugFunction`, uno per ogni versione della funzione, ma solo uno `mdMethodDef` token.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
