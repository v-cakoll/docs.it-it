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
ms.openlocfilehash: b293c30060107d18c6b609efc82c4128a73cc1c7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787204"
---
# <a name="setmanifestfile-method"></a>Metodo SetManifestFile
Consente di specificare o reimpostare il file manifesto utilizzato dal linker durante la creazione dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `pszFile`  
  
 Nome del file manifesto il cui contenuto viene inserito nel BLOB di risorse Win32.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="remarks"></a>Note  
 Chiamare questo oggetto prima di richiedere l'Win32ResBlob. Il valore del `pszFile` parametro è il nome del file manifesto il cui contenuto viene letto e inserito nelle risorse Win32 con ID RT_MANIFEST. Quando viene chiamato usando un parametro NULL, qualsiasi manifesto precedentemente letto viene cancellato. In questo modo, è possibile reimpostare lo stato del linker su quello del tempo di inizializzazione.  
  
## <a name="requirements"></a>Requisiti  
 Richiede aLink. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink3](ialink3-interface.md)
- [Alink (API)](index.md)
- [Interfaccia IALink](ialink-interface.md)
- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
