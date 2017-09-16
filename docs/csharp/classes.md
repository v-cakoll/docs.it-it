---
title: Classi - Guida a C#
description: Informazioni sui tipi di classe e su come crearli
keywords: .NET, .NET Core, C#
author: BillWagner
ms.author: wiwagn
ms.date: 10/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 95c686ba-ae4f-440e-8e94-0dbd6e04d11f
ms.translationtype: HT
ms.sourcegitcommit: b041fbec3ff22157d00af2447e76a7ce242007fc
ms.openlocfilehash: 13cbd3a5b53ea9b0f1acb22684b6a28639d00751
ms.contentlocale: it-it
ms.lasthandoff: 09/14/2017

---

# <a name="classes"></a>Classi
Una *classe* è un costrutto che consente di creare tipi personalizzati raggruppando insieme variabili di altri tipi, metodi e eventi. Una classe è simile a un progetto. Definisce i dati e il comportamento di un tipo. Se la classe non è dichiarata come statica, il codice client può usarla creando *oggetti* o *istanze* che vengono assegnate a una variabile. La variabile rimane in memoria fino a quando tutti i riferimenti non escono dall'ambito. In questa fase, CLR la contrassegna come idonea per Garbage Collection. Se la classe viene dichiarata come [statica](language-reference/keywords/static.md), viene mantenuta in memoria solo una copia e il codice client può accedervi solo tramite la classe stessa, non con una *variabile di istanza*. Per altre informazioni, vedere [Classi statiche e membri di classi statiche](programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  

## <a name="reference-types"></a>Tipi di riferimento  
Un tipo definito come [classe](language-reference/keywords/class.md) è un *tipo di riferimento*. In fase di esecuzione, quando si dichiara una variabile di un tipo di riferimento, la variabile contiene il valore [null](language-reference/keywords/null.md) fino a quando non si crea in modo esplicito un'istanza dell'oggetto usando l'operatore [new](language-reference/keywords/new.md), o fino a quando non gli viene assegnato un oggetto creato in un altro posto tramite [new](language-reference/keywords/new.md), come illustrato nell'esempio seguente:  

[!code-csharp[Reference Types](../../samples/snippets/csharp/concepts/classes/reference-type.cs)]
  
Quando viene creato l'oggetto, la memoria viene allocata nell'heap gestito e la variabile mantiene solo un riferimento al percorso dell'oggetto. I tipi nell'heap gestito richiedono un overhead quando vengono allocati e recuperati dalla funzionalità di gestione automatica della memoria di CLR, nota come *Garbage Collection*. La Garbage Collection è tuttavia anche altamente ottimizzata e, nella maggior parte degli scenari, non causa un problema di prestazioni. Per altre informazioni sulla Garbage Collection, vedere [Gestione automatica della memoria e Garbage Collection](../standard/garbage-collection/gc.md).  
  
I tipi di riferimenti supportano completamente l'*ereditarietà*, una caratteristica fondamentale nella programmazione orientata a oggetti. Quando si crea una classe, è possibile ereditare da qualsiasi altra interfaccia o classe che non è definita come [sealed](language-reference/keywords/sealed.md), e altre classi possono ereditare dalla classe ed eseguire l'override dei metodi virtuali. Per altre informazioni, vedere [Ereditarietà](programming-guide/classes-and-structs/inheritance.md).

## <a name="declaring-classes"></a>Dichiarazione di classi  
Le classi vengono dichiarate usando la parola chiave [class](language-reference/keywords/class.md), come illustrato nell'esempio seguente:  
  
[!code-csharp[Declaring Classes](../../samples/snippets/csharp/concepts/classes/declaring-classes.cs)]  
  
La parola chiave **class** è preceduta dal modificatore di accesso. Poiché in questo caso viene usata la parola chiave [public](language-reference/keywords/public.md), chiunque può creare oggetti da questa classe. Il nome della classe segue la parola chiave **class**. Il resto della definizione è il corpo della classe, in cui vengono definiti il comportamento e i dati. I campi, le proprietà, i metodi e gli eventi in una classe vengono collettivamente definiti *membri della classe*.  
  
## <a name="creating-objects"></a>Creazione di oggetti  
Una classe definisce un tipo di oggetto, ma non è un oggetto. Un oggetto è un'entità concreta ed è basato su una classe. Talvolta si fa riferimento all'oggetto come istanza di una classe.  
  
