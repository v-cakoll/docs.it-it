---
title: Funzione IsFrameworkAssembly
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
ms.openlocfilehash: e30b6f2d2254d2d107c4c82a2c5664850ce6ec23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123062"
---
# <a name="isframeworkassembly-function"></a>Funzione IsFrameworkAssembly
Ottiene un valore che indica se l'assembly specificato è gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzAssemblyReference`  
 in Nome dell'assembly da verificare.  
  
 `pbIsFrameworkAssembly`  
 out Valore booleano che indica se l'assembly è gestito.  
  
 `pwzFrameworkAssemblyIdentity`  
 in Stringa non canonica che contiene l'identità univoca dell'assembly.  
  
 `pccSize`  
 [in] Le dimensioni di `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Note  
 Il parametro `pwzAssemblyReference` è un puntatore a una stringa di caratteri che contiene il nome di un assembly.  
  
 Se questo assembly fa parte dell'.NET Framework, il parametro `pbIsFrameworkAssembly` conterrà un valore booleano di `true`.  
  
 Se l'assembly denominato non fa parte dell'.NET Framework o se il parametro `pwzAssemblyReference` non specifica un nome di assembly, `pbIsFrameworkAssembly` conterrà un valore booleano di `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
