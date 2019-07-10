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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29766636cd151744d25cf66deb60cd2e066e1b32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775786"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>Enumerazione CorSymSearchPolicyAttributes
Specifica i criteri da utilizzare quando si esegue una ricerca di un lettore di simboli. Queste costanti vengono utilizzate per la [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) e [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) metodi.  
  
> [!IMPORTANT]
>  È un rischio per la sicurezza per aprire un file di programma (PDB) del database da un'origine non attendibile.  
  
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
  
|Member|Descrizione|  
|------------|-----------------|  
|`AllowRegistryAccess`|Esegue una query il Registro di sistema per i percorsi di ricerca simbolo.|  
|`AllowSymbolServerAccess`|Accede a un server di simboli.|  
|`AllowOriginalPathAccess`|Cerca nel percorso specificato nella directory di Debug.|  
|`AllowReferencePathAccess`|Cerca il file PDB nel punto in cui il file .exe è.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