Gli oggetti possono essere creati tramite la parola chiave [new](language-reference/keywords/new.md) seguita dal nome della classe su cui si baserà l'oggetto, nel modo seguente:  
  
[!code-csharp[Creating Objects](../../samples/snippets/csharp/concepts/classes/creating-objects.cs)]   
  
Quando viene creata un'istanza di una classe, viene passato al programmatore un riferimento all'oggetto. Nell'esempio precedente, `object1` è un riferimento a un oggetto basato su `Customer`. Questo riferimento indica il nuovo oggetto, ma non contiene i dati dell'oggetto. Infatti, è possibile creare un riferimento all'oggetto senza creare un oggetto:  
  
[!code-csharp[Creating Objects](../../samples/snippets/csharp/concepts/classes/creating-objects2.cs)]  
  
Non è consigliabile creare riferimenti a oggetti come questo che non fanno riferimento a un oggetto reale perché il tentativo di accedere a un oggetto tramite tale riferimento avrà esito negativo in fase di esecuzione. Tuttavia, tale riferimento può essere creato per fare riferimento a un oggetto, creando un nuovo oggetto oppure assegnandolo a un oggetto esistente, come illustrato di seguito:  
  
[!code-csharp[Creating Objects](../../samples/snippets/csharp/concepts/classes/creating-objects3.cs)]  
  
Questo codice crea due riferimenti a oggetti che fanno entrambi riferimento allo stesso oggetto. Tutte le modifiche effettuate all'oggetto tramite `object3` si rifletteranno tuttavia nei successivi usi di `object4`. Poiché gli oggetti che si basano su classi vengono indicati tramite riferimenti, le classi sono note come tipi di riferimento.  
  
## <a name="class-inheritance"></a>Ereditarietà delle classi  
L'ereditarietà si ottiene usando una *derivazione*, vale a dire che una classe viene dichiarata usando una *classe di base* da cui eredita dati e comportamento. Una classe di base viene specificata tramite l'aggiunta di due punti e il nome della classe di base dopo il nome della classe derivata, nel modo seguente:  
  
[!code-csharp[Inheritance](../../samples/snippets/csharp/concepts/classes/inheritance.cs)]  
  
Quando una classe dichiara una classe di base, eredita tutti i membri della classe di base, a eccezione dei costruttori.  
  
Diversamente da C++, una classe di C# può ereditare direttamente solo da una classe di base. Tuttavia, poiché una classe di base può ereditare da un'altra classe, una classe può ereditare indirettamente più classi di base. Una classe può anche implementare direttamente più di un'interfaccia. Per altre informazioni, vedere [Interfacce](programming-guide/interfaces/index.md).  
  
Una classe può essere dichiarata come [astratta](language-reference/keywords/abstract.md). Una classe astratta contiene metodi astratti che hanno una definizione di firma, ma senza implementazione. Non è possibile creare un'istanza di classi astratte. Le classi astratte possono essere usate solo tramite classi derivate che implementano i metodi astratti. Al contrario, una classe [sealed](language-reference/keywords/sealed.md) non consente ad altre classi di derivare da tale classe. Per altre informazioni, vedere [Classi e membri delle classi astratte e sealed](programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
Le definizioni di classe possono essere suddivise tra file di origine diversa. Per altre informazioni, vedere [Definizioni di classi parziali](programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
 
## <a name="example"></a>Esempio
Nell'esempio seguente vengono definiti una classe pubblica che contiene un singolo campo, un metodo e un metodo speciale denominato costruttore. Per altre informazioni, vedere [Costruttori](programming-guide/classes-and-structs/constructors.md). Viene quindi creata un'istanza alla classe con la parola chiave **new**.

[!code-csharp[Class Example](../../samples/snippets/csharp/concepts/classes/class-example.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
Per altre informazioni, vedere le [specifiche del linguaggio C#](language-reference/language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="see-also"></a>Vedere anche  
[Guida per programmatori C#](programming-guide/index.md)   
[Polimorfismo](programming-guide/classes-and-structs/polymorphism.md)   
[Membri di classi e struct](programming-guide/classes-and-structs/members.md)   
[Metodi di classi e struct](programming-guide/classes-and-structs/methods.md)   
[Costruttori](programming-guide/classes-and-structs/constructors.md)   
[Finalizzatori](programming-guide/classes-and-structs/destructors.md)   
[Oggetti](programming-guide/classes-and-structs/objects.md)


