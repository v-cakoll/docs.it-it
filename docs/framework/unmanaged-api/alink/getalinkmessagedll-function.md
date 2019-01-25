---
title: Funzione GetALinkMessageDll
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 632f19e0ead57d5508265fece578bb22f18ba54a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722725"
---
# <a name="getalinkmessagedll-function"></a>Funzione GetALinkMessageDll
Trova e carica la DLL dei messaggi. Restituisce 0 se non è stato possibile che si trova o caricare la DLL dei messaggi. La DLL dei messaggi deve essere in una sottodirectory il cui nome è un ID di lingua, o nella directory corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** alink.h  
  
 **Libreria**: ALink. dll  
  
## <a name="see-also"></a>Vedere anche
- [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
