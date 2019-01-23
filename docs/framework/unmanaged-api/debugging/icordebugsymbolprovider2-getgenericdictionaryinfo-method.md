---
title: Metodo ICorDebugSymbolProvider2::GetGenericDictionaryInfo
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5ed689ad7c456121f7687e7df09eca6c7ea617d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502559"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a>Metodo ICorDebugSymbolProvider2::GetGenericDictionaryInfo
Recupera una mappa di dizionari generici.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetGenericDictionaryInfo(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppMemoryBuffer`  
 [out] Un puntatore all'indirizzo di un [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) oggetto contenente la mappa di dizionari generici. Per altre informazioni, vedere la sezione Osservazioni.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
 La mappa è costituita da due sezioni di primo livello:  
  
-   Oggetto [directory](#Directory) contenente gli indirizzi virtuali relativi (RVA) di tutti i dizionari inclusi nella mappa.  
  
-   Un byte allineato [heap](#Heap) che contiene informazioni sulle creazione di istanze di oggetti. Viene avviato immediatamente dopo l'ultima voce di directory.  
  
<a name="Directory"></a>   
## <a name="the-directory"></a>Directory  
 Ogni voce nella directory fa riferimento a un offset all'interno dell'heap, ovvero un offset relativo all'inizio dell'heap. Il valore delle singole voci non è necessariamente univoco. Più voci di directory possono puntare allo stesso offset nell'heap.  
  
 La parte directory della mappa di dizionari generici presenta la struttura seguente:  
  
-   I primi 4 byte contengono il numero di voci del dizionario, cioè il numero di indirizzi RVA (Relative Virtual Address) presenti nel dizionario. Si farà riferimento a questo valore come *N*. Se viene impostato il bit significativo, le voci vengono organizzate in base all'indirizzo RVA (Relative Virtual Address) in ordine crescente.  
  
-   Il *N* seguono le voci di directory. Ogni voce è costituita da 8 byte in due segmenti di 4 byte:  
  
    -   Byte 0 a 3: RVA; indirizzo virtuale relativo del dizionario.  
  
    -   Byte 4-7: Offset; un offset rispetto all'inizio dell'heap.  
  
<a name="Heap"></a>   
## <a name="the-heap"></a>Heap  
 È possibile calcolare le dimensioni dell'heap tramite un lettore del flusso, sottraendo la lunghezza del flusso dalle dimensioni della directory + 4. In altre parole:  
  
```  
Heap Size = Stream.Length – (Directory Size + 4)  
```  
  
 dove le dimensioni della directory corrispondono a `N * 8`.  
  
 Il formato di ogni elemento delle informazioni sull'heap è il seguente:  
  
-   Lunghezza in byte di questo elemento di informazioni sulla creazione di un'istanza, nel formato di metadati ECMA compresso. Il valore esclude le informazioni sulla lunghezza.  
  
-   Il numero di tipi di istanza generica, oppure *T*, nel formato di metadati ECMA compresso.  
  
-   *T* tipi, ognuno rappresentato nel formato di firma di tipo ECMA.  
  
 L'inclusione della lunghezza per ogni elemento dell'heap consente un ordinamento semplice della sezione della directory senza influire sull'heap.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugSymbolProvider2](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
