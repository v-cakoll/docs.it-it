---
title: Come inizializzare un dizionario con un inizializzatore di insieme - Guida per programmatori C#
description: Informazioni su come inizializzare un dizionario in C#, usando il metodo Add o un inizializzatore di indice. In questo esempio vengono illustrate entrambe le opzioni.
ms.date: 12/20/2018
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: 2f33240b02785c5c886a1ebebb8984d29c9f7795
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865047"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Come inizializzare un dizionario con un inizializzatore di insieme (Guida per programmatori C#)

Un oggetto <xref:System.Collections.Generic.Dictionary%602> contiene una raccolta di coppie chiave-valore. Il relativo metodo <xref:System.Collections.Generic.Dictionary%602.Add%2A> accetta due parametri, uno per la chiave e uno per il valore. Un modo per inizializzare un oggetto <xref:System.Collections.Generic.Dictionary%602> o qualsiasi raccolta il cui metodo `Add` accetta più parametri, consiste nel racchiudere ogni set di parametri tra parentesi graffe, come illustrato nell'esempio seguente. Un'altra opzione consiste nell'usare un inizializzatore di indice, come mostrato nell'esempio seguente.

## <a name="example"></a>Esempio

Nell'esempio di codice seguente, viene inizializzato un oggetto <xref:System.Collections.Generic.Dictionary%602> con istanze di tipo `StudentName`.  La prima inizializzazione usa il metodo `Add` con due argomenti. Il compilatore genera una chiamata a `Add` per ognuna delle coppie di chiavi `int` e valori `StudentName`. Il secondo usa un metodo di lettura pubblica / indicizzatore di scrittura della classe `Dictionary`:

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToDictionaryInitializer.cs#HowToDictionaryInitializer)]  

Si noti che vi sono due coppie di parentesi graffe in ogni elemento della raccolta nella prima dichiarazione. Le parentesi graffe più interne racchiudono l'inizializzatore di oggetto per `StudentName` e le parentesi graffe più esterne racchiudono l'inizializzatore per la coppia chiave/valore che verrà aggiunta a `students` <xref:System.Collections.Generic.Dictionary%602> . Infine, tutto l'inizializzatore di insieme per il dizionario è racchiuso tra parentesi graffe. Durante la seconda inizializzazione, il lato sinistro dell'assegnazione è la chiave e il lato destro è il valore, usando un inizializzatore di oggetto per `StudentName`.

## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../index.md)
- [Inizializzatori di oggetto e di raccolta](./object-and-collection-initializers.md)
