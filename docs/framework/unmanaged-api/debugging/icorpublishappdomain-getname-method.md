---
title: Metodo ICorPublishAppDomain::GetName
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e44ee4a1a2cdd40d93c487ccb41316f729038a5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469144"
---
# <a name="icorpublishappdomaingetname-method"></a>Metodo ICorPublishAppDomain::GetName
Ottiene il nome del dominio dell'applicazione che è rappresentato da questo [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cchName`  
 [in] Dimensione della matrice `szName`.  
  
 `pcchName`  
 [out] Un puntatore al numero di caratteri "wide", incluso il carattere null, restituito nel `szName` matrice.  
  
 `szName`  
 [out] Matrice in cui archiviare il nome.  
  
## <a name="remarks"></a>Note  
 Se `szName` è diverso da null, il `GetName` metodo copia fino a `cchName` caratteri (incluso il carattere di terminazione null) in `szName`. Se non null viene restituito in `pcchName`, il numero effettivo di caratteri del nome (incluso il carattere di terminazione null) verrà archiviato nel `szName` matrice.  
  
 Il `GetName` metodo restituisce un HRESULT S_OK indipendentemente dal numero di caratteri sono stato copiato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub.idl, CorPub.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
