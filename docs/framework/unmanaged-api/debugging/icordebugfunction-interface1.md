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
ms.openlocfilehash: 6b7b6969c1f207decbf47217e98b7fee3aa9ce54
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213241"
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
|[Metodo GetLocalVarSigToken](icordebugfunction-getlocalvarsigtoken-method.md)|Ottiene il token di metadati per la firma della variabile locale della funzione rappresentata da questa `ICorDebugFunction` istanza.|  
|[Metodo GetModule](icordebugfunction-getmodule-method.md)|Ottiene il modulo in cui è definita questa funzione.|  
|[Metodo GetNativeCode](icordebugfunction-getnativecode-method.md)|Ottiene il codice nativo per questa funzione.|  
|[Metodo GetToken](icordebugfunction-gettoken-method.md)|Ottiene il token di metadati per questa funzione.|  
  
## <a name="remarks"></a>Osservazioni  
 L' `ICorDebugFunction` interfaccia non rappresenta una funzione con parametri di tipo generico. Un'istanza, ad esempio, rappresenterebbe, `ICorDebugFunction` `Func<T>` ma non `Func<string>` . Chiamare [ICorDebugILFrame2:: EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md) per ottenere i parametri di tipo generico.  
  
 La relazione tra il token di metadati di un metodo, `mdMethodDef` e l'oggetto di un metodo dipende dalla possibilità `ICorDebugFunction` di modificare e continuare nella funzione:  
  
- Se la funzione modifica e continuazione non è consentita, esiste una relazione uno-a-uno tra l' `ICorDebugFunction` oggetto e il `mdMethodDef` token. Ovvero, la funzione dispone di un `ICorDebugFunction` oggetto e di un `mdMethodDef` token.  
  
- Se la funzione modifica e continuazione è consentita, esiste una relazione molti-a-uno tra l' `ICorDebugFunction` oggetto e il `mdMethodDef` token. Ovvero, la funzione può avere molte istanze di `ICorDebugFunction` , una per ogni versione della funzione, ma solo un `mdMethodDef` token.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:**  CorGuids. lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
