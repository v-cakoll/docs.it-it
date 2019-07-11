---
title: Metodo ISymUnmanagedENCUpdate::UpdateMethodLines
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54789003f7454a65449e55ea4d990edd672d9c1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774691"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a>Metodo ISymUnmanagedENCUpdate::UpdateMethodLines
Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono spostati in modo indipendente. Valore delta di ogni istruzione è consentito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a>Parametri  
 `mdMethodToken`  
 [in] I metadati del token del metodo.  
  
 `pDeltas`  
 [in] Matrice di `INT32` valori che indica i valori differenziali per ogni punto di sequenza nel metodo.  
  
 `cDeltas`  
 [in] Oggetto `ULONG` che contiene la dimensione del `pDeltas` parametro.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedENCUpdate](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
