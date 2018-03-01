---
title: Metodo SetManifestFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cf48153454fbb2c24dc3f1cfe1f82deefa4ee723
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="setmanifestfile-method"></a>Metodo SetManifestFile
Consente di specificare o reimpostare il file manifesto che il linker utilizza quando viene creato l'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametri  
 `pszFile`  
  
 Il nome del file manifesto il cui contenuto è inserito nel blob di risorse Win32.  
  
## <a name="return-value"></a>Valore restituito  
 Se il metodo ha esito positivo, restituisce S_OK.  
  
## <a name="remarks"></a>Note  
 Chiamare questo metodo prima di richiedere la Win32ResBlob. Il valore di `pszFile` parametro è il nome del file manifesto il cui contenuto viene letto e inserito nelle risorse Win32 con l'ID di RT_MANIFEST. Quando viene chiamato con un parametro null, viene cancellato qualsiasi manifesti letti in precedenza. Ciò consente di reimpostare lo stato del linker al momento dell'inizializzazione.  
  
## <a name="requirements"></a>Requisiti  
 Richiede aLink.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IALink3](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)  
 [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
