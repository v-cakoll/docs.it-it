---
title: Oggetti - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- objects [C#], about objects
- variables [C#]
ms.assetid: af4a5230-fbf3-4eea-95e1-8b883c2f845c
ms.openlocfilehash: a2f5300f9647823cf2c9ac2a4a5c7c888c7dd245
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626581"
---
# <a name="objects-c-programming-guide"></a>Oggetti (Guida per programmatori C#)
Una definizione di classe o struct è simile a un progetto iniziale in cui vengono specificate le funzionalità del tipo. Un oggetto è essenzialmente un blocco di memoria che è stato allocato e configurato in base al progetto iniziale. Un programma può creare molti oggetti della stessa classe. Gli oggetti, definiti anche istanze, possono essere archiviati in una variabile denominata o in una matrice o raccolta. Il codice client è il codice che usa queste variabili per chiamare i metodi e accedere alle proprietà pubbliche dell'oggetto. In un linguaggio orientato a oggetti come C#, il programma tipico è costituito da più oggetti che interagiscono dinamicamente.  
  
> [!NOTE]
> I tipi statici si comportano in modo diverso da quanto descritto qui. Per altre informazioni, vedere [Classi statiche e membri di classi statiche](./static-classes-and-static-class-members.md).
  
## <a name="struct-instances-vs-class-instances"></a>Istanze struct e istanze di classe  
 Poiché le classi sono tipi di riferimento, una variabile di un oggetto classe contiene un riferimento all'indirizzo dell'oggetto sull'heap gestito. Se al primo oggetto viene assegnato un secondo oggetto dello stesso tipo, entrambe le variabili fanno riferimento all'oggetto in quell'indirizzo. Questo punto viene illustrato più dettagliatamente di seguito in questo argomento.  
  
 Le istanze delle classi vengono create usando l'[operatore new](../../language-reference/operators/new-operator.md). Nell'esempio seguente `Person` è il tipo e `person1` e `person 2` sono le istanze o gli oggetti di tale tipo.  
  
 [!code-csharp[csProgGuideStatements#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#30)]  
  
 Poiché gli struct sono tipi di valore, una variabile di un oggetto struct contiene una copia dell'intero oggetto. Le istanze di struct possono essere create anche usando l'operatore `new`, sebbene non sia obbligatorio, come illustrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideStatements#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#31)]  
  
 La memoria per `p1` e `p2` viene allocata nello stack di thread. La memoria viene recuperata insieme al tipo o al metodo in cui è stata dichiarata. Questo è il motivo per cui gli struct vengono copiati per assegnazione. Al contrario, la memoria allocata per l'istanza di una classe viene recuperata automaticamente (tramite Garbage Collection) da Common Language Runtime quando tutti i riferimenti all'oggetto sono usciti dall'ambito. Non è possibile eliminare in modo deterministico un oggetto di classe come avviene in C++. Per altre informazioni su Garbage Collection in .NET Framework, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
> [!NOTE]
> L'allocazione e la deallocazione di memoria sull'heap gestito sono estremamente ottimizzate in Common Language Runtime. Nella maggior parte dei casi non esistono differenze significative in termini di impatto sulle prestazioni tra l'allocazione di un'istanza di classe sull'heap e l'allocazione di un'istanza di struttura sullo stack.
  
## <a name="object-identity-vs-value-equality"></a>Identità dell'oggetto e uguaglianza di valori  
 Quando si confrontano due oggetti per verificarne l'uguaglianza, è necessario innanzitutto distinguere se si vuole determinare se le due variabili rappresentano lo stesso oggetto in memoria oppure se i valori di uno o più campi sono equivalenti. Se si intende confrontare valori, è necessario considerare se gli oggetti sono istanze di tipi di valore (struct) o di tipi di riferimento (classi, delegati, matrici).  
  
- Per determinare se due istanze di classe fanno riferimento alla stessa posizione in memoria (ovvero hanno la stessa *identità*), usare il metodo statico <xref:System.Object.Equals%2A>. <xref:System.Object?displayProperty=nameWithType> è la classe di base implicita per tutti i tipi valore e i tipi riferimento, inclusi struct e classi definiti dall'utente.  
  
- Per determinare se i campi di istanza in due istanze di struct hanno gli stessi valori, usare il metodo <xref:System.ValueType.Equals%2A?displayProperty=nameWithType>. Poiché tutti gli struct ereditano implicitamente da <xref:System.ValueType?displayProperty=nameWithType>, il metodo viene chiamato direttamente nell'oggetto, come illustrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideStatements#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#32)]  
  
 L'implementazione <xref:System.ValueType?displayProperty=nameWithType> di `Equals` usa la reflection perché deve essere in grado di determinare i campi presenti in tutti gli struct. Quando si creano struct, eseguire l'override del metodo `Equals` per specificare un algoritmo di uguaglianza efficiente specifico del tipo.  
  
- Per determinare se i valori dei campi in due istanze di classe sono uguali, è possibile usare il metodo <xref:System.Object.Equals%2A> o l'operatore [==](../../language-reference/operators/equality-operators.md#equality-operator-). Tuttavia, usarli solo se la classe ha eseguito il loro override o overload per offrire una definizione personalizzata di cosa significa "uguaglianza" per gli oggetti di quel tipo. La classe può anche implementare l'interfaccia <xref:System.IEquatable%601> o <xref:System.Collections.Generic.IEqualityComparer%601>. Entrambe le interfacce offrono metodi che possono essere usati per verificare l'uguaglianza dei valori. Quando si progettano classi personalizzate che eseguono l'override di `Equals`, assicurarsi di seguire le linee guida indicate in [come definire l'uguaglianza di valori per un tipo](../statements-expressions-operators/how-to-define-value-equality-for-a-type.md) e <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>.
  
## <a name="related-sections"></a>Sezioni correlate  
 Per altre informazioni:  
  
- [Classi](./classes.md)  
  
- [Struct](./structs.md)  
  
- [Costruttori](./constructors.md)  
  
- [Finalizzatori](./destructors.md)  
  
- [Eventi](../events/index.md)  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [object](../../language-reference/builtin-types/reference-types.md)
- [Ereditarietà](./inheritance.md)
- [class](../../language-reference/keywords/class.md)
- [struct](../../language-reference/builtin-types/struct.md)
- [Operatore new](../../language-reference/operators/new-operator.md)
- [Common Type System](../../../standard/base-types/common-type-system.md)
