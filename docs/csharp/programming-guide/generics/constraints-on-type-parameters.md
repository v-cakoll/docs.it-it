---
title: Vincoli sui parametri di tipo (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.assetid: 141b003e-1ddb-4e1c-bcb2-e1c3870e6a51
caps.latest.revision: 41
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e91ae026bd89a6dd30b4c9233da4dd897928291e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="constraints-on-type-parameters-c-programming-guide"></a>Vincoli sui parametri di tipo (Guida per programmatori C#)
Quando si definisce una classe generica è possibile applicare restrizioni ai tipi che il codice client può usare per gli argomenti di tipo quando crea un'istanza della classe. Se il codice client tenta di creare un'istanza della classe con un tipo non consentito da un vincolo, viene restituito un errore in fase di compilazione. Queste restrizioni sono definite vincoli. I vincoli vengono specificati usando la parola chiave contestuale `where`. La tabella seguente elenca i sei tipi di vincoli:  
  
|Vincolo|Descrizione|  
|----------------|-----------------|  
|where T: struct|L'argomento tipo deve essere un tipo valore. È possibile specificare qualsiasi tipo valore tranne <xref:System.Nullable>. Per altre informazioni, vedere [Utilizzo dei tipi nullable](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).|  
|where T : class|L'argomento tipo deve essere un tipo riferimento, incluso qualsiasi tipo di classe, interfaccia, delegato o matrice.|  
|where T : new()|L'argomento tipo deve avere un costruttore pubblico senza parametri. Quando il vincolo `new()` viene usato con altri vincoli, deve essere specificato per ultimo.|  
|where T : \<nome della classe di base>|L'argomento tipo deve corrispondere alla classe di base specificata o derivare da essa.|  
|where T : \<nome interfaccia>|L'argomento tipo deve corrispondere all'interfaccia specificata o implementare tale interfaccia. È possibile specificare più vincoli di interfaccia. L'interfaccia vincolante può anche essere generica.|  
|where T : U|L'argomento tipo fornito per T deve corrispondere all'argomento fornito per U o derivare da esso.|  
  
## <a name="why-use-constraints"></a>Motivi per cui usare i vincoli  
 Se si vuole esaminare un elemento di un elenco generico per stabilire se è valido oppure per confrontarlo con un altro elemento, è necessario garantire al compilatore che l'operatore o il metodo da chiamare sarà supportato da qualsiasi argomento tipo che può venire specificato dal codice client. A tale scopo è possibile applicare uno o più vincoli alla definizione di classe generica. Specificando il vincolo della classe di base, ad esempio, si indica al compilatore che verranno usati come argomenti tipo solo gli oggetti del tipo specificato o derivati da esso. In presenza di questa garanzia, il compilatore può consentire le chiamate ai metodi del tipo all'interno della classe generica. I vincoli vengono applicati usando la parola chiave contestuale `where`. L'esempio di codice seguente illustra la funzionalità che è possibile aggiungere alla classe `GenericList<T>` (in [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md)) applicando un vincolo della classe di base.  
  
 [!code-cs[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_1.cs)]  
  
 Il vincolo consente alla classe generica di usare la proprietà `Employee.Name` perché garantisce che tutti gli elementi di tipo T siano oggetti `Employee` oppure oggetti che ereditano da `Employee`.  
  
 È possibile applicare più vincoli allo stesso parametro di tipo. I vincoli stessi possono essere tipi generici, come illustrato di seguito:  
  
 [!code-cs[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_2.cs)]  
  
 Vincolando il parametro di tipo, il numero di operazioni e di chiamate ai metodi consentite viene ampliato includendo quelle supportate dal tipo vincolante e da tutti i tipi nella relativa gerarchia di ereditarietà. Di conseguenza, se durante la progettazione di classi o metodi generici si eseguono operazioni su membri generici diverse dalla semplice assegnazione o dalla chiamata a metodi non supportati da `System.Object`, sarà necessario applicare vincoli al parametro di tipo.  
  
 Quando si applica il vincolo `where T : class`, evitare gli operatori `==` e `!=` nel parametro di tipo perché questi operatori verificano solo l'identità del riferimento e non l'uguaglianza dei valori. Ciò avviene anche se si esegue l'overload degli operatori in un tipo usato come argomento. Il codice seguente illustra questo aspetto. L'output è false anche se la classe <xref:System.String> esegue l'overload dell'operatore `==`.  
  
 [!code-cs[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_3.cs)]  
  
 Questo comportamento è dovuto al fatto che, in fase di compilazione, il compilatore sa solo che T è un tipo riferimento e quindi deve usare gli operatori predefiniti validi per tutti i tipi riferimento. Per verificare l'uguaglianza dei valori, è consigliabile applicare anche il vincolo `where T : IComparable<T>` e implementare tale interfaccia nelle classi che verranno usate per costruire la classe generica.  
  
## <a name="constraining-multiple-parameters"></a>Vincolo di più parametri  
 È possibile applicare vincoli a più parametri e più vincoli a un singolo parametro, come illustrato nell'esempio seguente:  
  
 [!code-cs[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_4.cs)]  
  
## <a name="unbounded-type-parameters"></a>Parametri di tipo senza vincoli  
 I parametri di tipo che non hanno vincoli, ad esempio T nella classe pubblica `SampleClass<T>{}`, sono detti parametri di tipo senza vincoli. I parametri di tipo senza vincoli prevedono le regole seguenti:  
  
-   Gli operatori `!=` e `==` non possono essere usati perché non si ha la garanzia che siano supportati dall'argomento di tipo concreto.  
  
-   Possono essere convertiti in e da `System.Object` oppure convertiti in modo esplicito in qualsiasi tipo di interfaccia.  
  
-   È possibile eseguire il confronto con [Null](../../../csharp/language-reference/keywords/null.md). Se si confronta un parametro senza vincoli con `null` e l'argomento tipo è un tipo valore, verrà sempre restituito false.  
  
## <a name="type-parameters-as-constraints"></a>Parametri di tipo come vincoli  
 L'uso di un parametro di tipo generico come vincolo è utile quando una funzione membro con il proprio parametro di tipo deve vincolare tale parametro a quello del tipo che lo contiene, come illustrato nell'esempio seguente:  
  
 [!code-cs[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_5.cs)]  
  
 Nell'esempio precedente `T` è un vincolo di tipo nel contesto del metodo `Add` e un parametro di tipo senza vincoli nel contesto della classe `List`.  
  
 I parametri di tipo possono anche essere usati come vincoli nelle definizioni di classi generiche. Si noti che è necessario dichiarare il parametro di tipo tra parentesi acute, insieme a eventuali altri parametri di tipo:  
  
 [!code-cs[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_6.cs)]  
  
 L'utilità dei parametri di tipo usati come vincoli in classi generiche è molto limitata poiché il compilatore non può presupporre niente sul parametro di tipo, tranne il fatto che deriva da `System.Object`. Usare i parametri di tipo come vincoli nelle classi generiche in scenari in cui si vuole applicare una relazione di ereditarietà tra due parametri di tipo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.Generic>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Classi generiche](../../../csharp/programming-guide/generics/generic-classes.md)   
 [Vincolo new](../../../csharp/language-reference/keywords/new-constraint.md)

