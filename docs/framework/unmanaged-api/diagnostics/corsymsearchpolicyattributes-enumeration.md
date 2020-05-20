---
title: Enumerazione CorSymSearchPolicyAttributes
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 0cd451854d4dbb3b243339efdc33d7dcd7860eb7
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420604"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>Enumerazione CorSymSearchPolicyAttributes
Specifica i criteri da utilizzare durante la ricerca di un lettore di simboli. Queste costanti vengono usate dai metodi [ISymUnmanagedBinder2:: GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) e [ISymUnmanagedBinder3:: GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) .  
  
> [!IMPORTANT]
> L'apertura di un file di database di programma (PDB) da un'origine non attendibile costituisce un rischio per la sicurezza.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`AllowRegistryAccess`|Esegue una query nel registro di sistema per individuare i percorsi dei simboli.|  
|`AllowSymbolServerAccess`|Accede a un server di simboli.|  
|`AllowOriginalPathAccess`|Cerca nel percorso specificato nella directory di debug.|  
|`AllowReferencePathAccess`|Cerca il PDB nel punto in cui si trova il file exe.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-enumerations.md)
