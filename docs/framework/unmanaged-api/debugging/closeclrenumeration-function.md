---
title: Funzione CloseCLREnumeration
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a05a779d4a56eb8f881da1824d5ffaa363b5a01
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274274"
---
# <a name="closeclrenumeration-function"></a>Funzione CloseCLREnumeration
Chiude tutti gli eventi di avvio di Common Language Runtime (CLR) validi presenti in una matrice di handle restituiti dalla [funzione EnumerateCLRs](enumerateclrs-function.md)e libera la memoria per le matrici del percorso di stringa e di handle.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pHandleArray`  
 in Puntatore alla matrice di handle dell'evento restituiti dalla [funzione EnumerateCLRs](enumerateclrs-function.md).  
  
 `pStringArray`  
 in Puntatore alla matrice di percorsi stringa CLR restituiti dalla [funzione EnumerateCLRs](enumerateclrs-function.md).  
  
 `dwArrayLength`  
 [in] DWORD contenente la dimensione (lunghezza) di `pHandleArray` o `pStringArray` (sono uguali).  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Gli handle aperti dalla [funzione EnumerateCLRs](enumerateclrs-function.md) vengono chiusi e la memoria allocata per l'handle e le matrici di stringhe viene liberata.  
  
 E_INVALIDARG  
 La lunghezza di `pHandleArray` non corrisponde alla lunghezza passata in `dwArrayLength`.  
  
 E_FAIL (o altri codici E_ restituiti)  
 La funzione non è in grado di liberare la memoria per `pHandleArray` ed `pStringArray`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** dbgshim. h  
  
 **Libreria:** dbgshim. dll  
  
 **Versioni .NET Framework:** 3.5 SP1
