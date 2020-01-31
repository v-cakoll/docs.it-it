---
title: Metodo ICorDebugCode::GetILToNativeMapping
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
ms.openlocfilehash: 98709c0ce7469db1d0365d71e10d2d021cd3b3f0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777882"
---
# <a name="icordebugcodegetiltonativemapping-method"></a>Metodo ICorDebugCode::GetILToNativeMapping
Ottiene una matrice di istanze "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da offset MSIL (Microsoft Intermediate Language) a offset nativi.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cMap`  
 [in] Dimensione della matrice `map`.  
  
 `pcMap`  
 out Puntatore al numero effettivo di elementi restituiti nella matrice `map`.  
  
 `map`  
 out Matrice di strutture di `COR_DEBUG_IL_TO_NATIVE_MAP`, ciascuna delle quali rappresenta un mapping da un offset MSIL a un offset nativo.  
  
 Non esiste alcun ordinamento per la matrice di elementi restituiti.  
  
## <a name="remarks"></a>Note  
 Il metodo `GetILToNativeMapping` restituisce risultati significativi solo se l'istanza "ICorDebugCode" rappresenta il codice nativo compilato con JIT dal codice MSIL.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugCode](icordebugcode-interface1.md)
