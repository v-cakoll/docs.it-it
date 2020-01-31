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
ms.openlocfilehash: 4325d61d12a66b17f88e5e368cbbc7806d0a3ec5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790711"
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
 out Puntatore al numero di caratteri wide, incluso il carattere null, restituito nella matrice `szName`.  
  
 `szName`  
 out Matrice in cui archiviare il nome.  
  
## <a name="remarks"></a>Note  
 Se `szName` è diverso da null, il metodo `GetName` copia fino a `cchName` caratteri, incluso il terminatore null, in `szName`. Se viene restituito un valore non null in `pcchName`, il numero effettivo di caratteri nel nome, incluso il terminatore null, viene archiviato nella matrice di `szName`.  
  
 Il metodo `GetName` restituisce una S_OK HRESULT indipendentemente dal numero di caratteri copiati.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorPublishAppDomain](icorpublishappdomain-interface.md)
