---
title: Metodo ICorDebugFunction::GetILCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f34a2fe2bb1f92e75f77c086b03776ec59495600
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995748"
---
# <a name="icordebugfunctiongetilcode-method"></a>Metodo ICorDebugFunction::GetILCode
Ottiene l'istanza ICorDebugCode che rappresenta il codice Microsoft intermediate language (MSIL) associato all'oggetto ICorDebugFunction.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppCode`  
 [out] Un puntatore al `ICorDebugCode` istanza oppure null se la funzione non è stata compilata in MSIL.  
  
## <a name="remarks"></a>Note  
 Se Modifica e continuazione è stata consentita su questa funzione, il `GetILCode` metodo verrà visualizzato il codice MSIL corrispondente alla versione modificata della funzione del codice in common language runtime (CLR).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
