---
title: Funzione CertFreeAuthenticodeSignerInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
ms.openlocfilehash: a233e0b8d17b9ee61b1991086f794c9fb20f89e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099818"
---
# <a name="certfreeauthenticodesignerinfo-function"></a>Funzione CertFreeAuthenticodeSignerInfo
Libera le risorse allocate per la struttura [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a>Parametri  
 `pSignerInfo`  
 [in, out] Informazioni del firmatario da rilasciare. Vedere la struttura [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se la funzione ha esito positivo. In caso contrario, verrà restituito un codice di errore.  
  
## <a name="see-also"></a>Vedere anche

- [Authenticode](index.md)
