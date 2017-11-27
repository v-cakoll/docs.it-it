---
title: Funzione IsFrameworkAssembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IsFrameworkAssembly
api_location: fusion.dll
api_type: COM
f1_keywords: IsFrameworkAssembly
helpviewer_keywords: IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 216a7221550cb6345b29b5ed9e45b13ce40eadf4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isframeworkassembly-function"></a>Funzione IsFrameworkAssembly
Ottiene un valore che indica se l'assembly specificato è stato gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a>Parametri  
 `pwzAssemblyReference`  
 [in] Il nome dell'assembly da controllare.  
  
 `pbIsFrameworkAssembly`  
 [out] Valore booleano che indica se l'assembly è stato gestito.  
  
 `pwzFrameworkAssemblyIdentity`  
 [in] Una stringa in formato non canonico che contiene l'identità univoca dell'assembly.  
  
 `pccSize`  
 [in] Le dimensioni di `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Note  
 Il `pwzAssemblyReference` parametro è un puntatore a una stringa di caratteri che contiene il nome di un assembly.  
  
 Se l'assembly fa parte di .NET Framework, il `pbIsFrameworkAssembly` parametro conterrà un valore booleano `true`.  
  
 Se l'assembly denominato non fa parte di .NET Framework o se il `pwzAssemblyReference` parametro non corrisponde a un assembly, `pbIsFrameworkAssembly` conterrà un valore booleano `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
