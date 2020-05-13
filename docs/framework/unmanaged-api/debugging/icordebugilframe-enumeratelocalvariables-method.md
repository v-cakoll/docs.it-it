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
ms.openlocfilehash: ad1a91e42f582ce96906da5cbf00ca89acb18499
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210293"
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
 [out] Puntatore all'indirizzo di un oggetto ICorDebugValueEnum che è l'enumeratore per le variabili locali nel frame.  
  
## <a name="remarks"></a>Osservazioni  
 `EnumerateLocalVariables`Ottiene un enumeratore in grado di elencare le variabili locali disponibili nel frame di chiamata rappresentato da questo oggetto ICorDebugILFrame. L'elenco potrebbe non includere tutte le variabili locali nella funzione in esecuzione, perché alcune potrebbero non essere attive.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
