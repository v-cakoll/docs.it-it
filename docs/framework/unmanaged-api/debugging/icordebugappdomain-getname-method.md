---
title: Metodo ICorDebugAppDomain::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84f895e749fc8f2520dbce3caf9e6c11fda78a7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugappdomaingetname-method"></a>Metodo ICorDebugAppDomain::GetName
Ottiene il nome del dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cchName`  
 [in] Dimensione della matrice `szName`. Impostare questo valore su zero per inserire questo metodo in modalità query.  
  
 `pcchName`  
 [out] Un puntatore alla dimensione del nome o il numero di caratteri effettivamente restituiti nella `szName`. In modalità query, questo valore consente al chiamante di sapere come un buffer di grandi dimensioni da allocare per il nome.  
  
 `szName`  
 [out] Matrice che archivia il nome del dominio dell'applicazione.  
  
## <a name="remarks"></a>Note  
 Un debugger chiama il `GetName` metodo una volta per ottenere la dimensione del buffer necessaria per il nome. Il debugger consente di allocare il buffer e quindi chiama il metodo una seconda volta per riempire il buffer. La prima chiamata, per ottenere la dimensione del nome, è detto *modalità query*.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
