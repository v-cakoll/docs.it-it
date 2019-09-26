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
ms.openlocfilehash: 5ae4c5743b01c4a9087323678d315473631cb32f
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274044"
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
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`oldOffset`|Offset MSIL (Microsoft Intermediate Language) precedente relativo all'inizio della funzione.|  
|`newOffset`|Nuovo offset MSIL relativo all'inizio della funzione.|  
|`fAccurate`|`true`Se il mapping è noto come accurato; in caso `false`contrario,.|  
  
## <a name="remarks"></a>Note  
 Il formato della mappa è il seguente: Si presuppone che `oldOffset` il debugger si riferisca a un offset MSIL all'interno del codice MSIL originale, non modificato. Il `newOffset` parametro fa riferimento all'offset MSIL corrispondente all'interno del nuovo codice instrumentato.  
  
 Per il corretto funzionamento, è necessario soddisfare i requisiti seguenti:  
  
- La mappa deve essere ordinata in ordine crescente.  
  
- Il codice MSIL instrumentato non deve essere riordinato.  
  
- Il codice MSIL originale non deve essere rimosso.  
  
- La mappa deve includere le voci per eseguire il mapping di tutti i punti di sequenza dal file di database di programma (PDB).  
  
 La mappa non esegue l'interpolazione delle voci mancanti. Nell'esempio seguente viene illustrata una mappa e i relativi risultati.  
  
 Mappa  
  
- 0 offset precedente, 0 nuovo offset  
  
- 5 offset precedente, 10 nuovo offset  
  
- 9 offset precedente, 20 nuovo offset  
  
 Risultati  
  
- Un offset precedente di 0, 1, 2, 3 o 4 verrà mappato a un nuovo offset di 0.  
  
- Viene eseguito il mapping di un offset precedente di 5, 6, 7 o 8 al nuovo offset 10.  
  
- Verrà eseguito il mapping di un offset precedente di 9 o superiore al nuovo offset 20.  
  
- Viene eseguito il mapping di un nuovo offset di 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 all'offset precedente 0.  
  
- Viene eseguito il mapping di un nuovo offset di 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 alla precedente offset 5.  
  
- Verrà eseguito il mapping di un nuovo offset di 20 o superiore alla precedente offset 9.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorProf.idl  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
