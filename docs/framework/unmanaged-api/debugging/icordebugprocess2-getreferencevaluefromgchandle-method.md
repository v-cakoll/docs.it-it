---
title: Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f38f9a3ebd88e0a5abb7a6bc8cb4026dc7d0f068
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736942"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle
Ottiene un puntatore di riferimento all'oggetto gestito specificato dotato di gestire una garbage collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `handle`  
 [in] Puntatore a un oggetto gestito che presenta un handle di garbage collection. Questo valore è un <xref:System.IntPtr> dell'oggetto e possono essere recuperati dal <xref:System.Runtime.InteropServices.GCHandle> per l'oggetto gestito.  
  
 `pOutValue`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugReferenceValue che rappresenta un riferimento all'oggetto gestito specificato.  
  
## <a name="remarks"></a>Note  
 Non confondere il valore restituito di riferimento con un valore di riferimento di garbage collection.  
  
 Il riferimento restituito si comporta come un normale riferimento. Viene disabilitato quando l'esecuzione di codice continua dopo un punto di interruzione. La durata dell'oggetto di destinazione non è interessata dalla durata del valore di riferimento.  
  
> [!NOTE]
>  Il `GetReferenceValueFromGCHandle` metodo non convalida l'handle. Pertanto, il `GetReferenceValueFromGCHandle` metodo può potenzialmente danneggiare il debugger sia il codice in fase di debug se viene passato un handle non valido.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
