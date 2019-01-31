---
title: Struct C# - Panoramica del linguaggio C#
description: Informazioni di base sui tipi di valori C# denominati struct
ms.date: 08/10/2016
ms.assetid: 88a74571-f741-4a31-a2b5-1ccf165535b8
ms.openlocfilehash: d22cb23fe095874f24d7c002dfdb3eefdde66722
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2019
ms.locfileid: "55065960"
---
# <a name="structs"></a>Struct

Analogamente alle classi, i tipi ***struct*** sono strutture dati che possono contenere membri dati e membri funzione. A differenza delle classi, tuttavia, i tipi struct sono tipi valore e non richiedono l'allocazione dell'heap. Una variabile di un tipo struct archivia direttamente i relativi dati, mentre una variabile di un tipo classe archivia un riferimento a un oggetto allocato in modo dinamico. I tipi struct non supportano l'ereditarietà specificata dall'utente. Tutti i tipi struct ereditano implicitamente dal tipo <xref:System.ValueType>, che a sua volta eredita implicitamente da `object`.

I tipi struct sono particolarmente utili per strutture dati di piccole dimensioni che hanno una semantica di valori. I numeri complessi, i punti di un sistema di coordinate o le coppie chiave-valore di un dizionario sono buoni esempi di struct. L'uso dei tipi struct al posto delle classi può determinare una notevole differenza riguardo al numero di allocazioni di memoria eseguite da un'applicazione. Il programma seguente, ad esempio, crea e inizializza una matrice di 100 punti. Con `Point` implementato come classe, vengono create istanze di 101 oggetti separati, uno per la matrice e uno per ciascuno dei 100 elementi.

[!code-csharp[PointClassUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L5-L13)]

Un'alternativa consiste nel trasformare Point in un tipo struct.

[!code-csharp[PointStruct](../../../samples/snippets/csharp/tour/structs/Point.cs#L3-L11)]

Viene ora creata un'istanza di un solo oggetto, quello relativo alla matrice, e le istanze di `Point` vengono memorizzate inline nella matrice.

I costruttori di struct vengono richiamati con l'operatore `new`, analogamente a un costruttore di classe. Tuttavia, invece di allocare in modo dinamico un oggetto nell'heap gestito e di restituire un riferimento a questo oggetto, un costruttore di struct restituisce semplicemente il valore di struct stesso, in genere in una posizione temporanea nello stack, che viene quindi copiato in base alle esigenze.

Con le classi, due variabili possono fare riferimento allo stesso oggetto e pertanto le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra. Con i tipi struct, ogni variabile ha una propria copia dei dati e le operazioni su una variabile non possono influire sull'altra. Ad esempio, l'output generato dal segmento di codice seguente dipende dal fatto che l'oggetto Point sia una classe o un tipo struct.

[!code-csharp[PointUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L19-L22)]

Se `Point` è una classe, l'output è 20 perché `a` e `b` fanno riferimento allo stesso oggetto. Se `Point` è un tipo struct, l'output è 10 perché l'assegnazione di `a` a `b` crea una copia del valore e tale copia non è interessata dalla successiva assegnazione a `a.x`.

L'esempio precedente evidenzia due delle limitazioni dei tipi struct. In primo luogo, la copia di un intero tipo struct è in genere meno efficiente della copia di un riferimento all'oggetto. Di conseguenza, il passaggio dei parametri di assegnazione e valore può risultare molto più costoso con i tipi struct che con i tipi riferimento. In secondo luogo, ad eccezione dei parametri `in`, `ref` e `out`, non è possibile creare riferimenti ai tipi struct e questa condizione che ne limita l'uso in varie situazioni.

>[!div class="step-by-step"]
>[Precedente](classes-and-objects.md)
>[Successivo](arrays.md)
