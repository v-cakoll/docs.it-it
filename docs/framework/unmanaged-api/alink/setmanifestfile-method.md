---
title: Metodo SetManifestFile
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f22927b388a62ee6025c987bb107b2dfd51da0e3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488994"
---
# <a name="setmanifestfile-method"></a>Metodo SetManifestFile
Consente di specificare o ripristinare il file manifesto che il linker Usa durante la creazione dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `pszFile`  
  
 Il nome del file manifesto viene inserito il cui contenuto nell'oggetto blob di risorse Win32.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="remarks"></a>Note  
 Chiamare questo metodo prima di richiedere il Win32ResBlob. Il valore della `pszFile` parametro è il nome del file manifesto il cui contenuto viene letto e inserire nelle risorse Win32 con l'ID di RT_MANIFEST. Quando viene chiamato con un parametro null, viene cancellata manifesto letta in precedenza. Ciò consente di reimpostare lo stato del linker al momento dell'inizializzazione.  
  
## <a name="requirements"></a>Requisiti  
 Richiede aLink.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IALink3](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
