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
ms.openlocfilehash: fa6297e926d53c02bb0d1af7b59b45b8ee152399
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616463"
---
# <a name="couninitializeee-function"></a>Funzione CoUninitializeEE
`CoUninitializeEE`è obsoleto e non fornisce alcuna funzionalità.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Osservazioni  
 Il motore di esecuzione Common Language Runtime non può essere scaricato da un processo. Per arrestare il motore di esecuzione, chiamare [CorExitProcess](corexitprocess-function.md).  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CoInitializeEE](coinitializeee-function.md)
- [Funzioni statiche globali dei metadati](../metadata/metadata-global-static-functions.md)
