---
title: Funzione CoUninitializeEE
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b3712b4cb66facc105a03d7bfad235f09339056
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193005"
---
# <a name="couninitializeee-function"></a>Funzione CoUninitializeEE
`CoUninitializeEE` è obsoleto e non fornisce alcuna funzionalità.  
  
## <a name="syntax"></a>Sintassi  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Note  
 Il motore di esecuzione di common language runtime non può essere scaricato da un processo. Per arrestare il motore, chiamare [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
