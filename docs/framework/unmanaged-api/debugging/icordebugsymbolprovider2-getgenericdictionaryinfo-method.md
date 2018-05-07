---
title: Metodo ICorDebugSymbolProvider2::GetGenericDictionaryInfo
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c69be53a429e2f40741cc1e4c20fef3b7363654
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
  
-   Allineata byte [heap](#Heap) che contiene informazioni sull'istanza di oggetto. Viene avviato immediatamente dopo l'ultima voce di directory.  
  
<a name="Directory"></a>   
## <a name="the-directory"></a>Directory  
 Ogni voce nella directory fa riferimento a un offset all'interno dell'heap, ovvero un offset relativo all'inizio dell'heap. Il valore delle singole voci non è necessariamente univoco. Più voci di directory possono puntare allo stesso offset nell'heap.  
  
 La parte directory della mappa di dizionari generici presenta la struttura seguente:  
  
-   I primi 4 byte contengono il numero di voci del dizionario, cioè il numero di indirizzi RVA (Relative Virtual Address) presenti nel dizionario. Si farà riferimento a questo valore come *N*. Se viene impostato il bit significativo, le voci vengono organizzate in base all'indirizzo RVA (Relative Virtual Address) in ordine crescente.  
  
-   Il *N* seguono le voci di directory. Ogni voce è costituita da 8 byte in due segmenti di 4 byte:  
  
    -   Byte da 0 a 3: RVA, ovvero l'indirizzo RVA (Relative Virtual Address) del dizionario.  
  
    -   Byte da 4 a 7: Offset, ovvero un offset relativo all'inizio dell'heap.  
  
<a name="Heap"></a>   
## <a name="the-heap"></a>Heap  
 È possibile calcolare le dimensioni dell'heap tramite un lettore del flusso, sottraendo la lunghezza del flusso dalle dimensioni della directory + 4. In altre parole:  
  
```  
Heap Size = Stream.Length – (Directory Size + 4)  
```  
  
 dove le dimensioni della directory corrispondono a `N * 8`.  
  
 Il formato di ogni elemento delle informazioni sull'heap è il seguente:  
  
-   Lunghezza in byte di questo elemento di informazioni sulla creazione di un'istanza, nel formato di metadati ECMA compresso. Il valore esclude le informazioni sulla lunghezza.  
  
-   Il numero di tipi di istanza generica, o *T*, nel formato di metadati ECMA compresso.  
  
-   *T* tipi, ognuno rappresentato nel formato di firma di tipo ECMA.  
  
 L'inclusione della lunghezza per ogni elemento dell'heap consente un ordinamento semplice della sezione della directory senza influire sull'heap.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugSymbolProvider2](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
