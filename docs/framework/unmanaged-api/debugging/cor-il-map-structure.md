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
ms.openlocfilehash: c7452b76509d5eca592cc3b95df1f77703ec1111
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561829"
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
|`newOffset`|L'offset MSIL nuovo rispetto all'inizio della funzione.|  
|`fAccurate`|`true` Se il mapping è nota l'accuratezza; in caso contrario, `false`.|  
  
## <a name="remarks"></a>Note  
 Il formato della mappa è come segue: Il debugger presupporrà che `oldOffset` fa riferimento a un offset MSIL all'interno del codice MSIL originale, non modificato. Il `newOffset` parametro fa riferimento all'offset MSIL corrispondente all'interno del nuovo codice instrumentato.  
  
 Per l'esecuzione di istruzioni per il corretto funzionamento, è necessario soddisfare i requisiti seguenti:  
  
-   La mappa deve essere disposti in ordine crescente.  
  
-   Il codice instrumentato MSIL non deve essere riordinato.  
  
-   Il codice MSIL originale non deve essere rimossi.  
  
-   La mappa deve includere le voci per eseguire il mapping di tutti i punti di sequenza dei file di database (PDB) di programma.  
  
 La mappa non esegue l'interpolazione voci mancanti. Nell'esempio seguente viene illustrata una mappa e i relativi risultati.  
  
 Eseguire il mapping:  
  
-   vecchio offset 0, 0 nuovo offset  
  
-   offset precedente 5, 10 nuovo offset  
  
-   offset precedente 9, 20 nuovo offset  
  
 Risultati:  
  
-   Un offset 0, 1, 2, 3 o 4 precedente verrà mappato a un nuovo offset pari a 0.  
  
-   Verrà eseguito il mapping di un offset precedente del 5, 6, 7 o 8 al nuovo offset 10.  
  
-   Verrà eseguito il mapping di un offset precedente del 9 o versione successiva al nuovo offset 20.  
  
-   Verrà eseguito il mapping di un nuovo offset 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al vecchio offset 0.  
  
-   Verrà eseguito il mapping di un nuovo offset di 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 al vecchio offset 5.  
  
-   Verrà eseguito il mapping di un nuovo offset pari a 20 o superiore al vecchio offset 9.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
