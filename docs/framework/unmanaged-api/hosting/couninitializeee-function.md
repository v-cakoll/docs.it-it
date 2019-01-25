---
title: Funzione CoUninitializeEE
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
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
ms.openlocfilehash: ef5faff6682ed6c043e81212f2cb27d4cfbd813d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601857"
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
