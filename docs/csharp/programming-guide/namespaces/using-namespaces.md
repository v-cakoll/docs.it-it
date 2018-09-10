---
title: Utilizzo degli spazi dei nomi (Guida per programmatori C#)
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 81876d1818a6e82764e4aea0ae2b6f9e091f0ba3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44208647"
---
# <a name="using-namespaces-c-programming-guide"></a>Utilizzo degli spazi dei nomi (Guida per programmatori C#)
Gli spazi dei nomi vengono usati frequentemente nei programmi C# in due modi. In primo luogo, le classi di .NET Framework usano gli spazi dei nomi per organizzare numerose classi. In secondo luogo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi.  
  
## <a name="accessing-namespaces"></a>Accesso agli spazi dei nomi  
 La maggior parte delle applicazioni C# iniziano con una sezione di direttive `using`. In questa sezione sono elencati gli spazi dei nomi usati di frequente dall'applicazione, evitando al programmatore di specificare un nome completo ogni volta che viene usato un metodo contenuto negli spazi dei nomi.  
  
 Ad esempio, includendo la riga:  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]  
  
 All'inizio di un programma, il programmatore può usare il codice:  
  
 [!code-csharp[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]  
  
 Invece di:  
  
 [!code-csharp[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]  
  
## <a name="namespace-aliases"></a>Alias degli spazi dei nomi  
 È anche possibile usare la [direttiva using](../../../csharp/language-reference/keywords/using-directive.md) per creare un alias per uno [spazio dei nomi](../../../csharp/language-reference/keywords/namespace.md). Se ad esempio si usa uno spazio dei nomi scritto in precedenza che contiene spazi dei nomi annidati, è consigliabile dichiarare un alias per fornire un modo abbreviato per fare riferimento a uno di essi in particolare, come nell'esempio seguente:  
  
 [!code-csharp[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]  
  
## <a name="using-namespaces-to-control-scope"></a>Uso degli spazi dei nomi per controllare l'ambito  
 La parola chiave `namespace` viene usata per dichiarare un ambito. La possibilità di creare ambiti all'interno del progetto consente di organizzare il codice e di creare tipi univoci globali. Nell'esempio seguente, una classe denominata `SampleClass` è definita in due spazi dei nomi, uno annidato all'interno dell'altro. Oggetto [. ](../../../csharp/language-reference/operators/member-access-operator.md) viene usato per identificare il metodo da chiamare.  
  
 [!code-csharp[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]  
  
## <a name="fully-qualified-names"></a>nomi completi  
 Spazi dei nomi e tipi hanno nomi univoci, descritti da nomi completi che indicano una gerarchia logica. Ad esempio, l'istruzione `A.B` implica che `A` è il nome dello spazio dei nomi o del tipo e `B` è annidato al suo interno.  
  
 Nell'esempio seguente sono presenti classi e spazi dei nomi annidati. Il nome completo è indicato come commento dopo ogni entità.  
  
 [!code-csharp[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]  
  
 Nel segmento di codice precedente:  
  
-   Lo spazio dei nomi `N1` è un membro dello spazio dei nomi globale. Il relativo nome completo è `N1`.  
  
-   Lo spazio dei nomi `N2` è un membro di `N1`. Il relativo nome completo è `N1.N2`.  
  
-   La classe `C1` è un membro di `N1`. Il relativo nome completo è `N1.C1`.  
  
-   Il nome della classe `C2` viene usato due volte in questo codice. Tuttavia, i nomi completi sono univoci. La prima istanza di `C2` è dichiarata all'interno di `C1`, pertanto il relativo nome completo è: `N1.C1.C2`. La seconda istanza di `C2` è dichiarata all'interno di uno spazio dei nomi `N2`, pertanto il relativo nome completo è `N1.N2.C2`.  
  
 Usando il segmento di codice precedente, è possibile aggiungere un nuovo membro della classe, `C3`, allo spazio dei nomi `N1.N2` come indicato di seguito:  
  
 [!code-csharp[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]  
  
 In generale, usare `::` per fare riferimento a un alias dello spazio dei nomi oppure `global::` per fare riferimento allo spazio dei nomi globale e `.` per qualificare i tipi o i membri.  
  
 È un errore usare `::` con un alias che fa riferimento a un tipo, anziché a uno spazio dei nomi. Ad esempio:  
  
 [!code-csharp[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]  
  
 Tenere presente che la parola `global` non è un alias predefinito, pertanto `global.X` non ha alcun significato speciale. Acquisisce un significato speciale solo quando viene usata con `::`.  
  
 Se si definisce un alias denominato global, viene generato l'avviso del compilatore CS0440, perché `global::` fa sempre riferimento allo spazio dei nomi globale e non a un alias. Ad esempio, la riga seguente genera l'avviso:  
  
 [!code-csharp[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]  
  
 L'uso di `::` con gli alias è consigliabile e garantisce la protezione contro l'introduzione imprevista di tipi aggiuntivi. Si prenda, ad esempio, in considerazione quanto segue:  
  
 [!code-csharp[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]  
  
 Questo metodo funziona, ma se un tipo denominato `Alias` dovesse essere introdotto successivamente, `Alias.` sarebbe associato a tale tipo. L'uso di `Alias::Exception` assicura che `Alias` sia trattato come un alias di spazio dei nomi e non venga erroneamente considerato un tipo.  
  
 Per altre informazioni sull'alias `global`, vedere l'argomento [Procedura: utilizzare l'alias dello spazio dei nomi globale](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Spazi dei nomi](../../../csharp/programming-guide/namespaces/index.md)  
- [Parole chiave per gli spazi dei nomi](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [. (operatore)](../../../csharp/language-reference/operators/member-access-operator.md)  
- [Operatore ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
- [extern](../../../csharp/language-reference/keywords/extern.md)
