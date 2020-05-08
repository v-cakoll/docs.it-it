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
ms.openlocfilehash: 3db37576f5da7b26e7bd9d3343f8bb8b97f2ba82
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895238"
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
 [in] Dimensione della matrice `szName`. Impostare questo valore su zero per inserire questo metodo in modalità query.  
  
 `pcchName`  
 out Puntatore alla dimensione del nome o al numero di caratteri effettivamente restituiti in `szName`. In modalità query questo valore consente al chiamante di rilevare la dimensione di un buffer da allocare per il nome.  
  
 `szName`  
 out Matrice che archivia il nome del dominio dell'applicazione.  
  
## <a name="remarks"></a>Osservazioni  
 Un debugger chiama il `GetName` metodo una volta per ottenere la dimensione di un buffer necessario per il nome. Il debugger alloca il buffer e quindi chiama il metodo una seconda volta per riempire il buffer. La prima chiamata, per ottenere le dimensioni del nome, viene definita *modalità query*.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
