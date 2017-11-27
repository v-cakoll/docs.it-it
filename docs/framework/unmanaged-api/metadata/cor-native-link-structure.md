---
title: Struttura COR_NATIVE_LINK
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_NATIVE_LINK
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_NATIVE_LINK
helpviewer_keywords: COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e27b66fce8a78ef0feb7ed10e77cc51fc1fe83c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="cornativelink-structure"></a>Struttura COR_NATIVE_LINK
Contiene informazioni usate per collegare il codice nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
|`m_linkType`|Il tipo di collegamento in codice nativo. Questo valore è un valore di [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valori.|  
|`m_flags`|Flag usati dal linker durante il collegamento del codice nativo. Questo valore è un valore di [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valori.|  
|`m_entryPoint`|Il token di metadati di MemberRef che rappresenta il punto di ingresso. Il formato è `lib:entrypoint`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [CorNativeLinkType (enumerazione)](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [CorNativeLinkFlags (enumerazione)](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
