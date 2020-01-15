---
title: Uso di struct - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
ms.openlocfilehash: 22d63465c534090a8918348ea5f050739c0cf01c
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964754"
---
# <a name="using-structs-c-programming-guide"></a>Utilizzo di struct (C# guida per programmatori)

Il tipo `struct` è adatto a rappresentare oggetti leggeri come `Point`, `Rectangle`e `Color`. Sebbene sia altrettanto conveniente rappresentare un punto con una [classe](../../language-reference/keywords/class.md) con [proprietà implementate automaticamente](./auto-implemented-properties.md), lo [struct](../../language-reference/keywords/struct.md) potrebbe essere più efficiente in alcuni scenari. Ad esempio, se si dichiara una matrice di 1000 oggetti `Point` , verrà allocata memoria aggiuntiva per fare riferimento a ogni oggetto. In questo caso, lo struct risulterebbe meno costoso. Poiché .NET contiene già un oggetto denominato <xref:System.Drawing.Point>, lo struct in questo esempio è denominato `Coords`.

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

È un errore definire un costruttore senza parametri per uno struct. È anche errato inizializzare un campo di istanza nel corpo di uno struct. È possibile inizializzare i membri dello struct accessibili dall'esterno solo usando un costruttore con parametri, il costruttore senza parametri implicito, un [inizializzatore di oggetto](object-and-collection-initializers.md) o accedendo ai membri singolarmente dopo la dichiarazione dello struct. I membri privati o altrimenti inaccessibili richiedono l'utilizzo di costruttori in modo esclusivo.

Quando si crea un oggetto struct mediante l'operatore [new](../../language-reference/operators/new-operator.md), questo viene creato e viene chiamato il costruttore appropriato in base alla [firma del costruttore](constructors.md#constructor-syntax). A differenza delle classi, è possibile creare istanze di struct senza usare l'operatore `new` . In tal caso, non vi è alcuna chiamata al costruttore, il che rende più efficiente l'allocazione. Tuttavia, i campi restano non assegnati e l'oggetto non può essere usato fino all'inizializzazione di tutti i campi. Ciò include l'impossibilità di ottenere o impostare valori tramite le proprietà.

Se si crea un'istanza di un oggetto struct usando il costruttore senza parametri, tutti i membri vengono assegnati in base ai relativi [valori predefiniti](../../language-reference/builtin-types/default-values.md).

Quando si scrive un costruttore con parametri per uno struct, è necessario inizializzare in modo esplicito tutti i membri. in caso contrario, uno o più membri rimangono non assegnati e non è possibile usare lo struct, generando l'errore del compilatore [CS0171](../../misc/cs0171.md).

Per gli struct non è prevista la stessa ereditarietà delle classi. Uno struct non può ereditare da un altro struct o da una classe e non può essere la base di una classe. Gli struct, tuttavia, ereditano dalla classe base <xref:System.Object>. Uno struct può implementare interfacce esattamente come le classi.

Non è possibile dichiarare una classe usando la parola chiave `struct`. In C# le classi e gli struct sono semanticamente diversi. Uno struct è un tipo di valore, mentre una classe è un tipo di riferimento. Per altre informazioni, vedere [tipi di valore](../../language-reference/keywords/value-types.md) e [tipi di riferimento](../../language-reference/keywords/reference-types.md).

A meno che non sia richiesta una semantica tipo-riferimento, una classe piccola può essere gestita in modo più efficiente dal sistema se dichiarata come uno struct.

## <a name="example-1"></a>Esempio 1

In questo esempio viene illustrata `struct` inizializzazione utilizzando i costruttori senza parametri e con parametri.

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

[!code-csharp[csProgGuideObjects#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#2)]

## <a name="example-2"></a>Esempio 2

Questo esempio illustra una funzionalità univoca per struct. Crea un oggetto Coords senza usare l'operatore `new`. Se si sostituisce la parola `struct` con la parola `class`, il programma non verrà compilato.

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

[!code-csharp[csProgGuideObjects#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#3)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](index.md)
- [Struct](structs.md)
