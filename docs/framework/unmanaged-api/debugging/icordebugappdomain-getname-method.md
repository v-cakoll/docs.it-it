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
ms.openlocfilehash: 535d94688d02a7315529d17fae555fba457bbb86
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737879"
---
# <a name="icordebugappdomaingetname-method"></a>Metodo ICorDebugAppDomain::GetName
Ottiene il nome del dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cchName`  
 [in] Dimensione della matrice `szName`. Impostare questo valore su zero per il metodo put in modalità query.  
  
 `pcchName`  
 [out] Un puntatore alla dimensione del nome o il numero di caratteri effettivamente restituiti nella `szName`. In modalità query, questo valore consente al chiamante di sapere come un buffer di grandi dimensioni da allocare per il nome.  
  
 `szName`  
 [out] Matrice che archivia il nome del dominio dell'applicazione.  
  
## <a name="remarks"></a>Note  
 Un debugger chiama il `GetName` metodo una volta per ottenere la dimensione del buffer necessaria per il nome. Il debugger esegue l'allocazione di buffer e quindi chiama il metodo di una seconda volta per riempire il buffer. La prima chiamata, per ottenere le dimensioni del nome, è detto *modalità query*.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
