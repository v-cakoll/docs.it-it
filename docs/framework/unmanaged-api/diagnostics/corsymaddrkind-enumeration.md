---
title: Enumerazione CorSymAddrKind
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 389cf2e77728002ce1078f63df3d741d1847c105
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744973"
---
# <a name="corsymaddrkind-enumeration"></a>Enumerazione CorSymAddrKind
Indica il tipo di indirizzo di memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|Indica un Microsoft intermediate language (MSIL) locale variabile o parametro di indice.|  
|`ADDR_NATIVE_RVA`|Indica un indirizzo virtuale relativo in un modulo.|  
|`ADDR_NATIVE_REGISTER`|Indica un registro della CPU.|  
|`ADDR_NATIVE_REGREL`|Indica che il primo indirizzo è un registro e l'indirizzo di secondo è un offset.|  
|`ADDR_NATIVE_OFFSET`|Indica un offset da un indirizzo di base.|  
|`ADDR_NATIVE_REGREG`|Indica che il primo indirizzo è la parte bassa di un registro, e il secondo indirizzo è la parte alta.|  
|`ADDR_NATIVE_REGSTK`|Indica che il primo indirizzo è la parte bassa di un registro, il secondo è la parte alta e il terzo è un offset.|  
|`ADDR_NATIVE_STKREG`|Indica che il primo indirizzo è un registro, il secondo è un offset e il terzo è la parte alta del registro.|  
|`ADDR_BITFIELD`|Indica che il primo indirizzo è l'inizio di un campo e il secondo indirizzo è la lunghezza del campo.|  
|`ADDR_NATIVE_ISECTOFFSET`|Indica che il primo indirizzo è la sezione e il secondo indirizzo è un offset.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Enumerazioni dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
