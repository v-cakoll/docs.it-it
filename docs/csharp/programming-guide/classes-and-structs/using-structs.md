---
title: Utilizzo di struct (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 94181c42ce913dc76c9a074e4bcbb8240764c896
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-structs-c-programming-guide"></a>Utilizzo di struct (Guida per programmatori C#)
Il tipo `struct` è adatto a rappresentare oggetti leggeri come `Point`, `Rectangle`e `Color`. Sebbene sia altrettanto conveniente rappresentare un punto con una [classe](../../../csharp/language-reference/keywords/class.md) con [proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), lo [struct](../../../csharp/language-reference/keywords/struct.md) potrebbe essere più efficiente in alcuni scenari. Ad esempio, se si dichiara una matrice di 1000 oggetti `Point` , verrà allocata memoria aggiuntiva per fare riferimento a ogni oggetto. In questo caso, lo struct risulterebbe meno costoso. Dal momento che [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contiene un oggetto denominato <xref:System.Drawing.Point>, lo struct in questo esempio è invece denominato "CoOrds".  
  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 È un errore definire un costruttore predefinito (senza parametri) per uno struct. È anche errato inizializzare un campo di istanza nel corpo di uno struct. È possibile inizializzare i membri accessibili dall'esterno dello struct solo utilizzando un costruttore con parametri, implicito, il costruttore predefinito, un [inizializzatore di oggetto](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md), o accedendo ai membri singolarmente dopo la dichiarazione della struttura. I membri privati o altrimenti inaccessibili richiedono l'utilizzo di costruttori in modo esclusivo.
  
 Quando si crea un oggetto struct mediante il [nuova](../../../csharp/language-reference/keywords/new.md) operatore, viene creato e viene chiamato il costruttore appropriato in base al [firma del costruttore](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax). A differenza delle classi, è possibile creare istanze di struct senza usare l'operatore `new` . In tal caso, non vi è alcuna chiamata al costruttore, il che rende più efficiente l'allocazione. Tuttavia, i campi restano non assegnati e l'oggetto non può essere usato fino all'inizializzazione di tutti i campi. Ciò include l'impossibilità di ottenere o impostare valori tramite le proprietà implementate automaticamente.
 
 Se si crea un'istanza di un oggetto struct mediante l'impostazione predefinita, il costruttore senza parametri, tutti i membri vengono assegnati in base alla loro [i valori predefiniti](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md).
  
 Quando si scrive un costruttore con parametri per uno struct, è necessario inizializzare in modo esplicito tutti i membri. in caso contrario, uno o più membri restano non assegnati e lo struct non può essere usato, che produce l'errore del compilatore CS0171.  
  
 Per gli struct non è prevista la stessa ereditarietà delle classi. Uno struct non può ereditare da un altro struct o da una classe e non può essere la base di una classe. Gli struct, tuttavia, ereditano dalla classe base <xref:System.Object>. Uno struct può implementare interfacce esattamente come le classi.  
  
 Non è possibile dichiarare una classe usando la parola chiave `struct`. In C# le classi e gli struct sono semanticamente diversi. Uno struct è un tipo di valore, mentre una classe è un tipo di riferimento. Per altre informazioni, vedere [Tipi di valore](../../../csharp/language-reference/keywords/value-types.md).  
  
 A meno che non sia richiesta una semantica tipo-riferimento, una classe piccola può essere gestita in modo più efficiente dal sistema se dichiarata come uno struct.  
  
## <a name="example-1"></a>Esempio 1  
  
### <a name="description"></a>Descrizione  
 Questo esempio mostra l'inizializzazione `struct` tramite costruttori con parametri e valore predefinito.  
  
### <a name="code"></a>Codice  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-csharp[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]  
  
## <a name="example-2"></a>Esempio 2  
  
### <a name="description"></a>Descrizione  
 Questo esempio illustra una funzionalità univoca per struct. Crea un oggetto CoOrds senza usare l'operatore `new` . Se si sostituisce la parola `struct` con la parola `class`, il programma non verrà compilato.  
  
### <a name="code"></a>Codice  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-csharp[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Struct](../../../csharp/programming-guide/classes-and-structs/structs.md)
