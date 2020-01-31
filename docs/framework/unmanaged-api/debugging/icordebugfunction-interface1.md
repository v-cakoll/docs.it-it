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
ms.openlocfilehash: ba0e0b1b2bac785e28f41e09dda74841121a748d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794509"
---
# <a name="icordebugfunction-interface"></a>Interfaccia ICorDebugFunction

Rappresenta una funzione o un metodo gestito.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](icordebugfunction-createbreakpoint-method.md)|Crea un punto di interruzione all'inizio di questa funzione.|  
|[Metodo GetClass](icordebugfunction-getclass-method.md)|Ottiene un oggetto ICorDebugClass che rappresenta la classe di cui questa funzione è membro.|  
|[Metodo GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md)|Ottiene il numero di versione dell'Ultima modifica apportata a questa funzione.|  
|[Metodo GetILCode](icordebugfunction-getilcode-method.md)|Ottiene il codice MSIL (Microsoft Intermediate Language) per questa funzione.|  
|[Metodo GetLocalVarSigToken](icordebugfunction-getlocalvarsigtoken-method.md)|Ottiene il token di metadati per la firma della variabile locale della funzione rappresentata da questa istanza di `ICorDebugFunction`.|  
|[Metodo GetModule](icordebugfunction-getmodule-method.md)|Ottiene il modulo in cui è definita questa funzione.|  
|[Metodo GetNativeCode](icordebugfunction-getnativecode-method.md)|Ottiene il codice nativo per questa funzione.|  
|[Metodo GetToken](icordebugfunction-gettoken-method.md)|Ottiene il token di metadati per questa funzione.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugFunction` non rappresenta una funzione con parametri di tipo generico. Ad esempio, un'istanza di `ICorDebugFunction` rappresenterebbe `Func<T>` ma non `Func<string>`. Chiamare [ICorDebugILFrame2:: EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md) per ottenere i parametri di tipo generico.  
  
 La relazione tra il token di metadati di un metodo, `mdMethodDef`e l'oggetto `ICorDebugFunction` di un metodo dipende dalla possibilità di modificare e continuare per la funzione:  
  
- Se la funzione modifica e continuazione non è consentita, esiste una relazione uno-a-uno tra l'oggetto `ICorDebugFunction` e il token di `mdMethodDef`. Ovvero, la funzione ha un oggetto `ICorDebugFunction` e un token di `mdMethodDef`.  
  
- Se la funzione modifica e continuazione è consentita, esiste una relazione molti-a-uno tra l'oggetto `ICorDebugFunction` e il token di `mdMethodDef`. Ovvero è possibile che la funzione disponga di molte istanze di `ICorDebugFunction`, una per ogni versione della funzione, ma un solo token di `mdMethodDef`.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:**  CorGuids. lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
