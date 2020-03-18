---
title: Classi e struct - Guida per programmatori C#
description: Descrive le modalità d'uso di classi e strutture (struct) in C#.
ms.date: 01/17/2016
helpviewer_keywords:
- structs [C#], about structs
- classes [C#], overview
- C# language, structs
- C# language, objects
- objects [C#]
- C# language, classes
ms.assetid: cc39dbda-8754-423e-b5b1-16a1db0734c0
ms.openlocfilehash: afd9e688bd716375bafb370fad4af082a9498411
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79399854"
---
# <a name="classes-and-structs-c-programming-guide"></a>Classi e struct (Guida per programmatori C#)
Classi e struct sono due dei costrutti di base del Common Type System in .NET Framework. Ognuno di essi è costituito essenzialmente da una struttura di dati che incapsula un set di dati e comportamenti che formano insieme un'unità logica. I dati e i comportamenti sono i *membri* della classe o del tipo struct e ne includono i metodi, le proprietà, gli eventi e così via, come illustrato più avanti in questo argomento.  
  
 Una dichiarazione di classe o struct è come un progetto iniziale usato per creare istanze o oggetti in fase di esecuzione. Se si definisce una classe o un tipo struct chiamato `Person`, `Person` è il nome del tipo. Se si dichiara e inizializza una variabile `p` di tipo `Person`, `p` è definito oggetto o istanza di `Person`. È possibile creare più istanze dello stesso tipo `Person` e nelle proprietà e nei campi di ogni istanza possono essere specificati valori diversi.  
  
 Una classe è un tipo riferimento. Quando viene creato un oggetto della classe, la variabile a cui è assegnato l'oggetto contiene solo un riferimento alla memoria. Se il riferimento all'oggetto viene assegnato a una nuova variabile, questa fa riferimento all'oggetto originale. Le modifiche apportate tramite una variabile vengono riflesse nell'altra variabile perché entrambe fanno riferimento agli stessi dati.  
  
 Un tipo struct è un tipo valore. Quando viene creato un tipo struct, la variabile a cui è assegnato questo tipo ne contiene i dati effettivi. Quando viene assegnato a una nuova variabile, il tipo struct viene copiato. La nuova variabile e quella originale contengono quindi due copie separate degli stessi dati. Eventuali modifiche apportate a una copia non influiscono sull'altra copia.  
  
 In generale, le classi vengono usate per modellare un comportamento più complesso o dati destinati a essere modificati dopo la creazione di un oggetto di classe. I tipi struct sono invece più adatti a piccole strutture che contengono principalmente dati non destinati a essere modificati dopo la creazione del tipo.  
  
 Per ulteriori informazioni, vedere [Classi](./classes.md), [Oggetti](./objects.md)e [Tipi di struttura](../../language-reference/builtin-types/struct.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente la classe `CustomClass` inclusa nello spazio dei nomi `ProgrammingGuide` contiene tre membri: un costruttore di istanze, una proprietà denominata `Number` e un metodo denominato `Multiply`. Il metodo `Main` nella classe `Program` crea un'istanza (oggetto) di `CustomClass` ed è possibile accedere al metodo e alla proprietà dell'oggetto usando la notazione del punto.
  
 [!code-csharp[csProgGuideObjects#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/class1.cs#1)]  
  
## <a name="encapsulation"></a>Incapsulamento  
 L'*incapsulamento* è talvolta definito come il principio fondamentale della programmazione orientata agli oggetti. In base al principio di incapsulamento, una classe o un tipo struct può specificare il modo in cui ognuno dei rispettivi membri è accessibile da codice esterno. I metodi e le variabili destinati a non essere usati all'esterno della classe o dell'assembly possono essere nascosti per limitare il rischio di errori di codifica o esiti dannosi.  
  
 Per altre informazioni sulle classi, vedere [Classi](./classes.md) e [Oggetti](./objects.md).  
  
### <a name="members"></a>Members  
 Tutti i metodi, i campi, le costanti, le proprietà e gli eventi devono essere dichiarati all'interno di un tipo e prendono il nome di *membri* del tipo. In C# non esistono variabili o metodi globali come in altri linguaggi. Anche il punto di ingresso di un programma, il metodo `Main`, deve essere dichiarato all'interno di una classe o di un tipo struct. Di seguito sono elencati tutti i tipi di membri che possono essere dichiarati in una classe o in un tipo struct.  
  
- [Campi](./fields.md)  
  
- [Costanti](./constants.md)  
  
- [Proprietà](./properties.md)  
  
- [Metodi](./methods.md)  
  
- [Costruttori](./constructors.md)  
  
- [Events](../events/index.md)  
  
- [Finalizzatori](./destructors.md)  
  
- [Indicizzatori](../indexers/index.md)  
  
- [Operatori](../../language-reference/operators/index.md)  
  
- [Tipi annidatiNested Types](./nested-types.md)  
  
### <a name="accessibility"></a>Accessibilità  
 Alcuni metodi e proprietà sono progettati in modo da essere chiamabili o accessibili da codice esterno alla classe o al tipo struct, noto come *codice client*. Altri metodi e proprietà possono invece essere usati esclusivamente all'interno della classe o del tipo struct. Questa distinzione è importante per limitare l'accessibilità del codice in modo che solo il codice client desiderato possa raggiungerlo. È possibile specificare l'accessibilità dei tipi e dei loro membri dal codice client usando i modificatori di accesso [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) e [private protected](../../language-reference/keywords/private-protected.md). L'accessibilità predefinita è `private`. Per altre informazioni, vedere [Modificatori di accesso](./access-modifiers.md).  
  
### <a name="inheritance"></a>Ereditarietà  
 Le classi (ma non i tipi struct) supportano il concetto di ereditarietà. Una classe che deriva da un'altra classe definita *classe di base* contiene automaticamente tutti i membri pubblici, protetti e interni della classe di base, ad eccezione di costruttori e finalizzatori. Per altre informazioni, vedere [Ereditarietà](./inheritance.md) e [Polimorfismo](./polymorphism.md).  
  
 Le classi possono essere dichiarate come [astratte](../../language-reference/keywords/abstract.md). Ciò significa che uno o più metodi di tali classi sono privi di implementazione. Anche se non è possibile crearne direttamente un'istanza, le classi astratte possono svolgere la funzione di classi di base per altre classi che forniscono l'implementazione mancante. Le classi possono anche essere dichiarate come [sealed](../../language-reference/keywords/sealed.md) per impedire che altre classi ereditino da esse. Per ulteriori informazioni, vedere [Classi astratte e sealed e Membri di classe](./abstract-and-sealed-classes-and-class-members.md).  
  
### <a name="interfaces"></a>Interfacce  
 Le classi e i tipi struct possono ereditare più interfacce. Quando eredita da un'interfaccia, un tipo implementa tutti i metodi definiti in tale interfaccia. Per ulteriori informazioni, vedi [Interfacce](../interfaces/index.md).  
  
### <a name="generic-types"></a>Tipi generici  
 Le classi e i tipi struct possono essere definiti con uno o più parametri di tipo. Il codice client fornisce il tipo quando ne crea un'istanza. Ad esempio, la classe <xref:System.Collections.Generic.List%601> nello spazio dei nomi <xref:System.Collections.Generic> viene definita con un solo parametro di tipo. Il codice client crea un'istanza di `List<string>` o `List<int>` per specificare il tipo che sarà contenuto nell'elenco. Per altre informazioni, vedere [Generics](../generics/index.md).  
  
### <a name="static-types"></a>Tipi statici  
 Le classi (ma non i tipi struct) possono essere dichiarate come [statiche](../../language-reference/keywords/static.md). Una classe statica può contenere solo membri statici e non è possibile crearne un'istanza con la nuova parola chiave. Una copia della classe viene caricata in memoria durante il caricamento del programma e i relativi membri sono accessibili tramite il nome della classe. Sia le classi che i tipi struct possono contenere membri statici. Per ulteriori informazioni, vedere [Classi statiche e Membri di classi statiche](./static-classes-and-static-class-members.md).  
  
### <a name="nested-types"></a>Tipi annidati  
 Una classe o un tipo struct può essere annidato all'interno di un'altra classe o di un altro tipo struct. Per ulteriori informazioni, vedere [Tipi annidati](./nested-types.md).  
  
### <a name="partial-types"></a>Tipi parziali  
 È possibile definire una parte di una classe, un tipo struct o un metodo in un file di codice e un'altra parte in un file di codice separato. Per altre informazioni, vedere [Classi e metodi parziali](./partial-classes-and-methods.md).  
  
### <a name="object-initializers"></a>Inizializzatori di oggetti  
 È possibile creare istanze e inizializzare oggetti classe o struct e raccolte di oggetti senza chiamare in modo esplicito il relativo costruttore. Per altre informazioni, vedere [Inizializzatori di oggetto e di raccolta](./object-and-collection-initializers.md).  
  
### <a name="anonymous-types"></a>Tipi anonimi  
 Nelle situazioni in cui non conviene o non è necessario creare una classe denominata, ad esempio quando si popola un elenco con strutture di dati che non devono necessariamente essere persistenti o passate a un altro metodo, è possibile usare i tipi anonimi. Per ulteriori informazioni, vedere [Tipi anonimi](./anonymous-types.md).  
  
### <a name="extension-methods"></a>Metodi di estensione  
 È possibile estendere una classe senza creare una classe derivata creando un tipo distinto i cui metodi possono essere chiamati come se appartenessero al tipo originale. Per altre informazioni, vedere [Metodi di estensione](./extension-methods.md).  
  
### <a name="implicitly-typed-local-variables"></a>Variabili locali tipizzate in modo implicito  
 All'interno di un metodo di classe o struct è possibile usare la tipizzazione implicita per indicare al compilatore di determinare il tipo corretto in fase di compilazione. Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](./implicitly-typed-local-variables.md).  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
