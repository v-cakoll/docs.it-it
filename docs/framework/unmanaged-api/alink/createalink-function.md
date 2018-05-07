---
title: Funzione CreateALink
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e29c9c246649229900beba2fcc9ab482071ae46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="createalink-function"></a>Funzione CreateALink
Crea un'istanza dell'Assembly Linker e imposta un puntatore a interfaccia specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|`riid`|Il nome fisico di una delle interfacce di Assembly Linker.|  
|`ppInterface`|Il percorso che al termine dell'esecuzione contiene un puntatore per il `riid` interfaccia.|  
  
## <a name="requirements"></a>Requisiti  
 **Libreria**: ALink. dll  
  
## <a name="see-also"></a>Vedere anche  
 [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
