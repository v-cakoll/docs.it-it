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
ms.openlocfilehash: e95f96847c6e069758362fb6febc28dc31911bc9
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396289"
---
# <a name="icorpublishappdomaingetname-method"></a>Metodo ICorPublishAppDomain::GetName
Ottiene il nome del dominio dell'applicazione rappresentato da questo [ICorPublishAppDomain](icorpublishappdomain-interface.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 out Puntatore al numero di caratteri wide, incluso il carattere null, restituito nella `szName` matrice.  
  
 `szName`  
 out Matrice in cui archiviare il nome.  
  
## <a name="remarks"></a>Commenti  
 Se `szName` è diverso da null, il `GetName` metodo copia fino a `cchName` caratteri (incluso il terminatore null) in `szName` . Se viene restituito un valore non null in `pcchName` , il numero effettivo di caratteri nel nome, incluso il terminatore null, viene archiviato nella `szName` matrice.  
  
 Il `GetName` metodo restituisce un S_OK HRESULT indipendentemente dal numero di caratteri copiati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorPublishAppDomain](icorpublishappdomain-interface.md)
