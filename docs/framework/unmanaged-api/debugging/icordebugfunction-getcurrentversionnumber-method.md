---
title: Metodo ICorDebugFunction::GetCurrentVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
ms.openlocfilehash: 5e080e9aa89816b24aa2eb1b6b1be823922e86fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794515"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a>Metodo ICorDebugFunction::GetCurrentVersionNumber
Ottiene il numero di versione dell'Ultima modifica apportata alla funzione rappresentata da questo oggetto ICorDebugFunction.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pnCurrentVersion`  
 out Puntatore a un valore integer che rappresenta il numero di versione dell'Ultima modifica apportata a questa funzione.  
  
## <a name="remarks"></a>Note  
 Il numero di versione dell'Ultima modifica apportata a questa funzione potrebbe essere maggiore del numero di versione della funzione stessa. Usare il metodo [ICorDebugFunction2:: GetVersionNumber](icordebugfunction2-getversionnumber-method.md) o [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) per recuperare il numero di versione della funzione.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
