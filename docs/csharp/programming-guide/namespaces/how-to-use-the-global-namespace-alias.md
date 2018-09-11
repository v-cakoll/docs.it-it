---
title: "Procedura: utilizzare l'alias dello spazio dei nomi globale (Guida per programmatori C#)"
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: c15271abb55cb29a200185e4b512a76a4913d848
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44195178"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a>Procedura: utilizzare l'alias dello spazio dei nomi globale (Guida per programmatori C#)
La possibilità di accedere a un membro nello [spazio dei nomi globale](../../../csharp/language-reference/keywords/namespace.md) è utile quando il membro può essere nascosto da un'altra entità con lo stesso nome.  
  
 Nel codice seguente, ad esempio, `Console` si risolve in `TestApp.Console` invece che nel tipo `Console` nello spazio dei nomi <xref:System>.  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 L'uso di `System.Console` causa comunque un errore perché lo spazio dei nomi `System` è nascosto dalla classe `TestApp.System`:  
  
 [!code-csharp[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 È tuttavia possibile evitare questo errore usando `global::System.Console`, come indicato di seguito:  
  
 [!code-csharp[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 Se l'identificatore di sinistra è `global`, la ricerca dell'identificatore di destra ha inizio dallo spazio dei nomi globale. La seguente dichiarazione fa ad esempio riferimento a `TestApp` come membro dello spazio globale.  
  
 [!code-csharp[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 Non è ovviamente consigliabile creare spazi dei nomi personali denominati `System` ed è improbabile trovare codice che include uno spazio dei nomi con tale nome. Nei progetti di grandi dimensioni è tuttavia molto probabile che si verifichi in qualche modo la duplicazione degli spazi dei nomi. In queste situazioni è possibile usare il qualificatore dello spazio dei nomi globale per specificare lo spazio dei nomi radice.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato lo spazio dei nomi `System` per includere la classe `TestClass`. Di conseguenza, è necessario usare `global::System.Console` per fare riferimento alla classe `System.Console`, nascosta dallo spazio dei nomi `System`. Viene inoltre usato l'alias `colAlias` per fare riferimento allo spazio dei nomi `System.Collections`. Di conseguenza, l'istanza di un oggetto <xref:System.Collections.Hashtable?displayProperty=nameWithType> è stata creata usando questo alias invece dello spazio dei nomi.  
  
 [!code-csharp[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
**A 1**
**B 2**
**C 3**

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Spazi dei nomi](../../../csharp/programming-guide/namespaces/index.md)  
- [. (operatore)](../../../csharp/language-reference/operators/member-access-operator.md)  
- [Operatore ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
- [extern](../../../csharp/language-reference/keywords/extern.md)
