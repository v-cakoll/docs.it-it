---
title: Classi - Guida per programmatori C#
description: Informazioni sui tipi di classe e su come crearli
ms.date: 08/21/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: d726ab3a882d2e6913fa69c7b82f1d6db78dd47d
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102047"
---
# <a name="classes-c-programming-guide"></a>Classi (Guida per programmatori C#)

## <a name="reference-types"></a>Tipi riferimento  
Un tipo definito come [classe](../../language-reference/keywords/class.md) è un *tipo di riferimento*. In fase di esecuzione, quando si dichiara una variabile di un tipo riferimento, la variabile contiene il valore [Null](../../language-reference/keywords/null.md) fino a quando non si crea in modo esplicito un'istanza della classe usando l'operatore [new](../../language-reference/operators/new-operator.md) o fino a quando non le viene assegnato un oggetto di un tipo compatibile creato altrove, come illustrato nell'esempio seguente:

```csharp
//Declaring an object of type MyClass.
MyClass mc = new MyClass();

//Declaring another object of the same type, assigning it the value of the first object.
MyClass mc2 = mc;
```

Quando viene creato l'oggetto, una quantità di memoria sufficiente viene allocata nell'heap gestito per l'oggetto specifico e la variabile mantiene solo un riferimento al percorso dell'oggetto. I tipi nell'heap gestito richiedono un overhead quando vengono allocati e recuperati dalla funzionalità di gestione automatica della memoria di CLR, nota come *Garbage Collection*. La Garbage Collection, tuttavia, è anche altamente ottimizzata e, nella maggior parte degli scenari, non genera un problema di prestazioni. Per altre informazioni sulla Garbage Collection, vedere [Gestione automatica della memoria e Garbage Collection](../../../standard/garbage-collection/fundamentals.md).  
  
## <a name="declaring-classes"></a>Dichiarazione di classi

 Le classi vengono dichiarate usando la parola chiave [class](../../language-reference/keywords/class.md) seguita da un identificatore univoco, come illustrato nell'esempio seguente:

 ```csharp
//[access modifier] - [class] - [identifier]
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 La parola chiave `class` è preceduta dal livello di accesso. Poiché in questo caso viene usata la parola chiave [public](../../language-reference/keywords/public.md), chiunque può creare istanze di questa classe. Il nome della classe segue la parola chiave `class`. Il nome della classe deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido. Il resto della definizione è il corpo della classe, in cui vengono definiti il comportamento e i dati. I campi, le proprietà, i metodi e gli eventi in una classe vengono collettivamente definiti *membri della classe*.  
  
## <a name="creating-objects"></a>Creazione di oggetti

Anche se vengono talvolta usati in modo intercambiabile, una classe e un oggetto sono elementi diversi. Una classe definisce un tipo di oggetto, ma non è un oggetto. Un oggetto è un'entità concreta ed è basato su una classe. Talvolta si fa riferimento all'oggetto come istanza di una classe.  
  
 Gli oggetti possono essere creati tramite la parola chiave [new](../../language-reference/operators/new-operator.md) seguita dal nome della classe su cui si baserà l'oggetto, nel modo seguente:  

 ```csharp
 Customer object1 = new Customer();
 ```

 Quando viene creata un'istanza di una classe, viene passato al programmatore un riferimento all'oggetto. Nell'esempio precedente, `object1` è un riferimento a un oggetto basato su `Customer`. Questo riferimento indica il nuovo oggetto, ma non contiene i dati dell'oggetto. Infatti, è possibile creare un riferimento all'oggetto senza creare un oggetto:  

```csharp
 Customer object2;
```

 Non è consigliabile creare riferimenti a oggetti come questo che non fanno riferimento a un oggetto reale perché il tentativo di accedere a un oggetto tramite tale riferimento avrà esito negativo in fase di esecuzione. Tuttavia, tale riferimento può essere creato per fare riferimento a un oggetto, creando un nuovo oggetto oppure assegnandolo a un oggetto esistente, come illustrato di seguito:  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
```
  
 Questo codice crea due riferimenti a oggetti che fanno entrambi riferimento allo stesso oggetto. Tutte le modifiche effettuate all'oggetto tramite `object3` si riflettono tuttavia nei successivi usi di `object4`. Poiché gli oggetti che si basano su classi vengono indicati tramite riferimenti, le classi sono note come tipi di riferimento.  
  
## <a name="class-inheritance"></a>Ereditarietà delle classi  

Le classi supportano completamente l'*ereditarietà*, una caratteristica fondamentale nella programmazione orientata a oggetti. Quando si crea una classe, è possibile ereditare da qualsiasi altra interfaccia o classe non definita come [sealed](../../language-reference/keywords/sealed.md) e le altre classi possono ereditare dalla classe appena creata ed eseguire l'override dei metodi virtuali della classe.

L'ereditarietà si ottiene usando una *derivazione*, vale a dire che una classe viene dichiarata usando una *classe di base* da cui eredita dati e comportamento. Una classe di base viene specificata tramite l'aggiunta di due punti e il nome della classe di base dopo il nome della classe derivata, nel modo seguente:  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```

Quando una classe dichiara una classe di base, eredita tutti i membri della classe di base, a eccezione dei costruttori. Per altre informazioni, vedere [Ereditarietà](inheritance.md).
  
Diversamente da C++, una classe di C# può ereditare direttamente solo da una classe di base. Tuttavia, poiché una classe di base può ereditare da un'altra classe, una classe può ereditare indirettamente più classi di base. Una classe può anche implementare direttamente più di un'interfaccia. Per ulteriori informazioni, vedi [Interfacce](../interfaces/index.md).  
  
Una classe può essere dichiarata come [astratta](../../language-reference/keywords/abstract.md). Una classe astratta contiene metodi astratti che hanno una definizione di firma, ma senza implementazione. Non è possibile creare un'istanza di classi astratte. Le classi astratte possono essere usate solo tramite classi derivate che implementano i metodi astratti. Al contrario, una classe [sealed](../../language-reference/keywords/sealed.md) non consente ad altre classi di derivare da tale classe. Per ulteriori informazioni, vedere [Classi astratte e sealed e Membri di classe](abstract-and-sealed-classes-and-class-members.md).  
  
Le definizioni di classe possono essere suddivise tra file di origine diversa. Per altre informazioni, vedere [Classi e metodi parziali](partial-classes-and-methods.md).  
  
## <a name="example"></a>Esempio

L'esempio seguente definisce una classe pubblica che contiene una [proprietà implementata automaticamente](auto-implemented-properties.md), un metodo e un metodo speciale denominato costruttore. Per altre informazioni, vedere gli argomenti [Proprietà](properties.md), [Metodi](methods.md) e [Costruttori](constructors.md). Le istanze della classe vengono quindi create con la parola chiave `new`.  
  
[!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)]
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida alla programmazione in C](../index.md)
- [Programmazione orientata ad oggetti](../concepts/object-oriented-programming.md)
- [Polimorfismo](polymorphism.md)
- [Nomi di identificatore](../inside-a-program/identifier-names.md)
- [Membri](members.md)
- [Metodi](methods.md)
- [Costruttori](constructors.md)
- [Finalizzatori](destructors.md)
- [Oggetti](objects.md)
