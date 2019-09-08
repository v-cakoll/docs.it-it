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
ms.openlocfilehash: 323e53c45a26d5703548ebe9863978f6d3929f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787470"
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
