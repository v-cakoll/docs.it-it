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
ms.openlocfilehash: ae65c59efe1d925b5e058e8664d1e093fdfec875
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917198"
---
# <a name="icordebugfunction-interface"></a>Interfaccia ICorDebugFunction

Rappresenta una funzione o un metodo gestito.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|Crea un punto di interruzione all'inizio di questa funzione.|  
|[Metodo GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|Ottiene un oggetto ICorDebugClass che rappresenta la classe di cui questa funzione è membro.|  
|[Metodo GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|Ottiene il numero di versione dell'Ultima modifica apportata a questa funzione.|  
|[Metodo GetILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|Ottiene il codice MSIL (Microsoft Intermediate Language) per questa funzione.|  
|[Metodo GetLocalVarSigToken](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|Ottiene il token di metadati per la firma della variabile locale della funzione rappresentata da questa `ICorDebugFunction` istanza.|  
|[Metodo GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Ottiene il modulo in cui è definita questa funzione.|  
|[Metodo GetNativeCode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|Ottiene il codice nativo per questa funzione.|  
|[Metodo GetToken](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|Ottiene il token di metadati per questa funzione.|  
  
## <a name="remarks"></a>Note  
 L' `ICorDebugFunction` interfaccia non rappresenta una funzione con parametri di tipo generico. Un' `ICorDebugFunction` `Func<string>` istanza`Func<T>` , ad esempio, rappresenterebbe, ma non. Chiamare [ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) per ottenere i parametri di tipo generico.  
  
 La relazione tra il token di metadati di un `mdMethodDef`metodo, e l'oggetto `ICorDebugFunction` di un metodo dipende dalla possibilità di modificare e continuare nella funzione:  
  
- Se la funzione modifica e continuazione non è consentita, esiste una relazione uno-a-uno `ICorDebugFunction` tra l'oggetto `mdMethodDef` e il token. Ovvero, la funzione dispone di un `ICorDebugFunction` oggetto e di `mdMethodDef` un token.  
  
- Se la funzione modifica e continuazione è consentita, esiste una relazione molti-a-uno `ICorDebugFunction` tra l'oggetto `mdMethodDef` e il token. Ovvero, la funzione può avere molte istanze di `ICorDebugFunction`, una per ogni versione della funzione, ma solo un `mdMethodDef` token.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria**  CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
