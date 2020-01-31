---
title: Metodo ICorDebugSymbolProvider2::GetGenericDictionaryInfo
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
ms.openlocfilehash: 02ecaf56e845680472f42c04f3978e54e7a69272
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791499"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a>Metodo ICorDebugSymbolProvider2::GetGenericDictionaryInfo

Recupera una mappa di dizionari generici.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetGenericDictionaryInfo(
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer
);
```

## <a name="parameters"></a>Parametri

`ppMemoryBuffer`\
out Puntatore all'indirizzo di un oggetto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) contenente la mappa del dizionario generico. Per altre informazioni, vedere la sezione Osservazioni.

## <a name="remarks"></a>Note

> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.

La mappa è costituita da due sezioni di primo livello:

- Una [directory](#Directory) contenente gli indirizzi RVA (relative Virtual Address) di tutti i dizionari inclusi in questa mappa.

- [Heap](#Heap) allineato ai byte che contiene informazioni sulla creazione di istanze di oggetti. Viene avviato immediatamente dopo l'ultima voce di directory.

<a name="Directory"></a>

## <a name="the-directory"></a>Directory

Ogni voce nella directory fa riferimento a un offset all'interno dell'heap, ovvero un offset relativo all'inizio dell'heap. Il valore delle singole voci non è necessariamente univoco. Più voci di directory possono puntare allo stesso offset nell'heap.

La parte directory della mappa di dizionari generici presenta la struttura seguente:

- I primi 4 byte contengono il numero di voci del dizionario, cioè il numero di indirizzi RVA (Relative Virtual Address) presenti nel dizionario. Il valore verrà fatto riferimento a *N*. Se viene impostato il bit elevato, le voci vengono ordinate in base all'indirizzo virtuale relativo in ordine crescente.

- Seguono le *N* voci di directory. Ogni voce è costituita da 8 byte in due segmenti di 4 byte:

  - Byte da 0 a 3: RVA, ovvero l'indirizzo RVA (Relative Virtual Address) del dizionario.

  - Byte da 4 a 7: Offset, ovvero un offset relativo all'inizio dell'heap.

<a name="Heap"></a>

## <a name="the-heap"></a>Heap

È possibile calcolare le dimensioni dell'heap tramite un lettore del flusso, sottraendo la lunghezza del flusso dalle dimensioni della directory + 4. In altre parole:

```csharp
Heap Size = Stream.Length – (Directory Size + 4)
```

dove le dimensioni della directory corrispondono a `N * 8`.

Il formato di ogni elemento delle informazioni sull'heap è il seguente:

- Lunghezza in byte di questo elemento di informazioni sulla creazione di un'istanza, nel formato di metadati ECMA compresso. Il valore esclude le informazioni sulla lunghezza.

- Il numero di tipi di creazione di istanze generiche, o *T*, nel formato di metadati ECMA compresso.

- Tipi *T* , ognuno rappresentato nel formato di firma del tipo ECMA.

L'inclusione della lunghezza per ogni elemento dell'heap consente un ordinamento semplice della sezione della directory senza influire sull'heap.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
