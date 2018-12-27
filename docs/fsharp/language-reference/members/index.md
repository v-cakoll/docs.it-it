---
title: Membri
description: Informazioni sui membri di oggetti di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: c32bd76ab60673563f0cc45ce0fb569b2ea262b9
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613141"
---
# <a name="members"></a>Membri

Questa sezione illustra i membri dei tipi di oggetto F#.

## <a name="remarks"></a>Note

I *membri* sono funzionalità che fanno parte di una definizione di tipo e vengono dichiarati con la parola chiave `member`. I tipi di oggetto F#, ad esempio record, classi, unioni discriminate, interfacce e strutture, supportano i membri. Per altre informazioni, vedere [Record](../records.md), [Classi](../classes.md), [Unioni discriminate](../discriminated-Unions.md), [Interfacce](../interfaces.md) e [Strutture](../structures.md).

I membri in genere costituiscono l'interfaccia pubblica per un tipo, e per questo motivo sono pubblici, se non diversamente specificato. I membri possono anche essere dichiarati privati o interni. Per altre informazioni, vedere [Controllo di accesso](../access-Control.md). Le firme per i tipi possono anche essere usate per esporre o meno determinati membri di un tipo. Per altre informazioni, vedere [Firme](../signatures.md).

I campi privati e le associazioni `do`, usati solo con le classi, non sono membri veri, perché non fanno mai parte dell'interfaccia pubblica di un tipo e non sono dichiarati con la parola chiave `member`, però vengono descritti in questa sezione.

## <a name="related-topics"></a>Argomenti correlati

|Argomento|Descrizione|
|-----|-----------|
|[Associazioni `let` nelle classi](let-bindings-in-classes.md)|Descrive la definizione dei campi privati e le funzioni nelle classi.|
|[Associazioni `do` nelle classi](do-bindings-in-classes.md)|Descrive la specifica del codice di inizializzazione dell'oggetto.|
|[Proprietà](properties.md)|Descrive i membri di proprietà nelle classi e altri tipi.|
|[Proprietà indicizzate](indexed-properties.md)|Descrive le proprietà di tipo matrice nelle classi e altri tipi.|
|[Metodi](methods.md)|Descrive funzioni che sono membri di un tipo.|
|[Costruttori](constructors.md)|Descrive funzioni speciali che inizializzano oggetti di un tipo.|
|[Overload degli operatori](../operator-overloading.md)|Descrive la definizione di operatori personalizzati per i tipi.|
|[Eventi](events.md)|Descrive la definizione di eventi e il supporto di gestione degli eventi in F# .|
|[Campi espliciti: Parola chiave `val`](explicit-fields-the-val-keyword.md)|Descrive la definizione dei campi non inizializzati in un tipo.|