---
title: Metodo ICorDebugILFrame::EnumerateArguments
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: 3945b1dea62dc0616d669356faf60f0d09cfb084
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210306"
---
# <a name="icordebugilframeenumeratearguments-method"></a>Metodo ICorDebugILFrame::EnumerateArguments
Ottiene un enumeratore per gli argomenti in questo frame.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppValueEnum`  
 out Puntatore all'indirizzo di un oggetto ICorDebugValueEnum che rappresenta l'enumeratore per gli argomenti in questo frame.  
  
## <a name="remarks"></a>Osservazioni  
 `EnumerateArguments`Ottiene un enumeratore in grado di elencare gli argomenti disponibili nel frame di chiamata rappresentato da questo oggetto ICorDebugILFrame. L'elenco includerà gli argomenti [vararg](/cpp/windows/vararg) (ovvero un numero variabile di argomenti) e gli argomenti che non lo sono `vararg` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
