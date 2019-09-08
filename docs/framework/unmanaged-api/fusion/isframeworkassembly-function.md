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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 269e3702c21532f377735ba6087abb1603dde4f7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796323"
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
 Il `pwzAssemblyReference` parametro è un puntatore a una stringa di caratteri che contiene il nome di un assembly.  
  
 Se questo assembly fa parte dell'.NET Framework, il `pbIsFrameworkAssembly` parametro conterrà un valore booleano pari `true`a.  
  
 Se l'assembly denominato non fa parte dell'.NET Framework o se il `pwzAssemblyReference` parametro non specifica un nome di assembly, `pbIsFrameworkAssembly` conterrà un valore booleano pari `false`a.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
