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
ms.openlocfilehash: 63719d0c6e13768e9dc7ed80e52e2a293e32a8a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449352"
---
# <a name="getalinkmessagedll-function"></a>Funzione GetALinkMessageDll
Trova e carica la DLL del messaggio. Restituisce 0 se non è stato possibile trovare o caricare la DLL del messaggio. La DLL del messaggio deve trovarsi in una sottodirectory il cui nome è un ID lingua o nella directory corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ALink. h  
  
 **Libreria**: ALink. dll  
  
## <a name="see-also"></a>Vedere anche

- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
