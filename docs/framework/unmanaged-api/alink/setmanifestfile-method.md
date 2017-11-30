---
title: Metodo SetManifestFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink3.SetManifestFile
api_location: alink.dll
api_type: COM
f1_keywords: SetManifestFile
helpviewer_keywords: SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 807452326193d193f3bc603ebc7b74a5a0f1c281
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 [ALink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
