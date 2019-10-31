---
title: Metodo ICorDebugILFrame::EnumerateLocalVariables
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: 07331a512dd513a94a7d8c3a8d8b0754d998b94b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131007"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a>Metodo ICorDebugILFrame::EnumerateLocalVariables
Ottiene un enumeratore per le variabili locali in questo frame.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppValueEnum`  
 out Puntatore all'indirizzo di un oggetto ICorDebugValueEnum che rappresenta l'enumeratore per le variabili locali in questo frame.  
  
## <a name="remarks"></a>Note  
 `EnumerateLocalVariables` ottiene un enumeratore in grado di elencare le variabili locali disponibili nel frame di chiamata rappresentato da questo oggetto ICorDebugILFrame. L'elenco potrebbe non includere tutte le variabili locali nella funzione in esecuzione, perché alcune potrebbero non essere attive.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
