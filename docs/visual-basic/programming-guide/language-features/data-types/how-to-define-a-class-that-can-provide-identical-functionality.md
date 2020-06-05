---
title: 'Procedura: Definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi'
ms.date: 07/20/2015
helpviewer_keywords:
- data type arguments [Visual Basic], using
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- data type parameters [Visual Basic], using
- generics [Visual Basic], defining classes with type parameters
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- type arguments
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
- parameters [Visual Basic], data type
- generics [Visual Basic], defining generic types
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
ms.openlocfilehash: 3b1f47250453c32735d633b98da0bd0ddb1ed5b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393857"
---
# <a name="how-to-define-a-class-that-can-provide-identical-functionality-on-different-data-types-visual-basic"></a>Procedura: definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi (Visual Basic)
È possibile definire una classe dalla quale creare oggetti in grado di fornire funzionalità identiche su tipi di dati diversi. A questo scopo, specificare uno o più *parametri di tipo* nella definizione. La classe potrà quindi servire come modello per gli oggetti che usano tipi di dati diversi. Una classe definita in questo modo viene denominata *classe generica*.  
  
 Il vantaggio della definizione di una classe generica sta nel fatto che viene definita un'unica volta e che può essere usata dal codice per la creazione di molti oggetti che usano una vasta gamma di tipi di dati. Questo comporta prestazioni superiori rispetto alla definizione della classe con il tipo `Object` .  
  
 Oltre alle classi, è possibile definire e usare anche strutture, interfacce, routine e delegati generici.  
  
### <a name="to-define-a-class-with-a-type-parameter"></a>Per definire una classe con un parametro di tipo  
  
1. Definire la classe nel modo normale.  
  
2. Aggiungere `(Of` *typeparameter* `)` subito dopo il nome della classe per specificare un parametro di tipo.  
  
3. Se esiste più di un parametro di tipo, creare un elenco separato da virgole all'interno delle parentesi. Non ripetere la parola chiave `Of` .  
  
4. Se le operazioni eseguite dal codice su un parametro di tipo sono diverse da una semplice assegnazione, far seguire il parametro di tipo da una clausola `As` per l'aggiunta di uno o più *vincoli*. Un vincolo garantisce che il tipo fornito per tale parametro di tipo soddisfi un requisito, ad esempio:  
  
    - Supporta un'operazione, quale `>`, eseguita dal codice  
  
    - Supporta un membro, quale un metodo, a cui accede il codice  
  
    - Espone un costruttore senza parametri  
  
     Se non si specifica alcun vincolo, le uniche operazioni e gli unici membri usati dal codice sono quelli supportati dal [Object Data Type](../../../language-reference/data-types/object-data-type.md). Per altre informazioni, vedere [Type List](../../../language-reference/statements/type-list.md).  
  
5. Identificare ogni membro della classe da dichiarare con un tipo fornito e dichiararlo `As` `typeparameter` . Questo vale per l'archiviazione interna, i parametri di routine e i valori restituiti.  
  
6. Accertarsi che il codice usi solo operazioni e metodi supportati da qualsiasi tipo di dati che può fornire a `itemType`.  
  
     Nell'esempio riportato di seguito viene definita una classe che gestisce un elenco molto semplice. L'elenco è contenuto negli `items`della matrice interna e il tipo di dati degli elementi dell'elenco può essere dichiarato dal codice. Un costruttore con parametri consente di usare il codice per impostare il limite superiore di `items` e il costruttore senza parametri imposta questa proprietà su 9 (per un totale di 10 elementi).  
  
     [!code-vb[VbVbalrDataTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#7)]  
  
     È possibile dichiarare una classe da `simpleList` per contenere un elenco di valori `Integer` , un'altra classe per contenere un elenco di valori `String` e un'altra per contenere valori `Date` . Ad eccezione del tipo di dati dei membri dell'elenco, gli oggetti creati da tutte queste classi si comportano in maniera identica.  
  
     L'argomento di tipo fornito dal codice a `itemType` può essere di tipo intrinseco come `Boolean` o `Double`, una struttura, un'enumerazione o qualsiasi tipo di classe, compresa una di quelle definite dall'applicazione.  
  
     È possibile verificare la classe `simpleList` con il codice seguente.  
  
     [!code-vb[VbVbalrDataTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](index.md)
- [Generic Types in Visual Basic](generic-types.md)
- [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../../standard/language-independence-and-language-independent-components.md)
- [Di](../../../language-reference/statements/of-clause.md)
- [Type List](../../../language-reference/statements/type-list.md)
- [Procedura: Usare una classe generica](how-to-use-a-generic-class.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
