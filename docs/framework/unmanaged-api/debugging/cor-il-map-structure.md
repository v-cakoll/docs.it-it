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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9676730a4f11ed77996b7a4aab4e538aba9b53c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="corilmap-structure"></a>Struttura COR_IL_MAP
Specifica le modifiche nell'offset relativo di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`oldOffset`|Il vecchio offset Microsoft intermediate language (MSIL) relativo all'inizio della funzione.|  
|`newOffset`|Nuovo offset MSIL relativo all'inizio della funzione.|  
|`fAccurate`|`true` Se il mapping è nota l'accuratezza; in caso contrario, `false`.|  
  
## <a name="remarks"></a>Note  
 Il formato della mappa è come segue: presuppone che il debugger `oldOffset` fa riferimento a un offset MSIL all'interno del codice MSIL originale, non modificato. Il `newOffset` parametro fa riferimento all'offset MSIL corrispondente all'interno del codice instrumentato.  
  
 Per l'esecuzione di istruzioni per il corretto funzionamento, devono essere soddisfatti i requisiti seguenti:  
  
-   La mappa deve essere ordinata in ordine crescente.  
  
-   Il codice instrumentato MSIL non deve essere riordinato.  
  
-   Il codice MSIL originale non deve essere rimosso.  
  
-   La mappa deve includere le voci per eseguire il mapping di tutti i punti di sequenza dal file di database di (programma PDB) di programma.  
  
 La mappa non interpolare voci mancanti. Nell'esempio seguente viene illustrata una mappa e i relativi risultati.  
  
 Eseguire il mapping:  
  
-   vecchio offset 0, nuovo offset 0  
  
-   vecchio offset 5, 10 nuovo offset  
  
-   vecchio offset 9, 20 nuovo offset  
  
 Risultati:  
  
-   Verrà eseguito il mapping di un vecchio offset 0, 1, 2, 3 o 4 a un nuovo offset pari a 0.  
  
-   Verrà eseguito il mapping di un offset di 5, 6, 7 o 8 precedente al nuovo offset 10.  
  
-   Verrà eseguito il mapping di un offset di 9 o versione successiva precedente al nuovo offset 20.  
  
-   Verrà eseguito il mapping di un nuovo offset di 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al vecchio offset 0.  
  
-   Verrà eseguito il mapping di un nuovo offset pari a 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 al vecchio offset 5.  
  
-   Verrà eseguito il mapping di un nuovo offset pari a 20 o superiore al vecchio offset 9.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Corprof. idl  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
