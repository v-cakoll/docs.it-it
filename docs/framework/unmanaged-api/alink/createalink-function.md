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
ms.openlocfilehash: b494b8b776f4cb0eb534233c5a03ab2d34a698ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115622"
---
# <a name="createalink-function"></a>Funzione CreateALink
Crea un'istanza dell'Assembly Linker e imposta un puntatore all'interfaccia specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|`riid`|Il nome fisico di una delle interfacce Assembly Linker.|  
|`ppInterface`|Il percorso che, al termine dell'esecuzione, contiene un puntatore al `riid` interfaccia.|  
  
## <a name="requirements"></a>Requisiti  
 **Libreria**: ALink. dll  
  
## <a name="see-also"></a>Vedere anche

- [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
