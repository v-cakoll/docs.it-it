---
title: Classi statiche e membri di classi statiche - Guida per programmatori C#
description: Non è possibile creare un'istanza delle classi statiche in C#. È possibile accedere ai membri di una classe statica usando il nome della classe.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, static members
- static members [C#]
- static classes [C#]
- C# language, static classes
- static class members [C#]
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
ms.openlocfilehash: 4f187d772d2f2e4375fbe3cfdc8c48af691f1c7c
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86863877"
---
# <a name="static-classes-and-static-class-members-c-programming-guide"></a>Classi statiche e membri di classi statiche (Guida per programmatori C#)

Una classe [statica](../../language-reference/keywords/static.md) corrisponde fondamentalmente a una classe non statica, ma c'è una differenza: di una classe statica non è possibile creare un'istanza. In altre parole, non è possibile usare l'operatore [new](../../language-reference/operators/new-operator.md) per creare una variabile del tipo di classe. Poiché non esiste una variabile dell'istanza, si accede ai membri di una classe statica tramite il nome stesso della classe. Se ad esempio si dispone di una classe statica denominata `UtilityClass` che ha un metodo statico pubblico denominato `MethodA`, si chiama il metodo come illustrato nell'esempio seguente:  
  
```csharp  
UtilityClass.MethodA();  
```  
  
 Una classe statica può essere usata come un contenitore adatto per insiemi di metodi che funzionano solo sui parametri di input e non devono ottenere o impostare campi di istanza interni. Nella libreria di classi .NET, ad esempio, la <xref:System.Math?displayProperty=nameWithType> classe statica contiene metodi che eseguono operazioni matematiche, senza alcun requisito per archiviare o recuperare dati univoci per una particolare istanza della <xref:System.Math> classe. In altre parole, si applicano i membri della classe specificando il nome della classe e il nome del metodo, come illustrato nell'esempio seguente.  
  
```csharp  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
```  
  
 Come nel caso di tutti i tipi di classe, le informazioni sul tipo per una classe statica vengono caricate dal runtime .NET quando viene caricato il programma che fa riferimento alla classe. Il programma non può specificare esattamente quando la classe verrà caricata. Tuttavia, è garantito che la classe sarà caricata, che i suoi campi saranno inizializzati e che il costruttore statico sarà chiamato prima che il programma faccia riferimento per la prima volta alla classe stessa. Un costruttore statico viene chiamato solo un volta e una classe statica rimane in memoria per la durata del dominio dell'applicazione in cui risiede il programma.  
  
> [!NOTE]
> Per creare una classe non statica che consente la creazione di un'unica istanza di se stessa, vedere [Implementing Singleton in C#](https://docs.microsoft.com/previous-versions/msp-n-p/ff650316%28v=pandp.10%29) (Implementare Singleton in C#).  
  
 Nell'esempio riportato di seguito sono indicate le principali funzionalità delle classi statiche:  
  
- Contiene solo membri statici.  
  
- Non è possibile crearne istanze.  
  
- È sealed.  
  
- Non può contenere [costruttori di istanze](./instance-constructors.md).  
  
 La creazione di una classe statica è pertanto analoga alla creazione di una classe che contiene solo membri statici e un costruttore privato, che impedisce la creazione di istanze della classe. Una classe statica presenta un indubbio vantaggio. Consente infatti al compilatore di verificare che non vengano aggiunti accidentalmente membri di istanze e quindi di garantire che non vengano create istanze di questa classe.  
  
 Le classi statiche sono sealed e pertanto non possono essere ereditate. Possono ereditare solo dalla classe <xref:System.Object>. Le classi statiche non possono contenere un costruttore di istanza. Tuttavia, possono contenere un costruttore statico. Le classi non statiche devono definire anche un costruttore statico se la classe contiene membri statici che richiedono un'inizializzazione più complessa. Per altre informazioni, vedere [Costruttori statici](./static-constructors.md).  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un esempio di una classe statica contenente due metodi che consentono di convertire i valori relativi alla temperatura da gradi Celsius a gradi Fahrenheit e viceversa:  
  
 [!code-csharp[csProgGuideObjects#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#31)]  
  
## <a name="static-members"></a>Membri static  
 Una classe non statica può contenere metodi, campi, proprietà o eventi statici. È possibile chiamare il membro statico di una classe anche quando non sono state create istanze della classe. Al membro statico si accede sempre tramite il nome della classe, non tramite il nome dell'istanza. Di un membro statico esiste una sola copia, indipendentemente dal numero di istanze della classe create. I metodi e le proprietà statici non possono accedere a eventi e campi non statici nel tipo contenitore e non possono accedere a una variabile di istanza di un oggetto a meno che non venga passato in modo esplicito in un parametro del metodo.  
  
 È più frequente dichiarare una classe non statica con alcuni membri statici, che dichiarare un'intera classe come statica. Due utilizzi comuni di campi statici sono: tenere un conteggio del numero di oggetti di cui è stata creata un'istanza o archiviare un valore che deve essere condiviso fra tutte le istanze.  
  
 I metodi statici possono essere sottoposti a overload ma non a override, perché appartengono alla classe e non a qualsiasi istanza della classe.  
  
 Sebbene non sia possibile dichiarare un campo come `static const`, il campo [const](../../language-reference/keywords/const.md) è essenzialmente statico nel comportamento. Appartiene al tipo, non a istanze del tipo. È pertanto `const` possibile accedere ai campi utilizzando la stessa `ClassName.MemberName` notazione utilizzata per i campi statici. Non è richiesta alcuna istanza dell'oggetto.  
  
 C# non supporta variabili locali statiche, ovvero variabili dichiarate nell'ambito del metodo.  
  
 I membri delle classi statiche vengono dichiarati tramite la parola chiave `static` prima del tipo restituito, come illustrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideObjects#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#29)]  
  
 I membri statici vengono inizializzati prima dell'accesso iniziale e prima dell'eventuale chiamata al costruttore statico, se presente. Per accedere a un membro di una classe statica, usare il nome della classe anziché il nome di una variabile per specificare la posizione del membro, come illustrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideObjects#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#30)]  
  
 Se la classe contiene campi statici, fornire un costruttore statico che li inizializzi al caricamento della classe.  
  
 Una chiamata a un metodo statico genera un'istruzione Call in Microsoft Intermediate Language (MSIL), mentre una chiamata a un metodo di istanza genera un' `callvirt` istruzione, che verifica anche la presenza di riferimenti a oggetti null. Tuttavia, nella maggior parte dei casi, la differenza di prestazioni tra i due non è significativa.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Classi statiche](~/_csharplang/spec/classes.md#static-classes) e [Membri statici e di istanza](~/_csharplang/spec/classes.md#static-and-instance-members) nella [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../index.md)
- [static](../../language-reference/keywords/static.md)
- [Classi](./classes.md)
- [class](../../language-reference/keywords/class.md)
- [Costruttori statici](./static-constructors.md)
- [Costruttori di istanza](./instance-constructors.md)
