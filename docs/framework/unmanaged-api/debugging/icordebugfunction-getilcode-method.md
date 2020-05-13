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
ms.openlocfilehash: 8c7be2d48a30a9f649c6d86e4edbc10085195b68
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213621"
---
# <a name="icordebugfunctiongetilcode-method"></a>Metodo ICorDebugFunction::GetILCode
Ottiene l'istanza di ICorDebugCode che rappresenta il codice MSIL (Microsoft Intermediate Language) associato a questo oggetto ICorDebugFunction.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppCode`  
 out Puntatore all' `ICorDebugCode` istanza o null se la funzione non è stata compilata in MSIL.  
  
## <a name="remarks"></a>Osservazioni  
 Se in questa funzione è consentita l'autorizzazione Modifica e continuazione, il `GetILCode` metodo otterrà il codice MSIL corrispondente alla versione modificata del codice di questa funzione nel Common Language Runtime (CLR).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
