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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49d7fb1de0b2ea63c1a766023b23acc42e027af8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995566"
---
# <a name="icordebugilframeenumeratearguments-method"></a>Metodo ICorDebugILFrame::EnumerateArguments
Ottiene un enumeratore per gli argomenti in questo frame.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppValueEnum`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugValueEnum che è l'enumeratore per gli argomenti in questo frame.  
  
## <a name="remarks"></a>Note  
 `EnumerateArguments` Ottiene un enumeratore in grado di elencare gli argomenti disponibili nel frame di chiamata che è rappresentato da questo ICorDebugILFrame oggetto. L'elenco includerà gli argomenti [vararg](/cpp/windows/vararg) (vale a dire, un numero variabile di argomenti), nonché di argomenti non `vararg`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
