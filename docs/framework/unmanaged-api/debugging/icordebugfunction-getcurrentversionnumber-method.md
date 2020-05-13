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
ms.openlocfilehash: b47580022b98ea02584a94b3f74b3fd1c276f297
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212906"
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
  
## <a name="remarks"></a>Osservazioni  
 Il numero di versione dell'Ultima modifica apportata a questa funzione potrebbe essere maggiore del numero di versione della funzione stessa. Usare il metodo [ICorDebugFunction2:: GetVersionNumber](icordebugfunction2-getversionnumber-method.md) o [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) per recuperare il numero di versione della funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
