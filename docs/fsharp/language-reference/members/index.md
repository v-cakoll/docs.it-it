---
title: Membri (F#)
description: Informazioni sui membri di oggetto nel linguaggio di programmazione c#.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: a37f14d138cc017cf78e3a0ff1d5b5bba2f09020
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
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
|[Campi espliciti: parola chiave `val`](explicit-fields-the-val-keyword.md)|Descrive la definizione dei campi non inizializzati in un tipo.|
