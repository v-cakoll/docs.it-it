---
title: Struttura COR_IL_MAP
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179297"
---
# <a name="cor_il_map-structure"></a>Struttura COR_IL_MAP
Specifica le modifiche nell'offset relativo di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`oldOffset`|L'offset MSIL (Microsoft Intermediate Language) precedente all'inizio della funzione.|  
|`newOffset`|Nuovo offset MSIL relativo all'inizio della funzione.|  
|`fAccurate`|`true`se il mapping è noto per essere accurato; in `false`caso contrario, .|  
  
## <a name="remarks"></a>Osservazioni  
 Il formato della mappa è il seguente: `oldOffset` il debugger presupporrà che fa riferimento a un offset MSIL all'interno del codice MSIL originale non modificato. Il `newOffset` parametro si riferisce all'offset MSIL corrispondente all'interno del nuovo codice instrumentato.  
  
 Affinché il passaggio funzioni correttamente, è necessario che siano soddisfatti i seguenti requisiti:  
  
- La mappa deve essere ordinata in ordine crescente.  
  
- Il codice MSIL instrumentato non deve essere riordinato.  
  
- Il codice MSIL originale non deve essere rimosso.  
  
- La mappa deve includere voci per eseguire il mapping di tutti i punti di sequenza dal file di database di programma (PDB).  
  
 La mappa non interpola le voci mancanti. Nell'esempio seguente viene illustrata una mappa e i relativi risultati.  
  
 Mappa:  
  
- 0 scostamento precedente, 0 nuovo offset  
  
- 5 scostamento vecchio, 10 nuovi offset  
  
- 9 vecchio offset, 20 nuovi offset  
  
 Risultati:  
  
- Un offset precedente di 0, 1, 2, 3 o 4 verrà mappato a un nuovo offset pari a 0.  
  
- Un offset precedente di 5, 6, 7 o 8 verrà mappato al nuovo offset 10.  
  
- Un offset precedente di 9 o superiore verrà mappato al nuovo offset 20.  
  
- Un nuovo offset di 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 verrà mappato all'offset precedente 0.  
  
- Un nuovo offset di 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 verrà mappato all'offset 5.  
  
- Un nuovo offset di 20 o superiore verrà mappato al vecchio offset 9.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
