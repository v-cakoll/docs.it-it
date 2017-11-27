---
title: Metodo ICorDebugILFrame::EnumerateArguments
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.EnumerateArguments
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf345f3fa684b57a33e3452916535b1cd7db3c8b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframeenumeratearguments-method"></a>Metodo ICorDebugILFrame::EnumerateArguments
Ottiene un enumeratore per gli argomenti nel frame.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppValueEnum`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugValueEnum che è l'enumeratore per gli argomenti nel frame.  
  
## <a name="remarks"></a>Note  
 `EnumerateArguments`Ottiene un enumeratore in grado di elencare gli argomenti disponibili nel frame di chiamata che è rappresentato dall'oggetto ICorDebugILFrame. L'elenco includerà gli argomenti devono essere [vararg](/cpp/windows/vararg) (ovvero, un numero variabile di argomenti) e argomenti che non sono `vararg`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
