---
title: Tipi di valore (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 3bbaea9247d975c27ed6f49dedb749312f675296
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526463"
---
# <a name="value-types-c-reference"></a>Tipi di valore (Riferimenti per C#)
I tipi valore comprendono due categorie principali:  
  
-   [Struct](../../../csharp/language-reference/keywords/struct.md)  
  
-   [Enumerazioni](../../../csharp/language-reference/keywords/enum.md)  
  
 Gli struct sono suddivisi nelle categorie seguenti:  
  
-   Tipi numerici  
  
    -   [Tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [Tipi a virgola mobile](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
-   [bool](../../../csharp/language-reference/keywords/bool.md)  
  
-   Struct definiti dall'utente.  
  
## <a name="main-features-of-value-types"></a>Funzionalità principali dei tipi valore  
 Le variabili che sono basate direttamente su tipi valore contengono valori. Assegnando una variabile di tipo valore a un'altra, il valore contenuto viene copiato. Questo comportamento è diverso dall'assegnazione delle variabili di tipo riferimento, in cui viene copiato un riferimento all'oggetto, ma non l'oggetto stesso.  
  
 Tutti i tipi valore sono derivati in modo implicito da <xref:System.ValueType?displayProperty=nameWithType>.  
  
 A differenza dei tipi riferimento, non è possibile derivare un nuovo tipo da un tipo valore. Tuttavia, come i tipi riferimento, gli struct possono implementare interfacce.  
  
 A differenza dei tipi riferimento, un tipo valore non può contenere il valore `null`. Tuttavia, la funzionalità per i [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md) consente di assegnare tipi valore a `null`.  
  
 Ogni tipo valore ha un costruttore predefinito implicito che inizializza il valore predefinito di tale tipo. Per informazioni sui valori predefiniti dei tipi valore, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).  
  
## <a name="main-features-of-simple-types"></a>Funzionalità principali dei tipi semplici  
 Tutti i tipi semplici, ovvero quelli integrali del linguaggio C#, sono alias dei tipi di sistema di .NET Framework. Ad esempio, [int](../../../csharp/language-reference/keywords/int.md) è un alias di <xref:System.Int32?displayProperty=nameWithType>. Per un elenco completo degli alias, vedere [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md).  
  
 Le espressioni costanti, in cui gli operandi sono tutte costanti di tipo semplice, vengono valutate in fase di compilazione.  
  
 I tipi semplici possono essere inizializzati mediante valori letterali. Ad esempio, 'A' è un valore letterale del tipo `char` e 2001 è un valore letterale del tipo `int`.  
  
## <a name="initializing-value-types"></a>Inizializzazione di tipi valore  
 Le variabili locali in C# devono essere inizializzate prima di poter essere usate. È ad esempio possibile dichiarare una variabile locale senza inizializzazione, come nell'esempio seguente:  
  
```csharp  
int myInt;  
```  
  
 Non è possibile usarla prima di averla inizializzata. È possibile inizializzarla mediante l'istruzione seguente:  
  
```csharp  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 Questa istruzione è equivalente all'istruzione seguente:  
  
```csharp  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 Naturalmente, è possibile inserire la dichiarazione e l'inizializzazione nella stessa istruzione, come negli esempi seguenti:  
  
```csharp  
int myInt = new int();  
```  
  
 - oppure -  
  
```csharp  
int myInt = 0;  
```  
  
 Usando l'operatore [new](../../../csharp/language-reference/keywords/new.md), viene chiamato il costruttore predefinito del tipo specifico e viene assegnato il valore predefinito alla variabile. Nell'esempio precedente, il costruttore predefinito assegna il valore `0` a `myInt`. Per altre informazioni sui valori assegnati chiamando i costruttori predefiniti, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Con i tipi definiti dall'utente, usare [new](../../../csharp/language-reference/keywords/new.md) per richiamare il costruttore predefinito. Ad esempio, l'istruzione seguente richiama il costruttore predefinito dello struct `Point`:  
  
```csharp  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 Dopo questa chiamata, lo struct viene considerato definitivamente assegnato, ovvero tutti i relativi membri sono inizializzati sui valori predefiniti.  
  
 Per altre informazioni sull'operatore new, vedere [new](../../../csharp/language-reference/keywords/new.md).  
  
 Per informazioni sulla formattazione dell'output dei tipi numerici, vedere [Tabella di formattazione dei risultati numerici](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
- [Tipi](../../../csharp/language-reference/keywords/types.md)  
- [Tabelle di riferimento per i tipi](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
- [Tipi riferimento](../../../csharp/language-reference/keywords/reference-types.md)  
- [Tipi nullable](../../programming-guide/nullable-types/index.md)  
