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
ms.openlocfilehash: 1d42292705dae03e9bf1a1555508dfb69cebde82
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132432"
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
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** dbgshim. h  
  
 **Libreria:** dbgshim. dll  
  
 **Versioni .NET Framework:** 3,5 SP1
