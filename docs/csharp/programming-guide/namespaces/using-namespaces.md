---
title: Uso degli spazi dei nomi - Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: b4326be8c9e299a96477096ec21864ec69037abe
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738236"
---
# <a name="using-namespaces-c-programming-guide"></a>Uso degli spazi dei nomi (Guida per programmatori C#)

Gli spazi dei nomi vengono usati frequentemente nei programmi C# in due modi. In primo luogo, le classi di .NET Framework usano gli spazi dei nomi per organizzare numerose classi. In secondo luogo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi.  
  
## <a name="accessing-namespaces"></a>Accesso agli spazi dei nomi

 La maggior parte delle applicazioni C# iniziano con una sezione di direttive `using`. In questa sezione sono elencati gli spazi dei nomi usati di frequente dall'applicazione, evitando al programmatore di specificare un nome completo ogni volta che viene usato un metodo contenuto negli spazi dei nomi.  
  
 Ad esempio, includendo la riga:  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 All'inizio di un programma, il programmatore può usare il codice:  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 Anziché:  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a>Alias dello spazio dei nomi

 È inoltre possibile utilizzare la [ `using` direttiva](../../language-reference/keywords/using-directive.md) per creare un alias per uno spazio dei nomi. Usare il [qualificatore di alias dello spazio dei nomi `::`](../../language-reference/operators/namespace-alias-qualifier.md) per accedere ai membri dello spazio dei nomi con alias. Nell'esempio seguente viene illustrato come creare e usare un alias dello spazio dei nomi:
  
[!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]
  
## <a name="using-namespaces-to-control-scope"></a>Uso degli spazi dei nomi per controllare l'ambito

 La parola chiave `namespace` viene usata per dichiarare un ambito. La possibilità di creare ambiti all'interno del progetto consente di organizzare il codice e di creare tipi univoci globali. Nell'esempio seguente, una classe denominata `SampleClass` è definita in due spazi dei nomi, uno annidato all'interno dell'altro. Il [ `.` token](../../language-reference/operators/member-access-operators.md#member-access-expression-) viene utilizzato per distinguere il metodo chiamato.  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a>Nomi completi

 Spazi dei nomi e tipi hanno nomi univoci, descritti da nomi completi che indicano una gerarchia logica. Ad esempio, l'istruzione `A.B` implica che `A` è il nome dello spazio dei nomi o del tipo e `B` è annidato al suo interno.  
  
 Nell'esempio seguente sono presenti classi e spazi dei nomi annidati. Il nome completo è indicato come commento dopo ogni entità.  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 Nel segmento di codice precedente:  
  
- Lo spazio dei nomi `N1` è un membro dello spazio dei nomi globale. Il relativo nome completo è `N1`.  
  
- Lo spazio dei nomi `N2` è un membro di `N1`. Il relativo nome completo è `N1.N2`.  
  
- La classe `C1` è un membro di `N1`. Il relativo nome completo è `N1.C1`.  
  
- Il nome della classe `C2` viene usato due volte in questo codice. Tuttavia, i nomi completi sono univoci. La prima istanza di `C2` è dichiarata all'interno di `C1`, pertanto il relativo nome completo è: `N1.C1.C2`. La seconda istanza di `C2` è dichiarata all'interno di uno spazio dei nomi `N2`, pertanto il relativo nome completo è `N1.N2.C2`.  
  
 Usando il segmento di codice precedente, è possibile aggiungere un nuovo membro della classe, `C3`, allo spazio dei nomi `N1.N2` come indicato di seguito:  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 In generale, usare il [qualificatore di alias dello spazio dei nomi `::`](../../language-reference/operators/namespace-alias-qualifier.md) per fare riferimento a un alias dello spazio dei nomi oppure `global::` per fare riferimento allo spazio dei nomi globale e `.` per qualificare i tipi o i membri.  
  
 È un errore usare `::` con un alias che fa riferimento a un tipo, anziché a uno spazio dei nomi. Ad esempio:  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 Tenere presente che la parola `global` non è un alias predefinito, pertanto `global.X` non ha alcun significato speciale. Acquisisce un significato speciale solo quando viene usata con `::`.  
  
 Se si definisce un alias denominato global, viene generato l'avviso del compilatore CS0440, perché `global::` fa sempre riferimento allo spazio dei nomi globale e non a un alias. Ad esempio, la riga seguente genera l'avviso:  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 L'uso di `::` con gli alias è consigliabile e garantisce la protezione contro l'introduzione imprevista di tipi aggiuntivi. Si prenda, ad esempio, in considerazione quanto segue:  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 Questo metodo funziona, ma se un tipo denominato `Alias` dovesse essere introdotto successivamente, `Alias.` sarebbe associato a tale tipo. L'uso di `Alias::Exception` assicura che `Alias` sia trattato come un alias di spazio dei nomi e non venga erroneamente considerato un tipo.  

## <a name="see-also"></a>Vedere anche

- [Guida alla programmazione in C](../index.md)
- [Spazi dei nomi](./index.md)
- [Espressione di accesso ai membri](../../language-reference/operators/member-access-operators.md#member-access-expression-)
- [:: (operatore)](../../language-reference/operators/namespace-alias-qualifier.md)
- [extern alias](../../language-reference/keywords/extern-alias.md)
