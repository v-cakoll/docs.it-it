---
title: Struttura COR_NATIVE_LINK
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
ms.openlocfilehash: a11b7d5939c4c20504b1ff3dfb4613f85bca0db4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007975"
---
# <a name="cor_native_link-structure"></a>Struttura COR_NATIVE_LINK
Contiene informazioni usate per collegare il codice nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`m_linkType`|Tipo da collegare nel codice nativo. Questo valore è uno dei valori [CorNativeLinkType](cornativelinktype-enumeration.md) .|  
|`m_flags`|Flag utilizzati dal linker durante il collegamento del codice nativo. Questo valore è uno dei valori [CorNativeLinkFlags](cornativelinkflags-enumeration.md) .|  
|`m_entryPoint`|Token di metadati MemberRef che rappresenta il punto di ingresso. Il formato è `lib:entrypoint`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di metadati](metadata-structures.md)
- [Enumerazione CorNativeLinkType](cornativelinktype-enumeration.md)
- [Enumerazione CorNativeLinkFlags](cornativelinkflags-enumeration.md)
